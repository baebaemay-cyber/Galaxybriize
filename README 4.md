# 2027 MKMA · เติมดาวในกาแลกซี

ไฟล์เดียว `index.html` ใช้บน GitHub Pages ได้เลย ไม่ต้อง build ไม่ต้องล็อกอินอะไร

## ขึ้น GitHub Pages
อัปโหลด `index.html` → Settings → Pages → Deploy from a branch → `main` / root

## วิธีทำงาน
- อ่าน certificate ด้วย OCR (Tesseract.js) ในเบราว์เซอร์ แล้วให้ตรวจ/แก้ข้อมูลก่อนกดยืนยัน
- ค่าเริ่มต้น (ยังไม่ตั้งค่า) ข้อมูลเก็บในเครื่องนั้น ๆ (localStorage) กาแลกซีรวมจะเห็นเฉพาะในเครื่องตัวเอง

## ให้กาแลกซีรวมเป็นของทุกคน (Firebase ฟรี)
1. https://console.firebase.google.com → สร้างโปรเจกต์ → Build → Firestore Database → Create (test mode)
2. Project settings → Your apps → เพิ่ม Web app → คัดลอก `apiKey` กับ `projectId`
3. เปิด `index.html` หา `const CFG={apiKey:"",projectId:""}` แล้วใส่ค่าสองตัวนั้น
4. ที่ Firestore → Rules ตั้งให้เขียน/อ่านคอลเลกชัน `galaxy` และ `certs` ได้:
```
rules_version = '2';
service cloud.firestore { match /databases/{db}/documents {
  match /{col}/{doc} { allow read, write: if col in ['galaxy','certs']; }
}}
```
หมายเหตุ: ใครก็เขียนได้ จึงเหมาะกับงานแฟนคลับเล็ก ๆ ไม่ใช่ระบบที่กันโกงได้
