# Lab Dart03 : OOP ระบบจัดการสินค้า (Product Management System)

# ข้อกำหนดงาน
1) Class แม่: Product
ให้สร้างคลาส Product ที่มี
Properties
_id (String) → private
name (String) → public
price (double) → public (ห้ามเป็น null)
stock (int?) → nullable (อาจไม่ระบุสต็อกตอนแรกได้)
Constructor
ใช้ named parameters และ required สำหรับ id, name, price
Getter/Setter
getter: id เพื่ออ่าน _id
setter: price
ต้องมากกว่า 0 เท่านั้น ถ้าค่าไม่ถูกต้องให้ “ไม่เปลี่ยน” และพิมพ์เตือน
Methods
applyDiscount(double percent)
percent ต้องอยู่ระหว่าง 0–100 เท่านั้น
ลดราคาตามเปอร์เซ็นต์
restock(int amount)
ถ้า stock เป็น null ให้ถือว่าเริ่มจาก 0
เพิ่มจำนวนสินค้าเข้า stock
showInfo()
แสดงข้อมูลสินค้า
ถ้า stock เป็น null ให้แสดง “ยังไม่ระบุสต็อก”

2) Class ลูก: DigitalProduct (extends Product)
เพิ่ม property:
fileSizeMB (double) → required
override method:
showInfo() ให้แสดงเพิ่มว่าเป็น “สินค้าแบบดิจิทัล” และแสดง fileSizeMB

3) Class ลูก: FoodProduct (extends Product)
เพิ่ม property:
expireDate (String) → required (เช่น "2026-01-10")
override method:
showInfo() ให้แสดงเพิ่มว่าเป็น “สินค้าอาหาร” และแสดงวันหมดอายุ

4) Polymorphism
ใน main() ให้ทำ
สร้างสินค้าอย่างน้อย 3 ชิ้น (ต้องมีทั้ง Product, DigitalProduct, FoodProduct)
เก็บลง List<Product>
วนลูปเรียก showInfo() ของแต่ละชิ้น (ให้เห็นการ override ทำงาน)

ตัวอย่างพฤติกรรมที่ต้องทำได้
ลดราคา 10%
เพิ่มสต็อก +50
ทดลองตั้งราคาเป็นค่าติดลบแล้วต้อง “ถูกป้องกัน”
ถ้า stock ยังไม่กำหนด ให้แสดงข้อความแทน null

