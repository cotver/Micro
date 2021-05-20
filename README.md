# Micro
## 1. Update the Raspberry Pi
```bash
sudo apt-get update
sudo apt-get dist-upgrade
```
## 2. Setup Camera
```bash
sudo raspi-config
```
• เลือก 'Camera' option<br/>
• กดปุ่ม Enter key เพื่อ enable การใช้งาน<br/>
• เลือก “Finish”<br/>
• เลือก reboot your Raspberry Pi.<br/>
<br/>
ติดตังLibrary โดยใชคำสั่ง:
```bash
sudo apt-get install python-picamera
```

## 3. Install TensorFlow

```bash
pip3 install tensorflow

sudo apt-get install libatlas-base-dev

sudo pip3 install pillow lxml jupyter matplotlib cython
sudo apt-get install python-tk
```

## 4. Install OpenCV
```bash
sudo apt-get install libjpeg-dev libtiff5-dev libjasper-dev libpng12-dev
sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
sudo apt-get install libxvidcore-dev libx264-dev
sudo apt-get install qt4-dev-tools libatlas-base-dev

sudo pip3 install opencv-python
```

## 5. Compile and Install Protobuf
```bash
sudo apt-get install protobuf-compiler
```

## 6. Set up TensorFlow Directory Structure and PYTHONPATH Variable
