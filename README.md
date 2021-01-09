# robosys-kadai2-pkg
## ロボシス2020年の課題2
## 説明
- このプログラムはROSを学ぶために作られたものです。
- パブリッシャ側はx,y,z軸を選び、点を移動させる距離を決めるプログラムです。
- サブスクライバ側はパブリッシャから受け取ったデータをもとに点を移動させ、その座標を描画するプログラムです。
## 準備(ワークスペースがある前提)
1. ```cd ~/catkin_ws/src/```でディレクトリの移動します。
2. ```git clone https://github.com/kataoka0824/robosys-kadai2-pkg```でパッケージの取得します。
3. ```(cd ~/catkin_ws/src && catkin_make)```を実行します。
## 使い方
### rosrunで実行する場合
1. 端末1で```roscore```を実行します。
2. 端末2で```rosrun robosys-kadai2-pkg pub.py```を実行し、プログラムを開きます。
3. 端末3で```rosrun robosys-kadai2-pkg sub.py```を実行し、プロクラムを開きます。
4. 2で開かれたウィンドウの左の空欄にx,y,zのどれか、右の空欄に距離を入力し,送信ボタンを押します。
5. グラフが描画されます。赤点が原点、水色点が現在の座標、青点が過去の座標となっています。

*補足：サブスクライバでグラフの表示と同時にターミナルで座標と受け取ったデータが確認できます。*
### launchで実行する場合
1. 端末1でroscoreの実行をします。
2. 端末2で```roslaunch robosys-kadai2-pkg pub_sub.launch```を実行し、プログラムを開きます。
3. 上の4.5と同じ操作を行います。

*注意点：launchで開いた場合ターミナルにサブスクライバの受け取ったデータは表示されません。*
### 閉じる際
　Ctrl-cで切ることができます。

## 動作の様子
  https://youtu.be/PaRDqg_M27w
## 動作環境
- Ubuntu18.04(ノートPC)
- ROS(melodic)
- python3
- 主なモジュール
  - tkinter
  - rospy
  - sys
  - matplotlib.pyplot
## 問題点
- パブリッシャ、サブスクライバの順でプログラムを開かなければ動きませんでした。
- サブスクライバ側のグラフでしばらくたつと反応しなくなります。
## ノード
![robosys-kadai2](https://user-images.githubusercontent.com/50820783/103738987-40c56100-5038-11eb-814b-8962e996952b.png)
>/pub_node、/sub_nodeはそれぞれパブリッシャ、サブスクライバのノードです。  
/pub_keyがx,y,zの文字データ、/pub_distが距離データになります。

