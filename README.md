# Install PX4-Autopilot
```
git clone https://github.com/PX4/PX4-Autopilot.git --recursive
cd PX4-Autopilot
sudo apt-get install python3-pip
sudo apt-get install libgstreamer-plugins-base1.0-dev
bash ./Tools/setup/ubuntu.sh –no-sim-tools –no-nuttx
sudo reboot now
```
- This procedure will take 20 mins
- It will usually stuck at nuxx, but it will sort out everything
- If there is something wrong, run this. Notice that, there should be no space and none ascii code character in your path
```
git checkout v1.13.2
make distclean
git submodule update –-recursive
```

# Run PX4-GAZEBO
```
make px4_sitl gazebo
```
It takes more than 10 mins, be patient
- If there is some error occured, it may because of some packets don't match
Try this:
```
sudo apt install ant
sudo apt upgrade libignition-math2
```

# Install ROS melodic
```
sudo apt-get install ros-melodic-mavros ros-melodic-mavros-extras
wget https://raw.githubusercontent.com/mavlink/mavros/master/mavros/scripts/install_geographiclib_datasets.sh
sudo bash ./install_geographiclib_datasets.sh
```

# Install QGround Control
```
sudo usermod -a -G dialout $USER
sudo apt-get remove modemmanager -y
sudo apt install gstreamer1.0-plugins-bad gstreamer1.0-libav gstreamer1.0-gl -y
sudo apt install libqt5gui5 -y
sudo apt install libfuse2 -y
```
After this restart your machine
Then:
```
wget https://d176tv9ibo4jno.cloudfront.net/latest/QGroundControl.AppImage
chmod +x ./QGroundControl.AppImage
./QGroundControl.AppImage
```
