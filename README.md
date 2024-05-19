# MobileRobot-Openloopcontrol
## Aim:

To develop a python control code to move the mobilerobot along the predefined path.

## Equipments Required:
1. RoboMaster EP core
2. Python 3.7

## Procedure

## Step1:
Define the predefined path Create a list or array to store the coordinates of the robot's predefined path. Each coordinate should represent a point along the path that the robot needs to follow.

## Step2:
Initialize the robot's starting position Set the robot's initial position to the first coordinate in the predefined path.

## Step3:
Move the robot along the path Loop through each coordinate in the predefined path, starting from the second coordinate. Calculate the distance and direction from the robot's current position to the next coordinate. Use appropriate robot control commands to move the robot towards the next coordinate. Repeat this process for each coordinate in the predefined path.

## Step4:
Check if the robot has reached the end of the path After completing the loop, compare the robot's final position with the last coordinate in the predefined path. If the two positions match or are within a certain threshold, the robot has successfully reached the end of the path. If not, modify the path or make other adjustments as needed.

## Step5:
End the program

Once the robot has reached the end of the path, stop the program or execute any additional tasks required. Print a message or perform any necessary cleanup steps before terminating the program.
## Program
```
from robomaster import robot
import time
from robomaster import camera

if __name__ == '__main__':
    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    ep_chassis = ep_robot.chassis
    ep_led = ep_robot.led
    ep_camera = ep_robot.camera

    print("Video streaming started.....")
    ep_camera.start_video_stream(display=True, resolution = camera.STREAM_360P)

    ep_chassis.move(x=2.5, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=255,b=255,effect="on")

    ep_chassis.move(x=0.5, y=0, z=80, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=100,b=0,effect="on")

    ep_chassis.move(x=1.0, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=150,g=150,b=150,effect="on")

    ep_chassis.move(x=0, y=-1.5, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=150,g=150,b=150,effect="on")

    ep_chassis.move(x=0, y=0, z=-118, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=150,g=150,b=150,effect="on")
    
    ep_chassis.move(x=-1.6, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=150,g=150,b=150,effect="on")
    
    ep_chassis.move(x=0, y=0, z=-45, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=150,g=150,b=150,effect="on")
    

    ep_chassis.move(x=0, y=1.5, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=150,g=150,b=150,effect="on")

    ep_chassis.move(x=2.1, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=150,g=150,b=150,effect="on")

    ep_chassis.move(x=0, y=0, z=84, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=150,g=150,b=150,effect="on")

    ep_chassis.move(x=0.6, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=150,g=150,b=150,effect="on")

    ep_chassis.move(x=0, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=150,g=150,b=150,effect="on")


    time.sleep(4)
    ep_camera.stop_video_stream()
    print("Stopped video streaming.....")

    ep_robot.close()


```

## MobileRobot Movement Image:

![robo](./img/robomaster.png)
![329312400-9fc25f41-1544-4407-b7f5-0098f18749e5](https://github.com/sowmya-badoni/mobilerobot-openloopcontrol/assets/152136324/15244536-9510-4d17-8414-1f32c7eae737)
![329313073-9bfb7e5b-3a10-4808-ae54-3732afc8ea20](https://github.com/sowmya-badoni/mobilerobot-openloopcontrol/assets/152136324/c879a777-b007-4ede-b978-31e8c2d56f61)
![329312954-ffd8c662-35ea-4a0d-9012-f8e3751f32c8](https://github.com/sowmya-badoni/mobilerobot-openloopcontrol/assets/152136324/62bf57fd-9e67-4524-8bb3-805428151bba)


## MobileRobot Movement Video:
## URL: https://youtu.be/NRl25ggT9eE?si=NyjbeHbuzBTqvv1E

## Result:
Thus the python program code is developed to move the mobilerobot in the predefined path.


```
Mobile Robotics Laboratory
SOWMYA BADONI (212223230211)
Department of Artificial Intelligence and Data Science
Saveetha Engineering College
```
