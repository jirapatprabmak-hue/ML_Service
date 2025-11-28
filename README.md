# ML Deployment Service (Flask + Docker)

โปรเจกต์นี้เป็นการนำ Machine Learning Model มาทำเป็น Web Service API โดยใช้ Flask และจำลองสภาพแวดล้อมด้วย Docker

## Prerequisites
ต้องติดตั้ง Docker Desktop ในเครื่องก่อนเริ่มใช้งาน

## How to Build & Run

### Build Docker Image
เปิด Terminal หรือ Command Prompt ในโฟลเดอร์โปรเจกต์ แล้วรันคำสั่ง:

```bash
docker build -t ds-ml-service . 
```

### Run Docker Container
เมื่อ Build เสร็จแล้วให้รันด้วยคำสั่ง
```bash
docker run --rm -p 5000:5000 ds-ml-service 
```
## How To Test

### วิธีที่ 1: ผ่าน Docker Desktop (ง่ายที่สุด)
1. เปิดโปรแกรม Docker Desktop
2. ไปที่เมนู Containers
3. มองหา Container ชื่อ `ds-ml-service`
4. คลิกที่ลิงก์ในคอลัมน์ Port (5000:5000)
5. Web Browser จะเปิดหน้าเว็บขึ้นมาให้ทดลองกรอกข้อมูลทันที

### วิธีที่ 2: ผ่าน API (PowerShell) เปิด Terminal ใหม่ (อย่าปิดหน้าต่างที่รัน Docker) แล้วใช้คำสั่ง:
```Powershell
Invoke-WebRequest -Uri "http://127.0.0.1:5000/predict" `
  -Method POST `
  -Body '{"features":[8.3,25.0,6.0,1.0,1200,3.0,34.2,-118.3]}' `
  -ContentType "application/json"
  ```

