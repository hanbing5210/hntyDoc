## Rebase 基变

### 参考资料
* [git 合并某个提交commit到指定的分支上](https://blog.csdn.net/anhenzhufeng/article/details/77962943)
* [git rebase --onto 中onto的作用](https://segmentfault.com/q/1010000008299360)
* [Git HEAD detached from XXX (git HEAD 游离) 解决办](https://blog.csdn.net/u011240877/article/details/76273335)

### 描述
**detection** 项目导入了company6 的 .jdl 生成修改了百余个文件，且此 commit 提交较早，后面又提交了许多commit，索性
对后面commit影响不大，仅有几个commit又影响。
![](/系统集成部/石万/resource/git/TIM截图20180918083415.png)

### 步骤
1. 由shop分支新建cpShop分支，获得所有commit
2. 新建分支init并reset --hdard到 Initial application generated by JHipster-5.1.0 这个commit
	![](/系统集成部/石万/resource/git/TIM截图20180918083703.png)
3. 查看commit发现不可merge到init分支的commit，发现以下几个commit不可需要(存在牵扯company6)
	![](/系统集成部/石万/resource/git/TIM截图20180918083921.png)
4. 将 **添加excel支持** 这个commit 移到init去。先切换到init分支    

	```bash
		git cherry-pick c913d8c
	```

5. 将一系列 commit 合并到 init 分支
> git rebase --onto base from to    
> 注意这里有个坑， 这里的 from（开始的commit）并不会合并到init去，要合并from请填写前一个commit id

### 实际步骤（再看看文档可能我这里有些操作是错的，不过结果成功了）
1. init分支执行 **git rebase --onto init(branchName) a92aa12(startCommitId) cae158cd0ebbb51c8accae3013c58e55095066a1(enCommitId)**
	> 这里的 **a92aa12** 就是from的那个坑，要写需要开始合并commit的前一个commit Id
2. 这里出现了报错    

	```bash
		Resolve all conflicts manually, mark them as resolved with 
		"git add/rm <conflicted_files>", then run "git rebase --continue". 
		You can instead skip this commit: run "git rebase --skip". 
		To abort and get back to the state before "git rebase", run "git rebase --abort".

		git rebase (--continue | --abort | --skip)
		If that is not the case, please
        rm -fr "F:/jhipster/ng6/detection/.git/rebase-apply"
		and run me again.  I am stopping in case you still have something
		valuable there.
	```
3. 这里是rebase发生冲突，是否继续。这里需要执行git rm 删除文件并从 git 的记录中剔除。操作解决冲突。直至rebase成功。    
	
	```bash
	git rm .\src\main\webapp\app\shared\shared.module.ts
	// 然后执行 git rebase --comtinue
	git rebase --comtinue
	// 如果发生 commit 修改的文件已经不存在(被git rm 移除掉了)可以执行下命令忽略
	git rebase --skip
	```

4. rebase成功后，遇到了游离分支问题，当前的HEAD没有指向init而是一个游离状态    

	```
	// 新建rebase分支
	git branch rebase
	// 当前提交的代码放到整个分支
	git checkout rebase
	```

5. 比较 --continue 和 --skip 的文件将最终结果修改到rebase分支上去提交新commit


### 教程步骤1（非实际操作的步骤）
> $ git rebase --onto argument1 argument2 argument3
* argument1是复制操作的目标提交。     
它将是argument2之后提交的前身。    
* argument2是将要复制的范围的第一次提交的前身。      
但是，argument2本身不会被复制。    
* argument3是将要复制的范围的最后一次提交。

eg1: 
```
git rebase --onto M O R
```
![](/系统集成部/石万/resource/git/git-rebase-onto-1.png)

eg2:
```
git rebase --onto L O R
```
![](/系统集成部/石万/resource/git/git-rebase-onto-2.png)


### 教程步骤2（非实际操作的步骤）
> $  git rebase   [startpoint]   [endpoint]  --onto  [branchName]

[startpoint]  [endpoint]仍然和上一个命令一样指定了一个编辑区间(前开后闭)，--onto的意思是要将该指定的提交复制到哪个分支上。
所以，在找到C(90bc0045b)和E(5de0da9f2)的提交id后，我们运行以下命令：

    git  rebase   90bc0045b^   5de0da9f2   --onto master
注:因为[startpoint]  [endpoint]指定的是一个前开后闭的区间，为了让这个区间包含C提交，我们将区间起始点向后退了一步。
