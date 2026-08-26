# Recursion Algorithm :

### Recursion Algorithm คืออะไร

Recursion Algorithm คือฟังก์ชันหรืออัลกิริทึม ที่เรียกใช้งานตัวเองโดนการแบ่งให้ปัญหาใหญ่กลายเป็นปัญหาย่อยๆ
 จนไปถึงจุดที่แก้ปัญหาได้ง่ายที่สุด

Recursion Algorithm จะมีสองส่วนหลักๆที่ต้องดู
1. **Base case (เงื่อนไขหยุด) <br>**
&emsp;คือจุดที่ Recrusive algorithm หยุดเรียกตัวเอง
2. **Recrusive Case (เรียกตัวเอง)<br>**
&emsp;เป็นส่วนที่ Algorithm เรียกตัวเองไปเรื่อยๆจนกว่าจะเจอ Base case

ตัวอย่างของการใช้ Recursive Algorithm (คำนวณ Factorial)

> 5! = 5 * 4 * 3 * 2 * 1

คำนวณแบบ Recursive(Python)

```python
def factorial(n): 
    if n <= 1:  
        return 1
    else : 
        return n * factorial(n-1)
 
print(factorial(5)) 
```

จากโค้ดที่เห็น factorial(n) จะเรียกตัวเองซ้ำๆ จรกว่าค่า n จะเท่ากับจำนวณ n * factorial(n-1)

ทุกครั้งที่ฟังก์ชันเรียกตัวเอง ระบบจะ push ข้อมูลลงใน Call Stack และเมื่อถึง base case จะเริ่ม pop ค่ากลับออกมาตามลำดับย้อนกลับ (LIFO)

การใช้ Recursive algorithm 
เหมาะหรือดีสำหรับปัญหาที่มีโครงสร้างแบบซ้ำซ้อนหรือย่อยเป็นรูปแบบเดียวกันได้ 

- เหมาะอย่างยิ่งกับการค้นหาหรือท่องเข้าไปในโครงสร้างข้อมูลประเภท Binary Search Tree, โครงสร้างไฟล์ไดเรกทอรี 
- ปัญหาที่สามารถแบ่งออกเป็นปัญหาย่อย แล้วนำคำตอบมารวมกัน
- งานประเภทค้นหาคำตอบแบบถอยหลังกลับ แบบการแก้โจทย์เขาวงกต , หมากรุก,Sudoku


### อ้างอิง

