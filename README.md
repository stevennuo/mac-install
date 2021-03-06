# mac-install 
本文主要流程参考自[sb2nov/mac-setup](https://github.com/sb2nov/mac-setup)，最近在[关注HomeBrew Cask](http://caskroom.io/)

开始：
* 先app store升级系统和xcode
* El Captain -> [System Integrity Protection](http://apple.stackexchange.com/questions/193368/what-is-the-rootless-feature-in-el-capitan-really/193379) -> [FIX](http://stackoverflow.com/questions/33145388/gem-update-install-operation-not-permitted-since-el-capitan-how-to-set-default)
* [Chrome](https://www.baidu.com/s?wd=chrome)
* [HomeBrew](http://brew.sh) -> 如果GFW把里面的脚本单独下载本地cat执行 -> `brew install git git-town gist git-flow`
* [Shadowsocks](https://github.com/stevennuo/shadowsocks) [服务器配置](https://github.com/guanghetv/op/blob/master/server/cloud/shadowsocks.md)
* Sign in Chrome -> restart -> sync

[主要参考见这里](https://github.com/sb2nov/mac-setup)
* 创建文件夹
``` 
mkdir ~/restore 
mkdir ~/restore/app
mkdir ~/restore/dmg
mkdir ~/codes
mkdir ~/sync
mkdir ~/cfg
cd ~/codes
git clone https://github.com/stevennuo/mac-install.git
git clone https://github.com/altercation/solarized
git clone https://github.com/jkaving/intellij-colors-solarized.git
ln -s ~/codes/mac-install/.gitignore_global ~/.gitignore_global
ln -s ~/codes/mac-install/iterm/env.sh ~/cfg/env.sh
ln -s ~/codes/mac-install/iterm/zshrc ~/.zshrc
ln -s ~/codes/mac-install/iterm/vimrc ~/.vimrc
```

* Git && Github
```
cd ~/codes
git config --global core.excludesfile ~/.gitignore_global
curl -s -O https://github-media-downloads.s3.amazonaws.com/osx/git-credential-osxkeychain
chmod u+x git-credential-osxkeychain
sudo mv git-credential-osxkeychain "$(dirname $(which git))/git-credential-osxkeychain"
```
输完密码 `git config --global credential.helper osxkeychain`


* [proxychains](https://github.com/rofl0r/proxychains-ng)
```
cd ~/codes && git clone https://github.com/rofl0r/proxychains-ng
cd ~/codes/proxychains-ng
./configure --prefix=/usr --sysconfdir=/etc
make
sudo make install
sudo make install-config
```
修改/etc/proxychains.conf最后一行proxylist `socks5  127.0.0.1 1080`

* [系统配置](https://github.com/sb2nov/mac-setup/tree/master/SystemPreferences)
* [iTerm-注意color和font,字体用mac自带fontbook统一安装](https://github.com/sb2nov/mac-setup/tree/master/iTerm) -> [Zsh-env和zsh上面脚本已配置](https://github.com/sb2nov/mac-setup/blob/master/iTerm/zsh.md) -> [Git快捷按键文档](https://github.com/robbyrussell/oh-my-zsh/wiki/Plugin:git) -> [Git Town](https://github.com/Originate/git-town)
iterm里面存放的是ohmyzsh的配置文件,如果需要可以自行修改
* [以下APP安装请看这里](https://github.com/sb2nov/mac-setup/tree/master/Apps):  
  Alfred / AppCleaner / Spectacle / Unarchiver / CheatSheet / VLC
* [Sublime](https://github.com/sb2nov/mac-setup/tree/master/SublimeText) -> [command tool](https://gist.github.com/olivierlacan/1195304)
* [Nodejs](https://nodejs.org/en/) -> [permission issue](https://docs.npmjs.com/getting-started/fixing-npm-permissions) -> [cnpm](http://npm.taobao.org/) -> `npm install -fg browserify buddy.js eslint eslint-config-defaults eslint-plugin-filenames js-beautify jsinspect mocha nodemon npm-check-updates pm2`

其它:
* [1Password](https://itunes.apple.com/us/app/1password-password-manager/id443987910?mt=12)
* [Canarymail](http://canarymail.io/)
* [DASH](https://itunes.apple.com/us/app/dash/id449589707?ls=1&mt=12)
* [PopClip](https://pilotmoon.com/popclip/)
  Plugin: paste/delete/selectall/trello/google/baidu/taobao/openinchrome/dash/terminal
* [GitX](http://gitx.frim.nl/) -> 设置Terminal tool
* [Thunder](http://mac.xunlei.com/)
* [aria2](https://aria2.github.io/)
* [WeChat](http://weixin.qq.com/cgi-bin/readtemplate?t=mac)
* [钉钉](http://www.dingtalk.com/#a1)
* [阿里旺旺](http://labs.etao.com/aliwangwang)
* [Aerial屏保](https://github.com/JohnCoates/Aerial)
* [微云](http://www.weiyun.com/)
* [producthunt](https://www.producthunt.com/apps/mac)
* [mosh](https://mosh.mit.edu/)
* [Kap](https://getkap.co)
* [Cal](http://instacalapp.com/)

开发:
* [WebStorm](http://www.jetbrains.com/webstorm/) -> [license](https://s.taobao.com/search?q=webstorm) -> [color](https://github.com/jkaving/intellij-colors-solarized) -> [live template](https://github.com/stevennuo/webstorm-es6-livetpls)
`ln -s ~/codes/mac-install/JavaScript.xml ~/Library/Preferences/WebStorm11/templates/JavaScript.xml`
* [PyCharm](https://www.jetbrains.com/pycharm/) 其他同上
* ssh-copy-id
```
brew install ssh-copy-id
ssh-keygen
ssh-copy-id -i master@bd.yangcong345.com
```
* [3T MongoChef](http://3t.io/mongochef/download/platform/)

!!!Reddis 采用docker

!!!Mongo 采用docker
