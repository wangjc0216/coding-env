# Git

针对git有很多使用方法，需要熟能生巧。 同时为了对抗记忆的遗忘，git的模型也需要深刻理解，这有助于对git的使用。


## 常见命令



## git-cz
git-cz是git commit 规范的一个项目，使用npm来进行安装，在安装好后，可以使用git-cz命令来代替之前使用的git commit命令。

```
//全局安装
npm install -g commitizen cz-conventional-changelog
echo '{ "path": "cz-conventional-changelog" }' > ~/.czrc

//需要在path中增加链接，当前的经验是在Mac上的/usr/local/bin目录下增加软链接
ln -s  /usr/local/lib/node_modules/node/lib/node_modules/commitizen/bin/git-cz  /usr/local/bin/git-cz

//执行git-cz即可验证是否安装完成
git-cz
```