# MindVibe - เว็บแอปพลิเคชันสำหรับเช่าชุด (dsi321)

**MindVibe** เป็นเว็บแอปพลิเคชันที่พัฒนาด้วย Django Framework สำหรับให้บริการเช่าชุดออนไลน์ ช่วยให้ผู้ใช้สามารถค้นหา เลือกดูรายละเอียด และเช่าชุดที่ต้องการได้อย่างสะดวกสบายผ่านเว็บไซต์

---

## 1. บทคัดย่อ (Abstract)

ผีเสื้อ 🦋 สัญลักษณ์สากลของการเปลี่ยนแปลงและการเติบโต จากดักแด้สู่ปีกอันงดงาม เปรียบได้กับการเปลี่ยนผ่านของอุตสาหกรรมแฟชั่น จากวัฏจักรที่รวดเร็วของ Fast Fashion สู่แนวคิด **Sustainable Fashion** และ **Circular Fashion** ที่ยั่งยืนกว่า

**MindVibe** ถือกำเนิดขึ้นจากแรงบันดาลใจนี้ เราเชื่อว่าการเปลี่ยนแปลงเล็กๆ เหมือนการขยับปีกของผีเสื้อ สามารถสร้างผลกระทบที่ยิ่งใหญ่ได้ แอปพลิเคชันเช่าชุดออนไลน์นี้จึงเป็นทางเลือกที่สนับสนุนแฟชั่นหมุนเวียน 🌱 ช่วยให้ผู้ใช้ได้สวมใส่ชุดสวยหลากหลายสไตล์สำหรับทุกโอกาส โดยไม่ต้องเพิ่มภาระให้ตู้เสื้อผ้าหรือโลกของเรา 🌏

MindVibe มอบประสบการณ์การเช่าชุดที่ครบวงจร ตั้งแต่การค้นหา เลือกดูรายละเอียดชุด จัดการตะกร้าสินค้า สร้างคำสั่งเช่า แจ้งชำระเงิน ติดตามสถานะ และแจ้งคืนสินค้า ระบบใช้งานง่าย พัฒนาด้วยเทคโนโลยี Django, PostgreSQL และ Docker เพื่อความสะดวกในการใช้งานและพัฒนาต่อยอด เรามุ่งหวังให้ MindVibe เป็นส่วนหนึ่งในการขับเคลื่อนการเปลี่ยนแปลงสู่แฟชั่นที่รับผิดชอบและยั่งยืน เหมือนดั่งผีเสื้อที่โบยบินอย่างอิสระและสมดุลกับธรรมชาติ 💚♻️

---

## 2. User Stories (ลักษณะการใช้งาน)

User Stories ต่อไปนี้อธิบายถึงความต้องการและลักษณะการใช้งานหลักของผู้ใช้ระบบ MindVibe:

