# enter_room_Gen2

:warning:これはシミュレータで動きます。実機ではcmdのトピック名を変えてください

# Description
入室後の進行距離と速度を指定して、ドアが開いたら入室するパッケージ

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
