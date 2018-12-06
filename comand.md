# コマンド備忘録

## MarkDown

| コマンド  | 実行内容                           |
|:---------:|:----------------------------------:|
| C-c C-c m | HTMLファイルを出力                 |
| C-c C-c p | 一時ファイル作成、ブラウザで表示   |
| C-c C-c l | ライブプレビューモードを有効にする |

## Terminal操作関連
・カレントディレクトリ以下に hogehoge の記述があるか探す。  
```
$ grep -r hogehoge
```

## Github関連
・ブランチを指定して git clone  
```
$ git clone -b <branch_name> <URL>
```

・コミットしてプッシュするまで  
```
$ git add <file_name>  
$ git commit -m "[something_new] hoge"  
$ git push <local_branch> <remote_branch>  
```

・フォルダごと add  
```
$ git add <folder_name>  
```

・all オプション  
```
\#全部 add  
$ git add -A  
\#拡張子指定(ex. .txt)  
$ git add -A *.txt  
```

・ローカルで削除したファイルのリモートへの反映（git管理下のファイルで、変更されたものすべてを add ）  
```
$ git add -u  
$ git commit -m "cleanup" <- メッセージは自由  
```  
個別に消すなら` git rm <file_name>`  

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

## バージョンチェック関連
・OpenCV のバージョン確認  
```
$ pkg-config --modversion opencv
```

## CMakeの方法
```
$ cd <package_name>  
$ mkdir build  
$ cd build  
$ cmake ..  
$ make -j8  
$ make install  
```
#### uninstallの方法
```
$ ~/build  
$ sudo make uninstall <-- /usr/local からソースを消す  
```

## ROS関連
・src内にあるpackage.xmlに記述のある依存関係のパッケージを一括ダウンロード
`rosdep install -iry --from-paths src`
