# Githubコマンド備忘録

### 参考ページ
> [リモートからの取得とリモートへの反映(fetch, pull, push)](https://qiita.com/forest1/items/db5ac003d310449743ca)	
> [fork元のリポジトリへの変更をforkしたリポジトリに反映する](https://qiita.com/chihiro/items/d018599ef13c35781412)

#### ブランチを指定して git clone  
```
$ git clone -b <branch_name> <URL>
```

#### コミットしてプッシュするまで  
```
$ git add <file_name>  
$ git commit -m "[something_new] hoge"  
$ git push <local_branch> <remote_branch>  
```

#### フォルダごと add  
```
$ git add <folder_name>  
```

#### all オプション  
```
\#全部 add  
$ git add -A  
\#拡張子指定(ex. .txt)  
$ git add -A *.txt  
```

#### ローカルで削除したファイルのリモートへの反映（git管理下のファイルで、変更されたものすべてを add ）  
```
$ git add -u  
$ git commit -m "cleanup" <- メッセージは自由  
```  
個別に消すなら` git rm <file_name>`  


### ブランチの削除
#### リモートブランチ
一度ローカルのブランチに checkout してそこからリモートを削除
```
$ git checkout [branchname]
$ git fetch -p
$ git pull origin [branchname]
$ git push --delete origin [branchname]
```

#### ローカルブランチ
マージ済みのブランチ
```
$ git branch -d [branch_name]
```
マージされていないブランチ
```
$ git branch -D [branch_name]
```

### フォークしてその先で変更を加える  
1. 対象のページから自分のリポジトリに Fork   
2. 自分のローカル環境に clone (`$ git clone https://hogehoge`)  
3. クローンした開発環境下で作業  
4. 更新した内容をフォークしたリポジトリに commit  
5. fork したリポジトリからオリジナルへ pull request  

#### フォーク元のやつを引っ張ってくる
```
$ git fetch [fork元]  
```

### コミットせずに変更を退避させる
```
$ git stash save
```
#### 作業退避時にメッセージをつける
```
$ git stash save "hoge"
$ git stash list  
  >>> stash@{0}: On test: hoge
```

### 退避した作業の一覧を見る
```
$ git stash list
```

### 退避した作業を戻す
```
$ git stash apply stash@{0}
```

### 退避した作業を消す
```
$ git stash drop stash@{0}
```
`stash`を使用して元に戻しても、退避した作業はそのまま残る
