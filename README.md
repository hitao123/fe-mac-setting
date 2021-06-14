# 前端 mac 换机 环境搭建

## 一、备好梯子

> 由于后续一些软件安装可能需要翻墙，包括 chrome 插件同步，都是需要的

## 二、homebrew 安装（mac 下包管理神器）

> 管理 mac 系统软件包，类似 npm，我们可以用来安装 nodejs, git, nginx wget 等一些其他工具包

```sh
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

brew install node git yarn zsh-autosuggestions

```

## 三、IDE 编辑器 & 编辑器插件安装

> 推荐安装 vscode, 把 vscode recommend 的所有插件安装就可以了, [官网下载](https://code.visualstudio.com/)


### vscode 插件同步

> 可以使用
Settings Sync是一款免费好用的VSCode插件。它是一款使用GitHub中的Gists作为配置文件存储来实现同步的。它可以让我们在无数个设备上同步VSCode的配置，
具体使用方式参照 [插件同步](https://juejin.cn/post/6844904145749540877)


## 四、git 账号配置

> 一般会使用 git 配置全局变量

```sh
git config --global user.name author # 将用户名设为author
git config --global user.email author@corpmail.com # 将用户邮箱设为author@corpmail.com

ssh-keygen

复制 .ssh/id_rsa.pub 内容到 代码仓库的密钥配置

```

```sh

vi ~/.gitconfig

[user]
        name = xx
        email = xx@gmail.com
[alias]
        co = checkout
        br = branch
        ci = commit
        st = status
        unstage = reset HEAD --
        last = log -1 HEAD
        gd = git diff --cached
[filter "lfs"]
        process = git-lfs filter-process
        required = true
        clean = git-lfs clean -- %f
        smudge = git-lfs smudge -- %f
[core]
        pager = git-split-diffs --color | less -RFX

```

git-lfs  git-split-diffs 需要单独安装

## 五、安装 oh-my-zsh (可能是地球上最好用的bash)

> zsh 比较好用，有一些好看的主题，还要 tab 填充提示，有助于提升开发效率

```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

chsh -s /usr/local/bin/zsh // 设置为系统默认 bash
```

### oh-my-zsh plugins

```js
  vi ~/.zshrc

  plugins=(
    git
    bundler
    dotenv
    osx
    rake
    rbenv
    ruby
  )
```

### oh-my-zsh themes

```js
ZSH_THEME="agnoster"

安装中文字体

# clone
git clone https://github.com/powerline/fonts.git
# install
cd fonts
./install.sh
```

## 六、node 环境相关

```
1. npm registry settings

npm i nrm -g

# 下面备选，推荐使用 nrm 切换源
npm config set registry https://registry.npm.taobao.org
npm config set registry https://registry.npmjs.org/

2. node version settings  用来切换不同 node 版本

npm i nvm -g

```

## 七、其他

### mac 下软件下载清单

- Chrome
- pap.er (壁纸软件)
- 微信
- Xmind
- Sketch
- Charles

### chrome 插件推荐

- ABP
- Grammarly for Chrome
- JSONView
- Momentum
- Pesticide for Chrome
- Redux DevTools
- React Developer Tools
- Proxy SwitchyOmega
- Vue.js devtools
- Tampermonkey
- Wappalyzer
- 壹伴
- 掘金