1.  **ในฐานะผู้เข้าชมทั่วไป (Guest User)** ฉันต้องการ `เรียกดูรายการชุดทั้งหมด` และ `ดูรายละเอียดของชุดแต่ละชุด` (เช่น รูปภาพ, คำอธิบาย, ราคาเช่าต่อวัน) เพื่อตัดสินใจว่าจะเช่าชุดไหนดี
2.  **ในฐานะผู้ใช้ที่ยังไม่ได้สมัครสมาชิก** ฉันต้องการ `สมัครสมาชิกใหม่` ด้วยชื่อผู้ใช้และอีเมล เพื่อสร้างบัญชีสำหรับเข้าใช้งานระบบเช่าชุด
3.  **ในฐานะผู้ใช้ที่ลงทะเบียนแล้ว (Registered User)** ฉันต้องการ `เข้าสู่ระบบ (Login)` ด้วยชื่อผู้ใช้และรหัสผ่าน เพื่อเข้าถึงฟังก์ชันสำหรับสมาชิก เช่น การเช่าชุด การดูประวัติ
4.  **ในฐานะผู้ใช้ที่ลงทะเบียนแล้ว** ฉันต้องการ `เพิ่มชุดที่สนใจลงในตะกร้าสินค้า` เพื่อรวบรวมชุดที่ต้องการเช่าไว้ในที่เดียว
5.  **ในฐานะผู้ใช้ที่ลงทะเบียนแล้ว** ฉันต้องการ `ดูรายการสินค้าในตะกร้า` และ `ลบสินค้าที่ไม่ต้องการออกจากตะกร้า` เพื่อจัดการรายการเช่าก่อนดำเนินการต่อ
6.  **ในฐานะผู้ใช้ที่ลงทะเบียนแล้ว** ฉันต้องการ `ดำเนินการเช่า (Checkout)` โดยกรอกข้อมูลติดต่อ ที่อยู่จัดส่ง และ `ระบุวันที่ต้องการเริ่มเช่าและวันที่ต้องการคืน` เพื่อสร้างคำสั่งเช่า
7.  **ในฐานะผู้ใช้ที่สร้างคำสั่งเช่าแล้ว** ฉันต้องการ `ดูรายละเอียดข้อมูลการชำระเงิน (บัญชีธนาคาร, QR Code)` และ `แจ้งการชำระเงิน` โดยกรอกวันเวลาที่โอนและแนบสลิป เพื่อให้ผู้ดูแลระบบตรวจสอบ
8.  **ในฐานะผู้ใช้ที่ลงทะเบียนแล้ว** ฉันต้องการ `ดูประวัติคำสั่งเช่าทั้งหมดของฉัน` พร้อมสถานะล่าสุด เพื่อติดตามการเช่าที่ผ่านมาและปัจจุบัน
9.  **ในฐานะผู้ใช้ที่เช่าชุดอยู่** ฉันต้องการ `แจ้งการส่งคืนสินค้า` โดยกรอกเลขพัสดุและแนบรูปสลิปการส่งคืน เพื่อให้ผู้ดูแลระบบทราบว่าสินค้ากำลังถูกส่งกลับ
10. **ในฐานะผู้ใช้ที่ลงทะเบียนแล้ว** ฉันต้องการ `แก้ไขข้อมูลโปรไฟล์ส่วนตัว` (เช่น ชื่อ, นามสกุล, อีเมล, เบอร์โทร, ที่อยู่) เพื่อให้ข้อมูลเป็นปัจจุบัน

---

## 3. ขั้นตอนการใช้งานตาม User Stories

ต่อไปนี้เป็นขั้นตอนการใช้งานฟังก์ชันหลักตาม User Stories:

**3.1 การสมัครสมาชิกและเข้าสู่ระบบ:**

1.  ไปที่หน้าแรกของ MindVibe
2.  คลิกที่ลิงก์ "สมัครสมาชิก" บนแถบนำทาง (Navigation bar)
3.  กรอกชื่อผู้ใช้ (Username), อีเมล (Email), และรหัสผ่าน (Password) ตามที่กำหนด จากนั้นคลิก "สมัครสมาชิก"
4.  ระบบจะสร้างบัญชีและนำคุณเข้าสู่ระบบ (หรือไปยังหน้า Profile/Home)
5.  สำหรับการเข้าสู่ระบบครั้งถัดไป ให้คลิก "เข้าสู่ระบบ" กรอกชื่อผู้ใช้และรหัสผ่าน แล้วคลิก "เข้าสู่ระบบ"

**3.2 การเลือกดูและเพิ่มชุดลงตะกร้า:**

1.  ไปที่หน้า "ชุดทั้งหมด" หรือเลือกดูตาม "หมวดหมู่" จากหน้าแรกหรือแถบนำทาง
2.  เรียกดูชุดต่างๆ ที่แสดงผล คลิกที่รูปภาพหรือชื่อชุดเพื่อดูรายละเอียดเพิ่มเติม (ราคา, คำอธิบาย)
3.  เมื่อเจอชุดที่ต้องการ ให้คลิกปุ่ม "เพิ่มลงตะกร้า" (ระบบจะเพิ่มชุดนั้น 1 ชิ้นลงในตะกร้า)
4.  ทำซ้ำขั้นตอนที่ 2-3 สำหรับชุดอื่นๆ ที่ต้องการ
5.  คลิกไอคอน "ตะกร้า" บนแถบนำทางเพื่อดูรายการชุดที่เลือกไว้

**3.3 การจัดการตะกร้าสินค้า:**

1.  ไปที่หน้า "ตะกร้าสินค้า"
2.  ตรวจสอบรายการชุด ราคาต่อวัน และยอดรวมต่อวัน
3.  หากต้องการลบชุดไหนออกจากตะกร้า ให้คลิกปุ่ม "ลบ" ที่อยู่ท้ายรายการนั้น
4.  เมื่อพอใจกับรายการในตะกร้าแล้ว คลิกปุ่ม "ดำเนินการต่อ" เพื่อไปยังหน้า Checkout

