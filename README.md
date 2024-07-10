# Flask Application สำหรับ Intent Classification และ Entity Recognition

โปรเจคนี้เป็นแอปพลิเคชัน Flask ที่ใช้สำหรับการจำแนกประเภทความต้องการ (Intent Classification) และการระบุชื่อเฉพาะที่สำคัญ (Entity Recognition)

![Untitled design](https://github.com/terkkyy/Find_Intent_Entity/assets/95850049/96653d1a-bc00-4231-b849-a5646d4affcb)

## การติดตั้งและการใช้งาน

1. **ติดตั้ง dependencies**

```bash
pip install flask transformers torch joblib pythainlp easynertag
```

2. **รันแอปพลิเคชัน**
```bash
python app.py
```

3. **การใช้งาน**

- เข้าถึงหน้าเว็บแอปพลิเคชันที่ URL: `http://localhost:5000/`
- เลือกคำถามที่ต้องการจากรายการหรือกรอกคำถามเองแล้วกดปุ่ม "Predict Intent" เพื่อทำนาย
- ระบบจะทำการจำแนกประเภทคำถาม (Intent) และแสดงผลลัพธ์ที่ได้
- ระบบยังทำการระบุชื่อเฉพาะที่สำคัญ (Entity) ในข้อความด้วย โดยการใช้กฎและเครื่องมือร่วมกับ EasyNERTag ในการช่วยหาแพทเทิร์นของ Entity

## โครงสร้างไฟล์

- `app.py`: ไฟล์หลักของแอปพลิเคชัน Flask
- `templates/index.html`: ไฟล์ HTML สำหรับเลยหน้าเว็บแอปพลิเคชัน
- `model/`: โฟลเดอร์เก็บโมเดลและข้อมูลที่ใช้ในการจำแนกประเภทคำถาม
- โดยสามารถดูวิธีการฝึกฝนโมเดลได้ที่ [Colab Intent Model](https://colab.research.google.com/drive/1vvMyEbNg8WHMJx4m2LogECqicaPUn4Ls?usp=sharing)

## ข้อกำหนดและเงื่อนไข

โปรเจคนี้ถูกพัฒนาขึ้นเพื่อการศึกษา สามารถนำไปปรับใช้หรือพัฒนาต่อยอมรับในข้อกำหนดของ [MIT License](./LICENSE)
```bash
Watcharin Khamkhotsoon, Flask Application for Intent Classification and Entity Recognition, 2024. GitHub repository: [Find_Intent_Entity.git](https://github.com/terkkyy/Find_Intent_Entity.git).
```
