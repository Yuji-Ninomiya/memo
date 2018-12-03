# コマンド備忘録

## MarkDown

| コマンド                                   | 実行内容                           |
|--------------------------------------------|------------------------------------|
| C-c C-c m                                  | HTMLファイルを出力                 |
| C-c C-c p                                  | 一時ファイル作成、ブラウザで表示   |
| C-c C-c l , M-x markdown-live-preview-mode | ライブプレビューモードを有効にする |

## terminal 関連
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
$ git commit -m "\[something_new] hoge"  
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

・フォークしてその先で変更を加える  
1. 対象のページから自分のリポジトリに Fork   
2. 自分のローカル環境に clone (`$ git clone https://hogehoge`)  
3. クローンした開発環境下で作業  
4. 更新した内容をフォークしたリポジトリに commit  
5. fork したリポジトリからオリジナルへ pull request  

## バージョンチェック関連
・OpenCV のバージョン確認  
```
$ pkg-config --modversion opencv
```

## Emacs 関連

| コマンド               | 実行内容                   |
|------------------------|----------------------------|
| C-x 2                  | window の分割（縦に2分割） |
| C-x 3                  | window の分割（横に2分割） |
| C-x o                  | 分割したwindowの移動       |
| M-% <- Alt + Shift + % | 文字列の置換               |

・undo tree : `C-x-u`からの戻りたいところ選択。`C-D`で差分の表示。`C-P`で戻る？  

### package.elの使い方

| コマンド                  | 実行内容           |
|---------------------------|--------------------|
| M-x package-list-packages | パッケージ一覧表示 |
|                           |                    |

#### 一覧表示中の操作

| コマンド | 実行内容                             |
|----------|--------------------------------------|
| h        | help                                 |
| i        | インストールパッケージの選択         |
| u        | 選択の解除                           |
| x        | インストール/消去の実行              |
| d        | 消去するパッケージの選択             |
| q        | 終了                                 |
| U        | アップデート可能なパッケージを全選択 |

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