**3.4 การดำเนินการเช่า (Checkout):**

1.  ในหน้า Checkout ระบบอาจดึงข้อมูลบางส่วน (ชื่อ, อีเมล) มาจากโปรไฟล์ของคุณ (หากเคยกรอกไว้)
2.  กรอกข้อมูลที่จำเป็นให้ครบถ้วน: ชื่อจริง, นามสกุล, อีเมล, เบอร์โทรศัพท์, ที่อยู่สำหรับจัดส่ง
3.  **สำคัญ:** เลือก "วันที่เริ่มเช่า" และ "วันที่คืน" ที่ต้องการ ระบบจะคำนวณจำนวนวันเช่าให้โดยอัตโนมัติ
4.  ตรวจสอบข้อมูลทั้งหมดอีกครั้ง จากนั้นคลิก "ยืนยันและดำเนินการต่อ"

**3.5 การแจ้งชำระเงิน:**

1.  หลังจาก Checkout สำเร็จ ระบบจะแสดงหน้ารายละเอียดคำสั่งเช่า หรือนำไปยังหน้าแจ้งชำระเงิน (อาจต้องคลิกปุ่ม "แจ้งชำระเงิน" จากหน้ารายละเอียดคำสั่งเช่าหรือประวัติการเช่า หากยังไม่ได้แจ้ง)
2.  ในหน้าแจ้งชำระเงิน คุณจะเห็นข้อมูลบัญชีสำหรับโอนเงิน (ชื่อบัญชี, เลขที่บัญชี, ธนาคาร, QR Code) และยอดรวมที่ต้องชำระ
3.  ทำการโอนเงินตามยอดที่ระบุ
4.  กลับมาที่หน้าแจ้งชำระเงิน กรอก "วันที่และเวลาโอนเงิน" ให้ตรงกับในสลิป
5.  คลิกปุ่ม "Choose File" หรือ "Browse" เพื่อเลือก "ไฟล์สลิปโอนเงิน" จากอุปกรณ์ของคุณ
6.  คลิก "ยืนยันการแจ้งชำระเงิน"
7.  สถานะคำสั่งเช่าจะเปลี่ยนเป็น "รอตรวจสอบสลิป"

**3.6 การตรวจสอบประวัติและสถานะ:**

1.  ล็อกอินเข้าสู่ระบบ
2.  คลิกที่ลิงก์ "ประวัติการเช่า" บนแถบนำทาง
3.  คุณจะเห็นรายการคำสั่งเช่าทั้งหมด พร้อมสถานะล่าสุด (เช่น รอชำระเงิน, กำลังดำเนินการ, จัดส่งแล้ว, กำลังเช่า, ได้รับคืนแล้ว ฯลฯ)
4.  คลิก "ดูรายละเอียด" เพื่อดูข้อมูลเพิ่มเติมของแต่ละคำสั่งเช่า

**3.7 การแจ้งส่งคืนสินค้า:**

1.  ไปที่ "ประวัติการเช่า" และคลิก "ดูรายละเอียด" ของคำสั่งเช่าที่ต้องการแจ้งคืน (สถานะควรเป็น "กำลังเช่า" หรือ "จัดส่งแล้ว")
2.  ในหน้ารายละเอียดคำสั่งเช่า คลิกปุ่ม "แจ้งส่งคืนสินค้า"
3.  กรอก "เลขพัสดุส่งคืน" ที่คุณได้รับจากบริษัทขนส่ง
4.  แนบ "รูปถ่ายพัสดุ" หรือ "สลิปการส่งคืน"
5.  คลิก "ยืนยันการแจ้งส่งคืน"
6.  สถานะคำสั่งเช่าจะเปลี่ยนเป็น "ลูกค้าส่งคืนแล้ว"

---

## 4. การติดตั้งและใช้งาน (Installation and Usage)

**Prerequisites:**

