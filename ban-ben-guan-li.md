# 版本规范 {#版本规范}

注意

项目开始开发时，预先新建 develop 分支，并在此分支上进行开发。若要变更分支名，请将./build/release.sh 文件中的分支名一同修改。否则 npm run release 命令会报错。

项目默认在分支 develop 上开发，并将生产版本代码合并至 master 上。项目中的 bulid 文件夹下的 release 文件中为打包脚本，用于自动上传代码、添加 tag、合并分支。 正式发布版本时，请使用 npm run release，该命令会自动在分支上打上 tag 值并合并分支至 master 上。

如果想要重复提交相同版本号的代码，请先将 package.json 中的版本号复原，再删除 Git 上的相应 tag 值。之后再使用 npm run release 提交代码。

```
git checkout master
git merge develop

#!/usr/bin/env sh
set -e
echo "Enter release version: "
read VERSION

read -p "Releasing $VERSION - are you sure? (y/n)" -n 1 -r
echo    # (optional) move to a new line
if [[ $REPLY =~ ^[Yy]$ ]]
then
  # build
  npm version $VERSION --no-git-tag-version
  VERSION=$VERSION npm run build

  # commit
  git tag v$VERSION

  git commit -am "release: $VERSION"

  # publish
  git push origin master
  git push origin refs/tags/v$VERSION
  git checkout develop
  git rebase master
  git push origin develop

  npm run build
```

项目的版本号应该根据某些规则进行迭代, 这里推荐使用语义化版本规范, 通过这个规范，用户可以了解版本变更的影响范围。 规则如下:

* 主版本号：当你做了不兼容的 API 修改 \(v1.0.0 -&gt; v2.0.0\)
* 次版本号：当你做了向下兼容的功能性新增 \(v1.0.0 -&gt; v1.1.0\)
* 修订号：当你做了向下兼容的问题修正 \(v1.0.0 -&gt; v1.0.1\)

项目中已经配置好了打生产包命令

