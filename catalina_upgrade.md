# macOS Marverick から Catalina へのアップグレードに関するメモ
書きかけ
## macOS のアップグレード
1. システム環境設定 > ソフトウェアアップデート から選択
2. ダウンロードに20〜30分，インストールに同じくらいの時間がかかる
## F-Secure にフルディスクアクセスを許可
1. F-Secure がフルディスク・アクセスを許可を求めてくるので，セキュリティとプライバシーから許可．
## bash → zsh
1. Terminal.app を起動すると
    ```
    The default interactive shell is now zsh.
    To update your account to use zsh, please run `chsh -s /bin/zsh`.
    ```
    と出てくるので，それに従う.
    ```
    chsh -s /bin/zsh
    ```
    を実行．
2. ```~/.zshrc```を以下のように修正．
   ```
   source ~/Dropbox/.zshrc

   export PATH=/usr/local/bin:$PATH
   export PATH=/usr/local/opt/ruby/bin:$PATH
   export PATH=$HOME/.gem/ruby/2.6.0/bin:$PATH
   
   # the following lines were inserted for pyenv
   export PYENV_ROOT="${HOME}/.pyenv"
   export PATH="${PYENV_ROOT}/bin:$PATH"
   eval "$(pyenv init -)"
   # the above lines were inserted for pyenv
   ```
## homebrew の更新
```
brew update
brew upgrade
```
だけでいけた．
