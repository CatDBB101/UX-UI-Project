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

1. **Bubble Sort** <br>
&emsp;  เปรียบเทียบข้อมูลที่อยู่ติดกัน แล้วสลับตำแหน่งของข้อมูลคู่นั้น หากเรียงลำดับไม่ถูกต้องจะทำซ้ำไปเรื่อยๆ จนไม่มีการสลับอีก

![bubble sort](/image/animate/bubble-sort.gif)

### code c++ bubble sort จะมีหน้าตาประมาณนี้

```c++
#include <iostream>
#include <vector>
using namespace std;

void bubbleSort(vector<int> &arr) {
  int n = arr.size();
  bool swapped;

  for (int i = 0; i < n - 1; i++) {
    swapped = false;
    for (int j = 0; j < n - i - 1; j++) {
      if (arr[j] > arr[j + 1]) {
        // Swap arr[j] and arr[j+1]
        int temp = arr[j];
        arr[j] = arr[j + 1];
        arr[j + 1] = temp;
        swapped = true;
      }
    }

    // Visualize current state of array
    cout << "Pass " << i + 1 << ": ";
    for (int k = 0; k < n; k++) {
      cout << arr[k] << " ";
    }
    cout << "\n";

    // If no swaps occurred, array is sorted
    if (!swapped)
      break;
  }
}

int main() {
  vector<int> arr = {5, 3, 1, 4, 2};

  cout << "Initial Array: ";
  for (int i = 0; i < arr.size(); i++) {
    cout << arr[i] << " ";
  }
  cout << "\n\n";

  bubbleSort(arr);

  cout << "\nSorted Array: ";
  for (int i = 0; i < arr.size(); i++) {
    cout << arr[i] << " ";
  }

  return 0;
}
```

- Time Complexity: O(n²) worst/average, O(n) best (ถ้าข้อมูลเรียงอยู่แล้ว)
- Space Complexity: O(1)
- ข้อดี: เข้าใจง่าย เขียนง่าย
- ข้อเสีย: ช้ามากเมื่อข้อมูลเยอะ

2. **Insertion Sort**<br>
&emsp; นำข้อมูลแต่ละตัวไปแทรกไว้ในตำแหน่งที่ถูกต้องภายในแถวข้อมูลที่เรียงลำดับเสร็จแล้ว (เหมือนเรียงไพ่)

![insertion](/image/animate/insertion-sort.gif)

### code c++ insertion sort จะมีหน้าตาประมาณนี้

```c++
#include <iostream>
#include <vector>
using namespace std;

void insertionSort(vector<int> &arr) {
  int n = arr.size();

  for (int i = 1; i < n; i++) {
    int key = arr[i];
    int j = i - 1;

    // Move elements of arr[0..i-1], that are greater than key, to one position
    // ahead of their current position
    while (j >= 0 && arr[j] > key) {
      arr[j + 1] = arr[j];
      j--;
    }

    // Insert key into the sorted part
    arr[j + 1] = key;

    // Print current state of array
    cout << "Pass " << i << ": ";
    for (int k = 0; k < n; k++) {
      cout << arr[k] << " ";
    }
    cout << "\n";
  }
}

int main() {
  vector<int> arr = {5, 3, 1, 4, 2};

  cout << "Initial Array: ";
  for (int i = 0; i < arr.size(); i++) {
    cout << arr[i] << " ";
  }
  cout << "\n\n";

  insertionSort(arr);

  cout << "\nSorted Array: ";
  for (int i = 0; i < arr.size(); i++) {
    cout << arr[i] << " ";
  }

  return 0;
}
```

- Time Complexity: O(n²) worst, O(n) best
- ข้อดี: เหมาะกับข้อมูลที่เกือบเรียงอยู่แล้ว หรือข้อมูลจำนวนน้อย เช่น เพิ่มตัวละครใหม่เข้าคิวที่เรียงอยู่แล้ว

3. **Selection Sort** <br>
&emsp; หาค่าที่น้อยที่สุด หรือมากที่สุด ในส่วนที่ยังไม่ได้เรียงแล้วนำไปสลับไปไว้ตำแหน่งหน้าสุด ทำซ้ำไปเรื่อยๆ จนไม่สลับอีก

![selection sort](/image/animate/selection-sort.gif)

### code c++ Selection sort จะมีหน้าตาประมาณนี้

