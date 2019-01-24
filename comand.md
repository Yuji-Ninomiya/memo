# コマンド備忘録

## Terminal操作関連
・カレントディレクトリ以下に hogehoge の記述があるか探す。  
```
$ grep -r hogehoge
```

## バージョンチェック関連
・OpenCV のバージョン確認  
```
$ pkg-config --modversion opencv
```
・PCLのバージョン
```
$ cd ~/catkin_ws/devel/lib/<package_name>/
$ ldd <package_name> | grep -e "pcl"
```
とすると、使用されている PCL のパッケージとそのバージョンが表示され、それがどこに置かれているか表示される。（<package_name> はコンパイルされたやつ）

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


