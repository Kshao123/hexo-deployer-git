# add new arg => all
**通过增加参数实现 push 整个文件夹，而非指定 public 文件夹**
```javascript
// lib/deployer.js => line: 93
// ...
then(() => {
	if (args.all) {
		log.info('Clearing .deploy_git .git... -ksh');
		return fs.rmdirSync(pathFn.join(deployDir, '.git'));
	}
})
```
## usage
in blog root `_config.yml` add `all: true` to deployer
```yaml
deploy:
  - type: git
    branch: master
    repo: <git repo url>
    
  - type: git
    all: true # 将整个文件夹提交
    branch: bolg
    repo: <git repo url>
```

# 2024/05/07
update from hexo-git