```c++
#include <iostream>
#include <vector>
using namespace std;

void selectionSort(vector<int> &arr) {
  int n = arr.size();

  for (int i = 0; i < n - 1; i++) {
    // Find the minimum element in unsorted array
    int minIndex = i;
    for (int j = i + 1; j < n; j++) {
      if (arr[j] < arr[minIndex]) {
        minIndex = j;
      }
    }

    // Swap the found minimum element with the first element
    int temp = arr[minIndex];
    arr[minIndex] = arr[i];
    arr[i] = temp;

    // Print current state of array
    cout << "Pass " << i + 1 << ": ";
    for (int k = 0; k < n; k++) {
      cout << arr[k] << " ";
    }
    cout << "\n";
  }
}

int main() {
  vector<int> arr = {5, 3, 1, 4, 2};

  cout << "Initial Array: ";
  for (int i = 0; i < arr.size(); i++) {
    cout << arr[i] << " ";
  }
  cout << "\n\n";

  selectionSort(arr);

  cout << "\nSorted Array: ";
  for (int i = 0; i < arr.size(); i++) {
    cout << arr[i] << " ";
  }

  return 0;
}
```

- Time Complexity: O(n²) ทุกกรณี
- Space Complexity: O(1)
- ข้อดี: จำนวนการสลับข้อมูล (swap) น้อยกว่า Bubble Sort

4. **Merge Sort** <br>
&emsp;แบ่งข้อมูลเป็นครึ่งๆ ทำซ้ำจนเหลือ 1 ตัว แล้วรวมพร้อทเรียงลำดับ

```csharp
void MergeSort(int[] arr, int left, int right)
{
    if (left >= right) return; // base case

    int mid = (left + right) / 2;
    MergeSort(arr, left, mid);       // recursive call ครึ่งซ้าย
    MergeSort(arr, mid + 1, right);  // recursive call ครึ่งขวา
    Merge(arr, left, mid, right);
}
```

- Time Complexity: O(n log n) ทุกกรณี — เสถียรกว่า Quick Sort
- Space Complexity: O(n) เพราะต้องใช้ array เสริม
- เป็นตัวอย่างคลาสสิกของ Recursion

5. **Quicksort**<br>
&emsp; เลือก ข้อมูลตัวหนึ่งเป็นจุดอ้างอิง (pivot) แบ่งข้อมูลออกเป็นสองส่วน คือ ข้อมูลที่น้อยกว่าจุดอ้างอิงและข้อมูลที่มากกว่าหรือเท่ากับจุดอ้างอิง แล้วจึงเรียงลำดับข้อมูลทั้งสองส่วนนั้น

```csharp
void QuickSort(int[] arr, int low, int high)
{
    if (low < high)
    {
        int pivotIndex = Partition(arr, low, high);
        QuickSort(arr, low, pivotIndex - 1);   // recursive
        QuickSort(arr, pivotIndex + 1, high);  // recursive
    }
}
```

6. **Heapsort** <br>
&emsp; สร้างโครงสร้างข้อมูลแบบ heap จากข้อมูลที่ต้องการเรียงลำดับ จากนั้นดึงข้อมูลที่ใหญ่ที่สุด (หรือเล็กที่สุด) ออกจาก heap ทีละตัวเพื่อสร้างแถวข้อมูลที่เรียงลำดับออกมา

```java
public class HeapSort {

    public static void main(String[] args) {
        int[] arr = {12, 11, 13, 5, 6, 7};

        heapSort(arr);

        System.out.print("Sorted array: ");
        for (int val : arr) {
            System.out.print(val + " ");
        }
    }

    public static void heapSort(int[] arr) {
        int n = arr.length;
        for (int i = n / 2 - 1; i >= 0; i--) {
            heapify(arr, n, i);
        }

        for (int i = n - 1; i > 0; i--) {
            int temp = arr[0];
            arr[0] = arr[i];
            arr[i] = temp;

            heapify(arr, i, 0);
        }
    }

    private static void heapify(int[] arr, int n, int i) {
        int largest = i;       
        int left = 2 * i + 1;  
        int right = 2 * i + 2; 
        
        if (left < n && arr[left] > arr[largest]) {
            largest = left;
        }

        if (right < n && arr[right] > arr[largest]) {
            largest = right;
        }

        if (largest != i) {
            int swap = arr[i];
            arr[i] = arr[largest];
            arr[largest] = swap;

            heapify(arr, n, largest);
        }
    }
}
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

