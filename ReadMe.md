실행방법
========

**1. roscore을 구동시킬 PC에서 rosbridge_websocket과 tf2_web_republisher을 실행한다**
---------------------------------------------------------------------------------
> 이 PC의 IP를 a.a.a.a라고 하자   

roslaunch rosbridge_server rosbridge_websocket.launch   
rosrun tf2_web_republisher tf2_web_republisher   
* 연구실의 desktop PC의 경우 alias bridge 및 rosbridge_websocket.launch를 수정해놓았기 때문에 bridge만 입력해도 된다   


**2. turtlebot에 ssh로 접속하여 turtlebot3_bringup과 rs_camera, slam을 실행한다**
---------------------------------------------------------------------
> 이 때 turtlebot의 MASTER_URI가 a.a.a.a여야 한다   

roslaunch turtlebot3_bringup turtlebot3_robot.launch   
roslaunch realsense2_camera rs_camera.launch   
roslaunch turtlebot3_slam turtlebot3_slam.launch   
* 연구실의 turtlebot의 경우 pi@192.168.0.39로 접속하고 비밀번호는 turtlebot이며 alias로 bringup과 rscam, slam만 입력해도 된다


**3. GUI를 실행시킬 PC에서 my_turtlebot3_bridge를 실행한다**
--------------------------------------------------------
> 이 때 my_turtlebot3_bridge.py의 client = roslibpy.Ros(host='a.a.a.a', port=9090)여야 한다   

rosrun my_turtlebot3 my_turtlebot3_bridge.py
