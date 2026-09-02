# Array data structure :

### Array คืออะไร

คือโครงสร้างไว้จัดเก็บข้อมูลหลายๆชุดในรูปแบบที่เป็นลำดับ โดยตำแหน่งของข้อมูลในแต่ละชิ้นเรียกว่า ดัชนี (Index) หรือ key

ข้อดีของ Array 
- สามารถเข้าถึงข้อมูลได้โดยตรงผ่าน index 
- จัดการข้อมูลง่าย

```python
students_scores = [65,88,72,64,99]
print(students_scores[1])
```
### Array 2 มิติ
```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]
```

### Array ในเกม

- Grid ของ tactical RPG (เช่น Fire Emblem) มักเก็บเป็น 2D Array `Tile[,] grid`
- Inventory ที่มีช่องจำกัด เช่น `Item[] inventorySlots = new Item[20]`
- ค่าสถานะ/สกิลของตัวละครที่จำนวนคงที่

**ข้อจำกัดของ Array**
1. ขนาดคงที่
2. หน่วยความจำ

### อ้างอิง

- [expert programming tutor.com](https://expert-programming-tutor.com/tutorial/article/KE003256_Arrays_in_Data_Structures_-_What_is_an_Array.php)
- [microcontroller.com](https://www.123microcontroller.com/th/cpp-arrays-data-structure/)


# Queue & Stack data structure :

### Stack data structure คืออะไร

เป็น Linear data struture เป็นการจัดการข้อมูลแบบต่อเนื่องกัน และเข้าถึงข้อมูลตามลำดับ เป็นการจัดข้อมูลแบบ LIFO (Last in first out) ท้ายเข้าท้ายออกก่อน

มองเป็นภาพกล่องใส่ของที่เราวางลองทับลงไปเรื่อย ๆ แล้วเวลาเอาของออกก็ต้องเอาของด้านบานออกก่อน

![stack](/Research/animate/stack.gif)

**สรุป Stack**

- Stack ใช้ระบบ LIFO (Last-In-First-Out) ซึ่งหมายความว่าข้อมูลที่ถูกเพิ่มล่าสุดจะถูกนำออกก่อนข้อมูลที่เพิ่มมาก่อนหน้า
- Stack เต็มหรือไม่ Stack มี Pointer 1 ตัวที่ชี้ไปยังตัวบนสุดของ Stack เพื่อเข้าถึงข้อมูลบนสุด
- การเพิ่มและลบข้อมูลผ่านทางเดียวก็คือตัว top นั่นเอง
- มักใช้กับงานแบบ backtracking เช่น undo/redo functionality

### Queue data structure คืออะไร

เป็นอีก linear data struture เป็นการจัดการข้อมูลแบบต่อเนื่องกัน เป็นการจัดข้อมูลแบบ FIFO (First in First out) แรกเข้าแรกออก

เหมือนท่อส่งน้ำ น้ำเข้าจากบนสุด น้ำออกจากข้างล้าง

![Queue](/Research/animate/Queue.gif)

**สรุป Queue**

- Queue ใช้ระบบ FIFO (First-In-First-Out) ซึ่งหมายความว่าข้อมูลที่ถูกเพิ่มล่าสุดจะถูกใช้งานก่อนข้อมูลที่เพิ่มมาก่อนหน้า
- Queue มี Pointer 2 ตัว: ตัวหนึ่งชี้ไปที่ตัวหน้า (Front, Head) และตัวอีกตัวชี้ไปที่ตัวท้าย (Rear, Tail)
- การเพิ่มและลบข้อมูลข้อมูลคนละด้านโดยเพิ่มจะต้องนำข้อมูลไปต่อกับ rear และลบจะนำข้อมูลออกจาก front
- มักใช้กับการทำงานตามลำดับเช่น handling requests หรือ scheduling tasks

### อ้างอิง

- [borntodev.com](https://www.borntodev.com/2023/09/26/stack-%E0%B9%81%E0%B8%A5%E0%B8%B0-queue/)
- [expert programming](https://expert-programming-tutor.com/tutorial/article/KE003282_Stack_and_Queue_in_Data_Structures_-_What_is_a_Queue.php)
- [bing.com](https://www.bing.com/search?pglt=929&q=Queue+data+structure+คือ&cvid=2c95b28126e440eda911b735e8e841e7&gs_lcrp=EgRlZGdlKgYIABBFGDkyBggAEEUYOTIGCAEQABhAMgYIAhAAGEAyBggDEAAYQDIGCAQQABhAMgYIBRAAGEAyBggGEAAYQDIGCAcQABhAMgYICBAAGEAyBggJEAAYQNIBCDY5MTJqMGo3qAIAsAIA&FORM=ANNTA1&PC=ASTS)