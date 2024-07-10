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

## ชุดข้อมูล (Dataset)

โปรเจคนี้ใช้ชุดข้อมูลที่เกี่ยวข้องกับการจำแนกประเภทความต้องการ (Intent) ซึ่งประกอบไปด้วยคำถามที่รวบรวมจากโรงงานอาหารสัตว์บกปักธงชัย (CPF)
โดยทำการ labal ประโยคประเป็นประเภทต่างๆ

```bash
data = {
    "question": [
        "พัดลมคูลเลอร์หน้าจอปกติ แต่หน้างานจริงไม่ทำงาน เบรคเกอร์ เปิด ปกติ",
        "รบกวนสอบถามไลน์ Meal Silo “Job Setting> Bin Ident Meal Silo”จากการใช้งานพึงกลับมาจับได้ 3 วัน ทางคลังเลือก ให้ใช้งาน 2 ถัง M105/M110 ตึก 1 ลากไลน์ Meal Down TR9 M110 อยู่ แต่ ตึก 2 จะลากไลน์ MealUp TR9 M105 “แต่ job วิ่งไปจับถัง M110 ครับ  โปรแกรมได้จัด Prioiy ไว้ไหมครับ",
        "ใบเชนติดตะแกลงเครื่องอัดเม็ด",
        "น็อตขาด",
        "ค่าอุณหภูมิเครื่องคอนค้าง ไม่อัพเดต",
        "temp cooler สูงกว่าปกติ",
        "เครื่องปั้มเม็ดสอง มีรอยเหล็กลงลูกกลิ้ง นอตขาด1 ดรายมีลูกเหล็ก ลูกกลิ้งปกติ น็อตครบ",
        "stream ตก",
        "น็อตลงดราย",
        "ตะแกลงร่อนขาด ชั้นกลางฝั่ง boiler",
        "ไลน์สอง แม่เหล็ก ลงคอน หลุด"
    ],
    "Intent": [
        "Report_cooler",
        "Report_Silo",
        "Report_Pellet",
        "Report_Nott",
        "Report_Conditioner",
        "Report_cooler",
        "Report_Pellet",
        "Report_Steam",
        "Report_Nott",
        "Report_Boiler",
        "Report_Conditioner"
    ]
}

```


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
