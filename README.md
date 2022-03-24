# Dockerインストールの際にエラーが出てつまずいたのでメモ
以下、対処方法など

## PC
MacBook Pro 13-inch, 2016

## OS
macOS Monterey
バージョン　12.2.1

### エラー

You don't have write access to　/Users/my-user-name/.docker/contexts　Delete it or fix its permissions before restarting Docker Desktop.

注）my-user-nameはPC所有者の名前

### 対処
権限の問題の様子。
エラーコードをそのまま検索して、下記のURLを参考に対処した。

https://github.com/lando/lando/issues/2780

コマンドは２つ試した
1. sudo chmod -R my-user-name /Users/my-user-name/.docker/contexts
2. sudo chown -R username /Users/username/.docker/contexts
注）my-user-nameやusernameはPC所有者の名前

自分の場合１では治らなかったが、２で治った。
以上。
