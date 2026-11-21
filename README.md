# 2027 MKMA · เติมดาวในกาแลกซี

หน้าเว็บไฟล์เดียว (`index.html`) ไม่ต้อง build

## วิธีขึ้น GitHub Pages
1. สร้าง repo ใหม่ แล้วอัปโหลด `index.html` และ `README.md`
2. ไปที่ Settings → Pages → เลือก Deploy from a branch → branch `main` / folder `/ (root)` → Save
3. รอสักครู่ จะได้ลิงก์ `https://<username>.github.io/<repo>/`

## สิ่งที่ใช้ได้บน GitHub Pages
- หน้าแรก ช่องกรอกชื่อทวิต ปุ่มและภาพขั้นตอนต่าง ๆ
- ดาวน์โหลดรูปกาแลกซีเป็น PNG

## สิ่งที่ยังใช้ไม่ได้บน GitHub Pages
เวอร์ชันนี้ถูกสร้างให้ทำงานบน claude.ai จึงพึ่งความสามารถ 2 อย่างที่ GitHub Pages ไม่มี:
- **ฐานข้อมูลร่วม** (`db`) เก็บกาแลกซีของแต่ละชื่อทวิตและเลข certificate กันซ้ำ
- **อ่านรูป certificate** (`sample`) ให้ Claude อ่านเลขใบ จำนวนโหวต วันและเวลา

หากต้องการให้ครบบน GitHub Pages ต้องเพิ่ม backend เอง เช่น Supabase/Firebase สำหรับเก็บข้อมูล และ API อ่านรูป (ซ่อน API key ไว้ฝั่งเซิร์ฟเวอร์ ห้ามใส่ใน index.html)
