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
สร้างโฟลเดอร์ “tensorflow1” และ cd เข้าไป.
```bash
mkdir tensorflow1
cd tensorflow1
```
ดาวน์โหลด tensorflow repository จาก GitHub:
```bash
git clone --depth 1 https://github.com/tensorflow/models.git
```
เราจำเป็นต้องแก้ไข PYTHONPATH environment variable เพื่อชี้ไปที่ไดเรกทอรีบางรายการภายในที่เก็บ TensorFlow ที่เราเพิ่งดาวน์โหลด เราต้องการให้ตั้งค่า PYTHONPATH ทุกครั้งที่เปิดเทอร์มินัลดังนั้นเราจึงต้องแก้ไขไฟล์. bashrc เปิดโดย:
```bash
sudo nano ~/.bashrc
```
และในบรรทัดสุดท้ายให้เพิ่ม:
```bash
export PYTHONPATH=$PYTHONPATH:/home/pi/tensorflow1/models/research:/home/pi/tensorflow1/models/research/slim
```
เราจำเป็นต้องใช้ Protoc เพื่อคอมไพล์ไฟล์ Protocol Buffer (.proto) ที่ Object Detection API ใช้ไฟล์ .proto ที่อยู่ใน /research/object_detection/protos แต่เราจำเป็นต้องดำเนินการคำสั่งจากไดเร็กทอรี /research :
```bash
cd /home/pi/tensorflow1/models/research
protoc object_detection/protos/*.proto --python_out=.
```
จากนั้นย้ายไปที่ไดเร็กทอรี object_detection:
```bash
cd /home/pi/tensorflow1/models/research/object_detection
```
ดาวน์โหลดโมเดล SSDLite-MobileNet:
```bash
wget http://download.tensorflow.org/models/object_detection/ssdlite_mobilenet_v2_coco_2018_05_09.tar.gz
tar -xzvf ssdlite_mobilenet_v2_coco_2018_05_09.tar.gz
```
