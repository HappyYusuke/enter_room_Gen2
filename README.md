# enter_room_Gen2

# Overview
入室後の進行距離と速度を取得して、ドアが開いたら入室するサービスサーバー

:warning:これはシミュレータで動きます。実機ではcmdのトピック名を変えるか、以下リンクからcloneしてください
https://github.com/KIT-Happy-Robot/happymimi_apps/blob/develop/happymimi_teleop/src/enter_roomGen2.py



# Description
主な動作、機能は以下の通りです
* サーバーが準備できたら`Ready to set enter_room_server`と出力します
* 前に障害物があると、`Prease open the door`と出力します
* 入室後の**進行距離**と**速度**を指定できます
* 処理が完了すると`enter_room finish [distance:指定距離, velocity:指定速度]`と`True`を返します
* 完了しない場合はFalseを返します



# build enviroment
cloneしたらビルドしてください
```
catkin build
```



# Usage
競技用マスターからはサービスで立ち上げます
|Name|Communication|Type|Input|Output|
|----|----|----|----|----|
|/enter_room_server|Service|EnterRoomGen2|float32 `distance`,`velocity`|bool `result`|

使用している型は独自型srvなのでimportしてください

happymimi_teleop:
`from happymimi_teleop.srv import EnterRoomGen2`

enter_room_Gen2:
`from enter_room.srv import EnterRoomGen2`

ターミナルから呼び出す場合はサーバー立ち上げ後に以下のコマンドを入力してください
```
rosservice call /enter_room_server "distance: 0.0 velocity: 0.0"
```
