## submodule 的使用

### 1、添加子模块
```shell
# 添加子模块
git submodule add git@github.com:gaollard/test_submodule_B.git  projectB

# 可设置子模块在当前项目的相对路径
git submodule add http://test.com/backend src/vendor/
```

### 2、检出项目的指定版本
```shell
# 检出项目的指定版本(HEAD), 注意它并不是指向一个分支
git submodule update
```

### 3、拉取项目时拉取子模块
```shell
# 可在拉取项目时把依赖的子模块同时拉取下来
git clone –recursive
```

### 4、submodule ignore 选项
```
untracked ：忽略在子模块B(projectB目录)新添加的，未受版本控制内容
dirty     ：忽略对projectB目录下受版本控制的内容进行了修改
all       ：同时忽略untracked和dirty
```

### 5、modified: XXX (new commits)
说明当前主仓库依赖的 HEAD 和 本地仓库提交不匹配了，这个时候要特别注意。
- 如果希望使用旧的 `HEAD`，使用 `git submodule update`；
- 如果希望使用新的 `HEAD`，那么就 `git add ` 提交代码；