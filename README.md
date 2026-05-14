# AR Indoor Guide — ภาควิชาสุขวิทยาเขตร้อน
**อาคารตระหนักจิตร ชั้น 8–9**
คณะเวชศาสตร์เขตร้อน มหาวิทยาลัยมหิดล

---

## โครงสร้าง Folder

```
ar-tmhg/
│
├── index.html          ← แอป AR หลัก (เปิดบน browser มือถือ)
│
├── markers/            ← ไฟล์ marker pattern สำหรับพิมพ์ติดหน้าห้อง
│   ├── hiro.png           (ห้องประชุมชั้น 8)
│   ├── kanji.png          (ห้อง JK Commons ชั้น 9)
│   ├── letterA.png        (Co-working Space 1)
│   ├── letterB.png        (Co-working Space 2)
│   └── letterC.png        (ห้องหัวหน้าภาค)
│
├── assets/             ← รูปภาพ โลโก้ ที่ใช้ในแอป (ถ้ามี)
│
├── qr-prints/          ← ไฟล์พร้อมพิมพ์ติดหน้าห้อง
│
└── README.md           ← ไฟล์นี้
```

---

## วิธีใช้งาน

### 1. ทดสอบในเครื่อง (Local)
```bash
# ต้องใช้ local server (ไม่ใช่เปิดไฟล์ตรงๆ เพราะกล้องต้องการ HTTPS หรือ localhost)
cd ar-tmhg
python -m http.server 8080
# เปิด http://localhost:8080 ใน browser
```

### 2. Deploy บน GitHub Pages
```bash
git init
git add .
git commit -m "AR Indoor Guide v1"
git remote add origin https://github.com/YOUR_USERNAME/ar-tmhg.git
git push -u origin main
# เปิด Settings → Pages → Deploy from main branch
# URL: https://YOUR_USERNAME.github.io/ar-tmhg/
```

---

## Markers ที่ใช้ (AR.js Built-in)

| Marker  | ห้อง                    | ชั้น |
|---------|------------------------|------|
| Hiro    | ห้องประชุมชั้น 8       | 8    |
| Kanji   | ห้องประชุม JK Commons  | 9    |
| Letter A| Co-working Space 1     | 8    |
| Letter B| Co-working Space 2     | 9    |
| Letter C| ห้องหัวหน้าภาค         | 8    |

ดาวน์โหลด marker pattern จาก:
https://ar-js-org.github.io/AR.js/three.js/examples/marker-training/examples/

---

## แก้ไขข้อมูลห้อง

เปิดไฟล์ `index.html` แก้ที่ส่วน `const BUILDING = { ... }`
แต่ละห้องมีโครงสร้าง:
```js
{
  id: "f8-meeting",        // รหัสห้อง (ห้ามซ้ำ)
  name: "ห้องประชุมชั้น 8", // ชื่อแสดง
  icon: "🏛️",              // emoji
  color: "#ff6b35",        // สีธีม
  desc: "รายละเอียด...",   // คำอธิบาย (ใช้ \n ขึ้นบรรทัด)
  tags: ["ประชุม","20 คน"] // ป้ายกำกับ
}
```

---

## ต้องการความช่วยเหลือ

- ติดต่อทีม IT ภาควิชาสุขวิทยาเขตร้อน
- Repository: github.com/YOUR_USERNAME/ar-tmhg
