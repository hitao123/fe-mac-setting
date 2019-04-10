# 前端 mac 换机 环境搭建

## 备好梯子

> 由于后续一些软件安装可能需要翻墙，包括 chrome 同步，都是需要的

## homebrew

> 管理 mac 系统软件包，类似 npm，我们可以用来安装 nodejs, git, nginx wget 等一些包

```sh
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

brew install node git
```

## 编辑器 & 编辑器插件

> 推荐安装 vscode, 把 vscode recommend 的所有插件安装就可以了, [官网下载](https://code.visualstudio.com/)

## oh-my-zsh

> zsh 比较好用，有一些好看的主题，还要 tab 填充提示，有助于提升开发效率

```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

chsh -s /usr/local/bin/zsh // 设置为系统默认 bash
```

### plugins

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

### themes

```js
ZSH_THEME="agnoster"

安装中文字体

# clone
git clone https://github.com/powerline/fonts.git
# install
cd fonts
./install.sh
```

## git 账号配置

> 一般会使用 git 配置全局变量

```sh
git config --global user.name author # 将用户名设为author
git config --global user.email author@corpmail.com # 将用户邮箱设为author@corpmail.com

ssh-keygen

复制 .ssh/id_rsa.pub 内容到 gitlab

```