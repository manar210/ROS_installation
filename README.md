# ROS_installation
في هذا المشروع تم تثبيت نظام تشغيل الروبوت وتحميل باكيج الذراع الالية عليه

اولا تم تحميل وتثبيت نظام تشغيل الروبوت بالطريقة التاليه

first, download virtual box : https://www.virtualbox.org/wiki/Downloads
second, install ubuntu : https://releases.ubuntu.com/18.04/
then, to install ROZ the following commands were followed:

sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654

sudo apt-get update

sudo apt-get install ros-melodic-desktop-full

apt-cache search ros-melodic

echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
source ~/.bashrc

sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential

sudo apt install python-rosdep

sudo rosdep init

rosdep update

sudo apt-get install ros-noetic-catkin

mkdir -p ~/catkin_ws/src

cd ~/catkin_ws/

catkin_make

cd ~/catkin_ws/src

لتثبيت باكيج الذراع الالية 

git clone https://github.com/smart-methods/arduino_robot_arm.git 

cd ~/catkin_ws

rosdep install --from-paths src --ignore-src -r -y

sudo apt-get install ros-melodic-moveit

sudo apt-get install ros-melodic-joint-state-publisher ros-melodic-joint-state-publisher-gui

sudo apt-get install ros-melodic-gazebo-ros-control joint-state-publisher

sudo apt-get install ros-melodic-ros-controllers ros-melodic-ros-control

sudo nano ~/.bashrc

at the end of the (bashrc) file add the follwing line
(source /home/manar/catkin_ws/devel/setup.bash)
then 
ctrl + o

source ~/.bashrc

roslaunch robot_arm_pkg check_motors.launch

تم ارفاق صور للذراع الالية