* **Docker:** [ติดตั้ง Docker](https://docs.docker.com/get-docker/)
* **Docker Compose:** [ติดตั้ง Docker Compose](https://docs.docker.com/compose/install/) (มักจะมาพร้อมกับ Docker Desktop)

**ขั้นตอนการติดตั้ง:**

1.  **Clone Repository:**
    ```bash
    git clone <your-repository-url> # แทน <your-repository-url> ด้วย URL ของ repo คุณ
    cd dsi321 # หรือชื่อโฟลเดอร์โปรเจกต์ของคุณ
    ```

2.  **สร้างไฟล์ Environment Variables (`.env`):**
    สร้างไฟล์ชื่อ `.env` ใน root directory ของโปรเจกต์ และใส่ค่าตัวแปรที่จำเป็น (ดูตัวอย่างจาก `settings.py` และ `docker-compose.yml`):
    ```dotenv
    # .env Example
    SECRET_KEY=your_strong_django_secret_key_here # เปลี่ยนเป็น Secret Key ของคุณ
    DEBUG=1 # ตั้งเป็น 1 สำหรับ Development, 0 สำหรับ Production
    DJANGO_ALLOWED_HOSTS=localhost,127.0.0.1 # เพิ่ม Host อื่นๆ ถ้าจำเป็น

    # Database (ใช้ค่าเดียวกับใน docker-compose.yml หรือเปลี่ยนตามต้องการ)
    POSTGRES_DB=mindvibe_db
    POSTGRES_USER=mindvibe_user
    POSTGRES_PASSWORD=your_strong_password # ตั้งรหัสผ่านที่ปลอดภัย
    DATABASE_URL=postgres://mindvibe_user:your_strong_password@db:5432/mindvibe_db # ตรวจสอบว่าตรงกับด้านบน

    # Email Settings (สำหรับ Password Reset) - ใช้ Gmail เป็นตัวอย่าง
    EMAIL_BACKEND=django.core.mail.backends.smtp.EmailBackend
    EMAIL_HOST=smtp.gmail.com
    EMAIL_PORT=587
    EMAIL_USE_TLS=True
    EMAIL_HOST_USER=your_email@gmail.com # ใส่อีเมลของคุณ
    EMAIL_HOST_PASSWORD=your_gmail_app_password # ใส่ App Password ที่สร้างจาก Google Account

    # Bank Account Details (สำหรับแสดงในหน้า Payment)
    BANK_ACCOUNT_NAME=ชื่อบัญชี ธนาคาร
    BANK_ACCOUNT_NUMBER=เลขที่บัญชี
    BANK_NAME=ชื่อธนาคาร
    BANK_QR_CODE_STATIC_PATH=outfits/images/my_qr.jpg # path ไปยังไฟล์ QR Code ใน static files
    ```
    * **หมายเหตุ:** สำหรับ `EMAIL_HOST_PASSWORD` หากใช้ Gmail ต้องไปสร้าง "App Password" ใน Google Account ของคุณ (ต้องเปิด 2-Step Verification ก่อน) อย่าใช้รหัสผ่าน Gmail ปกติ

3.  **Build และ Run Docker Containers:**
    เปิด Terminal หรือ Command Prompt ใน root directory ของโปรเจกต์ แล้วรันคำสั่ง:
    ```bash
    docker-compose up --build -d
    ```
    * `--build` เพื่อสร้าง image ใหม่ (จำเป็นในครั้งแรก หรือเมื่อมีการเปลี่ยนแปลง Dockerfile/requirements)
    * `-d` เพื่อรันใน background (detach mode)

4.  **Apply Database Migrations:**
    รอให้ container `db` และ `web` เริ่มทำงานสักครู่ จากนั้นรันคำสั่ง:
    ```bash
    docker-compose exec web python manage.py migrate
    ```

5.  **Create Superuser (Admin Account):**
    สร้างบัญชีผู้ดูแลระบบเพื่อเข้าหน้า Admin (/admin/):
    ```bash
    docker-compose exec web python manage.py createsuperuser
    ```
    ทำตามขั้นตอนเพื่อตั้งชื่อผู้ใช้, อีเมล, และรหัสผ่าน

6.  **Collect Static Files (สำหรับ Production):**
    (ไม่จำเป็นสำหรับ Development ถ้า `DEBUG=1`)
    ```bash
    docker-compose exec web python manage.py collectstatic --noinput
    ```

7.  **Access the Application:**
    เปิดเว็บเบราว์เซอร์แล้วไปที่:
    * **หน้าหลัก:** `http://localhost:8000`
    * **หน้า Admin:** `http://localhost:8000/admin/` (ล็อกอินด้วย Superuser ที่สร้างไว้)

**การหยุดการทำงาน:**

```bash
docker-compose down