- [learn algorithm.com](https://learnalgorithm.com/simply-explained/recursion/)
- [expert programming.com](https://expert-programming-tutor.com/tutorial/article/-KE001111_What_is_recursion_How_useful_is_it_When_you_use_it_the_easiest_explanation.php)
- [expert programing tutor.com](https://expert-programming-tutor.com/tutorial/article/KE003204_Computer_Science_that_you_should_know_-_Using_Recursive_Algorithms_to_solve_problems.php)
# 
# Sorting Algorithm :

### Recursion Algorithm คืออะไร

คือ ชุดขั้นตอนทางคอมพิวเตอร์ที่ใช้จัดลำดับสมาชิกในชุดข้อมูล เช่นพวก Array หรือ List

### Sorting algorithmsแบ่งเป็นสองประเภทคือ

1. **Comparison-based sorting algorithms** <br>
&emsp;เปรียบเทียบข้อมูลเพื่อกำหนดลำดับที่สัมพันธ์กัน เช่น bubble sort, insertion sort, selection sort, merge sort, quicksort, heapsort

2. **Non-comparison-based sorting algorithms** <br>
&emsp;ไม่ใช้การเปรียบเทียบเพื่อกำหนดลำดับของข้อมูล แต่ใช้ประโยชน์จากคุณสมบัติเฉพาะของข้อมูล เช่น ช่วงของค่าหรือการกระจายของข้อมูล มาเป็นตัวชี้วัดในการจัดเรียงแทน ตัวอย่างเช่น counting sort, radix sort, bucket sort

### ประเภทของการ Sort

โดยทั่วไปแล้วพื้นฐานจะมี Bubble Sort ,  Insertion Sort และ Selection Sort

# 1. **Bubble Sort** <br>
&emsp;  เปรียบเทียบข้อมูลที่อยู่ติดกัน แล้วสลับตำแหน่งของข้อมูลคู่นั้น หากเรียงลำดับไม่ถูกต้องจะทำซ้ำไปเรื่อยๆ จนไม่มีการสลับอีก

![bubble sort](/image/animate/bubble-sort.gif)

### code python bubble sort จะมีหน้าตาประมาณนี้

```python
def bubble_sort(arr):
    n = len(arr)

    for i in range(n - 1):
        swapped = False
        for j in range(0, n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
                swapped = True

        print(f"Pass {i + 1}: ", end="")
        for k in range(n):
            print(arr[k], end=" ")
        print()

        if not swapped:
            break

if __name__ == "__main__":
    arr = [5, 3, 1, 4, 2]

    print("Initial Array: ", end="")
    for x in arr:
        print(x, end=" ")
    print("\n")

    bubble_sort(arr)

    print("\nSorted Array: ", end="")
    for x in arr:
        print(x, end=" ")
    print()
```

- Time Complexity: O(n²) worst/average, O(n) best (ถ้าข้อมูลเรียงอยู่แล้ว)
- Space Complexity: O(1)
- ข้อดี: เข้าใจง่าย เขียนง่าย
- ข้อเสีย: ช้ามากเมื่อข้อมูลเยอะ

# 2. **Insertion Sort**<br>
&emsp; นำข้อมูลแต่ละตัวไปแทรกไว้ในตำแหน่งที่ถูกต้องภายในแถวข้อมูลที่เรียงลำดับเสร็จแล้ว (เหมือนเรียงไพ่)

![insertion](/image/animate/insertion-sort.gif)

### code python insertion sort จะมีหน้าตาประมาณนี้

```python
def insertion_sort(arr):
    n = len(arr)

    for i in range(1, n):
        key = arr[i]
        j = i - 1

        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            j -= 1

        arr[j + 1] = key

        print(f"Pass {i}: ", end="")
        for k in range(n):
            print(arr[k], end=" ")
        print()

if __name__ == "__main__":
    arr = [5, 3, 1, 4, 2]

    print("Initial Array: ", end="")
    for x in arr:
        print(x, end=" ")
    print("\n")

    insertion_sort(arr)

    print("\nSorted Array: ", end="")
    for x in arr:
        print(x, end=" ")
    print()
```

- Time Complexity: O(n²) worst, O(n) best
- ข้อดี: เหมาะกับข้อมูลที่เกือบเรียงอยู่แล้ว หรือข้อมูลจำนวนน้อย เช่น เพิ่มตัวละครใหม่เข้าคิวที่เรียงอยู่แล้ว

# 3. **Selection Sort** <br>
&emsp; หาค่าที่น้อยที่สุด หรือมากที่สุด ในส่วนที่ยังไม่ได้เรียงแล้วนำไปสลับไปไว้ตำแหน่งหน้าสุด ทำซ้ำไปเรื่อยๆ จนไม่สลับอีก

![selection sort](/image/animate/selection-sort.gif)

### code python Selection sort จะมีหน้าตาประมาณนี้

```python
def selection_sort(arr):
    n = len(arr)

    for i in range(n - 1):
        min_index = i
        for j in range(i + 1, n):
            if arr[j] < arr[min_index]:
                min_index = j

        arr[i], arr[min_index] = arr[min_index], arr[i]

        print(f"Pass {i + 1}: ", end="")
        for k in range(n):
            print(arr[k], end=" ")
        print()

if __name__ == "__main__":
    arr = [5, 3, 1, 4, 2]

    print("Initial Array: ", end="")
    for x in arr:
        print(x, end=" ")
    print("\n")

    selection_sort(arr)

    print("\nSorted Array: ", end="")
    for x in arr:
        print(x, end=" ")
    print()
```

- Time Complexity: O(n²) ทุกกรณี
- Space Complexity: O(1)
- ข้อดี: จำนวนการสลับข้อมูล (swap) น้อยกว่า Bubble Sort

# 4. **Merge Sort** <br>
&emsp;แบ่งข้อมูลเป็นครึ่งๆ ทำซ้ำจนเหลือ 1 ตัว แล้วรวมพร้อทเรียงลำดับ

### code python Merge sort จะมีหน้าตาประมาณนี้

```python
def merge(arr, left, mid, right):
    left_part = arr[left : mid + 1]
    right_part = arr[mid + 1 : right + 1]

    i = 0  # ตัวชี้ใน left_part
    j = 0  # ตัวชี้ใน right_part
    k = left  # ตัวชี้ใน arr หลัก

    while i < len(left_part) and j < len(right_part):
        if left_part[i] <= right_part[j]:
            arr[k] = left_part[i]
            i += 1
        else:
            arr[k] = right_part[j]
            j += 1
        k += 1

    while i < len(left_part):
        arr[k] = left_part[i]
        i += 1
        k += 1

    while j < len(right_part):
        arr[k] = right_part[j]
        j += 1
        k += 1


def merge_sort(arr, left, right):
    if left >= right:  # base case
        return

    mid = (left + right) // 2
    merge_sort(arr, left, mid)  # recursive call 
    merge_sort(arr, mid + 1, right)  
    merge(arr, left, mid, right)

if __name__ == "__main__":
    arr = [5, 3, 1, 4, 2]
    print("Initial Array:", arr)

    merge_sort(arr, 0, len(arr) - 1)

    print("Sorted Array: ", arr)
```

- Time Complexity: O(n log n) ทุกกรณี — เสถียรกว่า Quick Sort
- Space Complexity: O(n) เพราะต้องใช้ array เสริม
- เป็นตัวอย่างคลาสสิกของ Recursion

# 5. **Quicksort**<br>
&emsp; เลือก ข้อมูลตัวหนึ่งเป็นจุดอ้างอิง (pivot) แบ่งข้อมูลออกเป็นสองส่วน คือ ข้อมูลที่น้อยกว่าจุดอ้างอิงและข้อมูลที่มากกว่าหรือเท่ากับจุดอ้างอิง แล้วจึงเรียงลำดับข้อมูลทั้งสองส่วนนั้น

### code python Quicksort จะมีหน้าตาประมาณนี้

```python
def partition(arr, low, high):
    pivot = arr[high]  # เลือกตัวสุดท้ายเป็น Pivot
    i = low - 1  # ตำแหน่งของตัวที่น้อยกว่า Pivot

    for j in range(low, high):
        # ถ้าเจอค่าที่น้อยกว่าหรือเท่ากับ Pivot
        if arr[j] <= pivot:
            i += 1
            arr[i], arr[j] = arr[j], arr[i]  # สลับตำแหน่ง

    # สลับตำแหน่ง Pivot 
    arr[i + 1], arr[high] = arr[high], arr[i + 1]
    return i + 1


def quick_sort(arr, low, high):
    if low < high:
        pivot_index = partition(arr, low, high)
        quick_sort(arr, low, pivot_index - 1)  # recursive call ครึ่งซ้าย
        quick_sort(arr, pivot_index + 1, high)  # recursive call ครึ่งขวา

if __name__ == "__main__":
    arr = [5, 3, 1, 4, 2]
    print("Initial Array:", arr)

    quick_sort(arr, 0, len(arr) - 1)

    print("Sorted Array: ", arr)
```

# 6. **Heapsort** <br>
&emsp; สร้างโครงสร้างข้อมูลแบบ heap จากข้อมูลที่ต้องการเรียงลำดับ จากนั้นดึงข้อมูลที่ใหญ่ที่สุด (หรือเล็กที่สุด) ออกจาก heap ทีละตัวเพื่อสร้างแถวข้อมูลที่เรียงลำดับออกมา

### code python Heapsort จะมีหน้าตาประมาณนี้

```python
def heapify(arr, n, i):
    largest = i
    left = 2 * i + 1
    right = 2 * i + 2

    # ตรวจสอบว่าโหนดลูกทางซ้ายมีค่ามากกว่าโหนดแม่หรือไม่
    if left < n and arr[left] > arr[largest]:
        largest = left

    # ตรวจสอบว่าโหนดลูกทางขวามีค่ามากกว่าโหนดแม่หรือไม่
    if right < n and arr[right] > arr[largest]:
        largest = right

    # ถ้าตำแหน่งที่มีค่าน้อยที่สุดไม่ใช่โหนดแม่เดิม ให้ทำการสลับ
    if largest != i:
        arr[i], arr[largest] = arr[largest], arr[i]
        heapify(arr, n, largest)  

def heap_sort(arr):
    n = len(arr)

    # 1. สร้าง Max Heap (Rearrange array)
    for i in range(n // 2 - 1, -1, -1):
        heapify(arr, n, i)

    # 2. ดึงทีละตัวออกจาก Heap และสลับไปไว้ท้ายสุด
    for i in range(n - 1, 0, -1):
        arr[0], arr[i] = arr[i], arr[0]  # สลับ root (ค่ามากสุด) ไปไว้หลังสุด
        heapify(arr, i, 0)  # เรียก heapify ที่ root ใหม่


# ส่วนของการทำงานหลัก (main)
if __name__ == "__main__":
    arr = [12, 11, 13, 5, 6, 7]

    heap_sort(arr)

    print("Sorted array: ", end="")
    for val in arr:
        print(val, end=" ")
    print()
```
- Time Complexity: $O(n \log n)$ การันตีความเร็วเท่านี้ทั้งกรณี Best, Average และ Worst Case
- Space Complexity: $O(1)$ In-place Sorting ไม่จำเป็นต้องสร้าง Array เพิ่ม

การใช้ Sorting Algorithm 

- เมื่อต้องการเพิ่มความเร็วในการค้นหาข้อมูล
- ต้องการกำจัดข้อมูลซ้ำ
- ต้องการหาค่าสถิติเฉพาะจุด


### อ้างอิง

- [expert programming.com](https://expert-programming-tutor.com/tutorial/article/KE003174_Computer_Science_that_you_should_know_-_Sorting_data__Sorting_Algorithms_.php)
- [thai github](https://thai-cp.github.io/dsa-basic/sorting/)
- [medium](https://medium.com/@mworldmyworld/%E0%B8%A1%E0%B8%B1%E0%B8%99%E0%B9%84%E0%B8%A1%E0%B9%88%E0%B8%87%E0%B9%88%E0%B8%B2%E0%B8%A2%E0%B9%80%E0%B8%A5%E0%B8%A2%E0%B8%97%E0%B8%B5%E0%B9%88%E0%B8%88%E0%B8%B0%E0%B9%80%E0%B8%82%E0%B9%89%E0%B8%B2%E0%B9%83%E0%B8%88-sorting-algorithm-ep-2-dd492b01666)
- [mikelopster.dev](https://docs.mikelopster.dev/c/c-dsa/chapter-6/sort#:~:text=%E0%B8%81%E0%B8%B2%E0%B8%A3%20sorting%20algorithm%20%28%E0%B8%AB%E0%B8%A3%E0%B8%B7%E0%B8%AD%20%E0%B8%82%E0%B8%B1%E0%B9%89%E0%B8%99%E0%B8%95%E0%B8%AD%E0%B8%99%E0%B8%A7%E0%B8%B4%E0%B8%98%E0%B8%B5%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B9%80%E0%B8%A3%E0%B8%B5%E0%B8%A2%E0%B8%87%E0%B8%A5%E0%B8%B3%E0%B8%94%E0%B8%B1%E0%B8%9A%E0%B8%82%E0%B9%89%E0%B8%AD%E0%B8%A1%E0%B8%B9%E0%B8%A5%29%20%E0%B8%84%E0%B8%B7%E0%B8%AD%E0%B8%81%E0%B8%A3%E0%B8%B0%E0%B8%9A%E0%B8%A7%E0%B8%99%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B8%88%E0%B8%B1%E0%B8%94%E0%B9%80%E0%B8%A3%E0%B8%B5%E0%B8%A2%E0%B8%87%E0%B8%82%E0%B9%89%E0%B8%AD%E0%B8%A1%E0%B8%B9%E0%B8%A5%E0%B9%83%E0%B8%AB%E0%B9%89%E0%B8%AD%E0%B8%A2%E0%B8%B9%E0%B9%88%E0%B9%83%E0%B8%99%E0%B8%A5%E0%B8%B3%E0%B8%94%E0%B8%B1%E0%B8%9A%E0%B8%97%E0%B8%B5%E0%B9%88%E0%B8%95%E0%B9%89%E0%B8%AD%E0%B8%87%E0%B8%81%E0%B8%B2%E0%B8%A3%20%E0%B9%84%E0%B8%A1%E0%B9%88%E0%B8%A7%E0%B9%88%E0%B8%B2%E0%B8%88%E0%B8%B0%E0%B9%80%E0%B8%9B%E0%B9%87%E0%B8%99%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B9%80%E0%B8%A3%E0%B8%B5%E0%B8%A2%E0%B8%87%E0%B8%88%E0%B8%B2%E0%B8%81%E0%B8%99%E0%B9%89%E0%B8%AD%E0%B8%A2%E0%B9%84%E0%B8%9B%E0%B8%A1%E0%B8%B2%E0%B8%81,%E0%B8%AB%E0%B8%A3%E0%B8%B7%E0%B8%AD%E0%B8%88%E0%B8%B2%E0%B8%81%E0%B8%A1%E0%B8%B2%E0%B8%81%E0%B9%84%E0%B8%9B%E0%B8%99%E0%B9%89%E0%B8%AD%E0%B8%A2%20%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B8%88%E0%B8%B1%E0%B8%94%E0%B9%80%E0%B8%A3%E0%B8%B5%E0%B8%A2%E0%B8%87%E0%B8%82%E0%B9%89%E0%B8%AD%E0%B8%A1%E0%B8%B9%E0%B8%A5%20%28sorting%29%20%E0%B9%80%E0%B8%9B%E0%B9%87%E0%B8%99%E0%B8%9E%E0%B8%B7%E0%B9%89%E0%B8%99%E0%B8%90%E0%B8%B2%E0%B8%99%E0%B8%AA%E0%B8%B3%E0%B8%84%E0%B8%B1%E0%B8%8D%E0%B9%83%E0%B8%99%20computer%20science%20%E0%B9%81%E0%B8%A5%E0%B8%B0%E0%B8%A3%E0%B8%A7%E0%B8%A1%E0%B8%96%E0%B8%B6%E0%B8%87%E0%B8%A1%E0%B8%B5%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B8%99%E0%B8%B3%E0%B9%84%E0%B8%9B%E0%B9%83%E0%B8%8A%E0%B9%89%E0%B9%83%E0%B8%99%E0%B8%87%E0%B8%B2%E0%B8%99%E0%B8%AB%E0%B8%A5%E0%B8%B2%E0%B8%81%E0%B8%AB%E0%B8%A5%E0%B8%B2%E0%B8%A2%E0%B8%A3%E0%B8%B9%E0%B8%9B%E0%B9%81%E0%B8%9A%E0%B8%9A%20%E0%B9%80%E0%B8%8A%E0%B9%88%E0%B8%99)

