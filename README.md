# Parking Management System

ระบบจัดการลานจอดรถ (Parking Management System) พัฒนาด้วย PHP และ MySQL ระบบนี้ออกแบบมาเพื่อจัดการการจอดรถทั้งสำหรับผู้ใช้ทั่วไปและผู้ใช้แบบสมัครสมาชิก (Subscribers) โดยมีฟีเจอร์การจองที่จอดรถ การคำนวณค่าบริการอัตโนมัติ และระบบแอดมินสำหรับจัดการข้อมูลต่างๆ ในระบบ

## 🌟 คุณสมบัติเด่น (Features)

- **ระบบสมาชิก (User Authentication)**
  - สมัครสมาชิกและเข้าสู่ระบบ
  - แบ่งสิทธิ์การใช้งานระหว่างผู้ใช้ทั่วไป (User) และผู้ดูแลระบบ (Admin)
- **การจัดการลานจอดรถและโซน (Parking Zones & Spots)**
  - แบ่งโซนการจอดรถออกเป็นหลายโซน (เช่น Zone A, B, C, VIP)
  - แสดงสถานะช่องจอดรถว่า ว่าง (Free) หรือ ไม่ว่าง (Occupied)
- **ระบบการจองรถและบันทึกการเข้าจอด (Parking Records & Reservation)**
  - บันทึกข้อมูลป้ายทะเบียนรถ เวลาเข้า (Entry Time) และเวลาออก (Exit Time)
  - รองรับระบบการจองช่องจอดรถล่วงหน้า (Reservation)
- **ระบบคำนวณค่าบริการและการชำระเงิน (Fee Calculation & Payments)**
  - คำนวณค่าบริการอัตโนมัติตามระยะเวลาที่จอด
  - อัตราค่าบริการแตกต่างกันระหว่างผู้ใช้ทั่วไป (Normal) และผู้ใช้ที่สมัครแพ็กเกจ (Subscriber)
- **แพ็กเกจสมาชิก (Subscription Plans)**
  - รองรับการสมัครแพ็กเกจรายเดือนและรายปี เพื่อรับส่วนลดค่าบริการจอดรถ
- **ระบบจัดการสำหรับผู้ดูแลระบบ (Admin Dashboard)**
  - จัดการข้อมูลผู้ใช้งาน จัดการช่องจอดรถ และดูรายงานสรุปต่างๆ

## 🛠️ เทคโนโลยีที่ใช้ (Technologies Used)

- **Frontend:** HTML, CSS, JavaScript (Bootstrap framework)
- **Backend:** PHP 
- **Database:** MySQL (MariaDB)

## 📦 โครงสร้างฐานข้อมูล (Database Structure)

ระบบใช้ฐานข้อมูลชื่อ `parking_management1` ซึ่งประกอบด้วยตารางหลักๆ ดังนี้:
- `auth_users`: ข้อมูลการเข้าสู่ระบบและสิทธิ์การใช้งาน
- `user`, `user_types`: ข้อมูลส่วนตัวของผู้ใช้งานและประเภทผู้ใช้งาน
- `parking_zones`, `parking_spots`: ข้อมูลโซนและช่องจอดรถ
- `parking_records`: บันทึกการเข้าจอดรถและการจอง
- `subscription_plans`, `user_subscriptions`: ข้อมูลแพ็กเกจและการสมัครใช้งาน
- `payments`: ข้อมูลการชำระเงิน

## 🚀 การติดตั้งและใช้งาน (Installation & Setup)

1. **โคลนโปรเจกต์**
   ```bash
   git clone https://github.com/jayasianboyd/parking_system1.git
   cd parking_system1
   ```
2. **ตั้งค่าฐานข้อมูล**
   - เปิดโปรแกรมจำลองเซิร์ฟเวอร์ (เช่น XAMPP, MAMP, หรือ WAMP)
   - สร้างฐานข้อมูลใหม่ใน phpMyAdmin ชื่อ `parking_management1`
   - นำเข้าไฟล์ (Import) `parking_management1.sql` เข้าสู่ฐานข้อมูล
3. **กำหนดค่าการเชื่อมต่อฐานข้อมูล**
   - ตรวจสอบไฟล์ `config.php` และปรับตั้งค่าให้ตรงกับเซิร์ฟเวอร์ของคุณ:
     ```php
     $host = "localhost";
     $username = "root";
     $password = "";
     $database = "parking_management1";
     ```
4. **การรันโฮสต์โปรเจกต์**
   - นำโฟลเดอร์โปรเจกต์ไปไว้ใน `htdocs` (สำหรับ XAMPP) หรือ `www` (สำหรับ WAMP)
   - เปิดเบราว์เซอร์ไปที่ `http://localhost/parking_system1/`

### 🔑 บัญชีสำหรับการทดสอบ (Test Accounts)
- **Admin:** Username: `admin` / Password: *(กรุณาดูการตั้งค่ารหัสผ่านเริ่มต้นในฐานข้อมูล หรือสร้างใหม่ผ่านการสมัครสมาชิกระบบ)*
- **User:** Username: `usertest` หรือสมัครสมาชิกใหม่ผ่านหน้า `register.php`
