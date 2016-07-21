# git-hooks
Git Hooks

# 使い方


#### ソースをローカルへクローニング

※clone する場所をHomeにしておきます。
  
```
$ cd ~
$ git clone https://github.com/kenzo0107/git-hooks
```  
  
  
#### 実行権限付与

```
$ chmod 0777 ~/git-hooks/.git_template/hooks/pre-commit
```
  
  
#### フック設定

```
git config --global init.templatedir ~/git-hooks/.git_template/
```
  
#### 設定確認

```
git config --list

...
init.templatedir=/Users/kenzo/git-hooks/.git_template/
...
```



上記設定は `git clone` もしくは `git init` したタイミングで適用されます。
  
  
その為、既にclone済みの場合は、そのプロジェクトの最高階層で`git init`すること。

```
cd `git rev-parse --show-toplevel`
git init
```
  

#### pre-commitが反映されているか確認


* t.phpファイル作成

```
vi t.php
```

```
<php
a = 1
?>
```


* indexへ追加

`git add t.php`
  

* git commit



```
git commit -m "create t.php"


PHP Parse error:  syntax error, unexpected '=' in t.php on line 2

Parse error: syntax error, unexpected '=' in t.php on line 2
Errors parsing t.php
```

上記のように `git commit`しようとするとシンタックスエラーが表示され実行できなくなれば、設定反映されています。


以上

