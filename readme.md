# C++ Cookbook

## Table of Contents

1. [Fundamental](#fundamental)
2. [Data Types](#data-types)
3. [Decision Making](#decision-making)
4. [Loops](#loops)
5. [Array](#arrays)
6. [String] - **Coming Soon**

## Fundamental

- [Variables](#variables)
- [Constants](#constants)
- [Naming conventions](#naming-conventions)
- [Mathematical expressions](#mathematical-expressions)
- [Order of Operation](#order-of-operation)
- [Writing output to the console](#writing-output-to-the-console)
- [Reading input from the console](#reading-input-from-the-console)
- [CMath library](#cmath-library)
- [Comments](#comments)

---

### Variables

วิธีการสร้างตัวแปร จะอยู่ในรูปแบบของ `VAR_TYPE VAR_NAME = VALUE;` เช่น

```c++
#include <iostream>

int main()
{
    int money = 100;
    double height = 160.5;

    return 0;
}
```

หรือเราจะไม่กำหนดค่าเริ่มต้นให้กับตัวแปรก็ได้ แต่ compiler ทำการสุ่มค่าให้

```c++
#include <iostream>
using namespace std;

int main()
{
    int money;
    cout << money; // money = some random number

    return 0;
}
```

Program Example : สลับค่าตัวแปร

```c++
#include <iostream>
using namespace std;

int main()
{
    int a = 10;
    int b = 20;

    int temp = a;
    a = b;
    b = temp;

    cout << a << " " << b;

    return 0;
}
```

```c++
#include <iostream>
using namespace std;

int main()
{
    int a = 10;
    int b = 20;

    a = a + b; // Step 1: Add both numbers
    b = a - b; // Step 2: Subtract the new value of a by b to get original a
    a = a - b; // Step 3: Subtract the new value of b from the new value of a to get original b

    cout << a << " " << b;

    return 0;
}
```

---

### Constants

วิธีการสร้างค่าคงที่ด้วยคำสั่ง `const` เพื่อป้องกันไม่ให้ตัวแปรถูกเปลี่ยนแปลงค่า

```c++
#include <iostream>

int main()
{
    const int number = 999;
    number = 199; // can't update value

    return 0;
}
```

---

### Naming conventions

ในภาษา C++ มักจะใช้ Camel Case กัน

```c++
#include <iostream>

int main()
{
    int item_count; // Snake Case
    int ItemCount;  // Pascal Case
    int itemCount;  // Camel Case

    return 0;
}
```

---

### Mathematical expressions

```c++
#include <iostream>

int main()
{
    int x = 10;
    int y = 3;
    int z;

    z = x + y;
    z = x - y;
    z = x * y;
    z = x / y;
    z = x % y;

    x += 1;

    x++;
    ++x;

    z = x++;
    z = ++x;

    return 0;
}
```

---

### Order of Operation

```c++
#include <iostream>

int main()
{
    // ()
    // * and /
    // + and -
    double x = (1 + 2) * 3;

    return 0;
}
```

---

### Writing output to the console

เขียนข้อมูลไปที่ console

```c++
#include <iostream>
using namespace std;

int main()
{
    int x = 10;
    cout << "x = ";
    cout << x;

    return 0;
}
```

สามารถรวบให้เหลือในบรรทัดเดียวได้

```c++
#include <iostream>
using namespace std;

int main()
{
    int x = 10;
    cout << "x = " << x;

    return 0;
}
```

ใช้คำสั่ง endl (end line) เพื่อขึ้นบรรทัดใหม่ได้

```c++
#include <iostream>
using namespace std;

int main()
{
    int x = 10;
    int y = 20;
    cout << "x = " << x << endl;
    cout << "y = " << y;

    return 0;
}
```

สามารถรวบคำสั่งได้ (แนะนำให้ tab บรรทัดที่ 2 ขึ้นไปให้ตำแหน่งอยู่ตรงกับผลลัพธ์)

```c++
#include <iostream>
using namespace std;

int main()
{
    int x = 10;
    int y = 20;
    cout << "x = " << x << endl
         << "y = " << y;

    return 0;
}
```

Program Example : โปรแกรมคำนวน vat 7% + service charge 10%

```c++
#include <iostream>
using namespace std;

int main()
{
    double price = 5000;
    cout << "Price: ฿" << price << endl;

    const double tax = .07;
    double stateTax = price * tax;
    cout << "State Tax: ฿" << stateTax << endl;

    const double serviceCharge = .1;
    double stateServiceCharge = price * serviceCharge;
    cout << "State Service Charge: ฿" << stateServiceCharge << endl;

    double totalTax = stateTax + stateServiceCharge;
    cout << "Total Tax: ฿" << totalTax;

    return 0;
}
```

---

### Reading input from the console

อ่านค่าจาก console ด้วยคำสั่ง `cin`

```c++
#include <iostream>
using namespace std;

int main()
{
    cout << "Enter a value: ";

    int value;
    cin >> value;

    cout << value;

    return 0;
}
```

ในการรับค่าตัวแปรมากกว่า 1 ตัวสามารถใช้คั่นด้วย space หรือ enter ก็ได้

```c++
#include <iostream>
using namespace std;

int main()
{
    cout << "Enter values for x and y: ";

    int x;
    int y;
    cin >> x;
    cin >> y;

    cout << x + y;

    return 0;
}
```

เช่นเดียวกับการใช้งาน `cout` เราสามารถรวบคำสั่ง `cin` ได้

```c++
#include <iostream>
using namespace std;

int main()
{
    cout << "Enter values for x and y: ";

    int x;
    int y;
    cin >> x >> y;

    cout << x + y;

    return 0;
}
```

Program Exmaple : Fahrenheit to Celsius

```c++
#include <iostream>
using namespace std;

int main()
{
    cout << "Fahrenheit: ";
    int fahrenheit;
    cin >> fahrenheit;

    double celsius = (fahrenheit - 32) / 1.8;
    cout << celsius;

    return 0;
}
```

---

### Cmath library

> document : https://cplusplus.com/reference/cmath/

ตัวอย่างการใช้งานฟังก์ชันจาก cmath library

```c++
#include <iostream>
#include <cmath>
using namespace std;

int main()
{
    int p = pow(2, 5);
    cout << "Power = " << p << endl;    // ยกกำลัง

    double c = ceil(1.34);
    cout << "Ceil = " << c << endl;     // ปัดขึ้น

    double f = floor(1.74);
    cout << "Floor = " << f;            // ปัดลง
    return 0;
}
```

Program Example - คำนวณพื้นที่วงกลม

```c++
#include <iostream>
#include <cmath>
using namespace std;

int main()
{
    cout << "Enter radius: ";
    double radius;
    cin >> radius;

    const double pi = 3.14;
    double area = pi * pow(radius, 2);

    cout << area;
    return 0;
}
```

---

### Comments

การคอมเมนต์โค้ด เพื่อผู้อื่น และตัวเองในอนาคต

```c++
#include <iostream>

int main()
{
    // Hello World
    // This is a comment

    /*
     Hello World
     This is also a comment
     */

    return 0;
}
```

## Data Types

- [Fundamental Types](#fundamental-types)
- [Initializing Variables](#initializing-variables)
- [Formatting Output](#formatting-output)
- [Data Limits](#data-limits)
- [Type Casting](#type-casting)
- [Working with Booleans](#working-with-booleans)

---

### Fundamental Types

**Integer Number**

|    Type     | Range                                                   |
| :---------: | ------------------------------------------------------- |
|   `short`   | -32,768 to 32767                                        |
|    `int`    | -2,147,483,648 to 2,147,483,647                         |
|   `long`    | -2,147,483,648 to 2,147,483,647                         |
| `long long` | -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |

**Floating-point Number**

|     Type      | Range                | Precision (Digits) |
| :-----------: | -------------------- | ------------------ |
|    `float`    | -3.4E38 to 3.4E38    | 7                  |
|   `double`    | -1.7E308 to 1.7E308  | 15                 |
| `long double` | -3.4E932 to 1.7E4832 |                    |

**Others Types**

|  Type  | Range        |
| :----: | ------------ |
| `bool` | true / false |
| `char` | 1 character  |

---

### Initializing Variables

```c++
#include <iostream>

int main()
{
    double price = 25.50;
    float taxRate = 0.07f;
    long money = 90000L;
    long long lifePoint = 999999999LL;
    char letter = 'a';
    bool isValid = false;

    return 0;
}
```

---

### Formatting Output

**Format floating-point number**

```c++
#include <iostream>
#include <iomanip>
using namespace std;

int main()
{
    cout << fixed << setprecision(2) << 124.45678;

    return 0;
}
```

---

### Data Limits

```c++
#include <iostream>
using namespace std;

int main()
{
    cout << numeric_limits<int>::min() << endl  // min = -2,147,483,648
         << numeric_limits<int>::max();         // max =  2,147,483,647

    return 0;
}
```

---

### Type Casting

```c++
#include <iostream>
using namespace std;

int main()
{
    int x = 10;
    int y = 3;

    double z = (double)x / y; // Cast variable x from INT to DOUBLE
    cout << z;

    return 0;
}
```

### Working with Booleans

```c++
#include <iostream>
using namespace std;

int main()
{
    bool result = false;
    cout << result;              // 0
    cout << boolalpha << result; // false

    bool result2 = true;
    cout << result2;              // 1
    cout << boolalpha << reslut2; // true

    return 0;
}
```

---

## Decision Making

- [Comparison Operators](#comparison-operators)
- [Logical Operators](#logical-operators)
- [Order of Logical Operators](#order-of-logical-operators)
- [IF Statement](#if-statement)
- [IF-ELSE Statement](#if-else-statement)
- [Conditional Operator](#conditional-operator)
- [SWITCH Statement] - **Coming Soon**

---

### Comparison Operators

| Operator | Name                     | Example |
| :------: | ------------------------ | :-----: |
|   `>`    | Grater than              |  x > y  |
|   `<`    | Less than                |  x < y  |
|   `>=`   | Grather than or equal to | x >= y  |
|   `<=`   | Less than or equal to    | x <= y  |
|   `==`   | Equal to                 | x == y  |
|   `!=`   | Not equal                | x != y  |

```c++
#include <iostream>

int main()
{
    int x = 10;
    int y = 20;

    bool result = x > y;    // result = false
    bool result2 = x == 10; // result2 = true

    return 0;
}

```

---

### Logical Operators

| Operator | Name        |       Example       |
| :------: | ----------- | :-----------------: |
|   `&&`   | Logical and |   x > 5 && x < 10   |
|  `\|\|`  | Logical or  |  x < 0 \|\| x > 1   |
|   `!`    | Logical not | !(x >= 2 && x <= 7) |

```c++
#include <iostream>

int main()
{
    int age = 2;

    bool isBaby = age >= 1 && age <= 3;      // isBaby = true
    bool isNotBaby = !(age >= 1 && age <= 3) // isNotBaby = false

    return 0;
}
```

---

### Order of Logical Operators

```c++
#include <iostream>

int main ()
{
    // ()
    // !
    // &&
    // ||

    bool a = true;
    bool b = false;

    bool result1 = b || !a;     // result1 = false
    bool result2 = a || b && b; // result2 = true

    return 0;
}
```

---

### IF Statement

```c++
if (boolean)
{
    // do statements when boolean == true
}
```

```c++
#include <iostream>
using namespace std;

int main()
{
    int number = 100;
    if (number > 0)
    {
        cout << "Positive Number" << endl;
    }

    cout << "End Program";

    return 0;
}

```

Program Example : โปรแกรมคำนวณเกรด

```c++
#include <iostream>
using namespace std;

int main()
{
    int score = 70;

    if (score >= 80)
    {
        cout << "Grade A";
    }

    if (score >= 70 && score <= 79)
    {
        cout << "Grade B";
    }

    if (score >= 60 && score <= 69)
    {
        cout << "Grade C";
    }

    if (score <= 59)
    {
        cout << "Grade D";
    }

    return 0;
}
```

---

### IF-ELSE Statement

```c++
if (boolean)
{
    // do statements when boolean == true
}
else
{
    // do statements when boolean == false
}
```

```c++
#include <iostream>
using namespace std;

int main()
{
    int number = 100;
    if (number > 0)
    {
        cout << "Positive Number" << endl;
    }
    else
    {
        cout << "Not a Positive Number" << endl;
    }

    cout << "End Program";

    return 0;
}
```

Program Example : โปรแกรมคำนวณเกรด

```c++
#include <iostream>
using namespace std;

int main()
{
    int score = 70;
    if (score >= 80)
    {
        cout << "Grade A";
    }
    else
    {
        if (score >= 70)
        {
            cout << "Grade B";
        }
        else
        {
            if (score >= 60)
            {
                cout << "Grade C";
            }
            else
            {
                cout << "Grade D";
            }
        }
    }

    return 0;
}
```

แต่เนื่องจากในแต่ละ statement มีเพียง 1 คำสั่ง สามารถละเว้น `{}` ได้ เพื่อให้โค้ดอ่านง่ายขึ้น

```c++
#include <iostream>
using namespace std;

int main()
{
    int score = 70;
    if (score >= 80)
        cout << "Grade A";
    else if (score >= 70)
        cout << "Grade B";
    else if (score >= 60)
        cout << "Grade C";
    else
        cout << "Grade D";

    return 0;
}
```

---

### Conditional Operator

```c++
#include <iostream>

int main()
{
    int price = 1000;

    // double tax;
    // if (price >= 1000)
    // {
    //     tax = .07;
    // }
    // else
    // {
    //     tax = .1;
    // }
    double tax = (price >= 1000) ? .07 : .1;

    return 0;
}
```

Program Example : ค้นหาจำนวนที่มากกว่า จากข้อมูลเข้าสองจำนวน

```c++
#include <iostream>
using namespace std;

int main()
{
    int first;
    int second;
    cin >> first >> second;

    int result;
    if (first > second)
        result = first;
    else
        result = second;

    cout << result;

    return 0;
}
```

```c++
#include <iostream>
using namespace std;

int main()
{
    int first;
    int second;
    cin >> first >> second;

    int result = (first > second) ? first : second;

    cout << result;

    return 0;
}
```

---

## Loops

- [For Loops](#for-loops)
- [Range-based for Loops]()
- [While Loops](#while-loops)
- [Do-while Loops](#do-while-loops)
- [Break and continue statements](#break-and-continue-statements)

---

### For Lops

```c++
for (initialization; condition; update)
{
    // do staetment if condition is true
}
```

```c++
#include <iostream>
using namespace std;

int main()
{
    for (int i = 0; i < 5; i++)
    {
        cout << "Hello World " << i << endl;
    }

    for (int i = 10; i >= 6; i--)
    {
        cout << "Hello World " << i << endl;
    }

    for (int i = 1; i <= 10; i++)
    {
        if (i % 2 == 0)
        {
            cout << i << endl;
        }
    }

    for (int i = 1; i <= 10; i += 2)
    {
        cout << i << endl;
    }

    return 0;
}
```

Program Example : หาผลรวมตัวเลขสิบตัวจาก input

```c++
#include <iostream>
using namespace std;

int main()
{
    int number;
    int sum = 0;

    for (int i = 0; i < 10; i++)
    {
        cin >> number;
        sum += number;
    }

    cout << sum;
}
```

---

### Range-based for Loops

```c++
int numbers[5] = { 10, 20, 30, 40, 50 }

for (int number: numbers)
    cout << number << endl;

for (auto number: numbers)
    cout << number << endl;

```

---

### While Loops

```c++
while (condition)
{
    // Do statement if condition is True
}
```

```c++
#include <iostream>
using namespace std;

int main()
{
    int i = 0;
    while (i < 5)
    {
        cout << "Hello World " << i << endl;
        i++;
    }

    return 0;
}
```

```c++
#include <iostream>
using namespace std;

int main()
{
    int number = -1;

    while (number != 0)
    {
        cin >> number;
    }

    return 0;
}
```

---

### Do-while Loops

```c++
do
{
    // Always execute at least 1 time.
    // Do statement until condition is false.
} while (condition);
```

```c++
#include <iostream>
using namespace std;

int main()
{
    int number;

    do
    {
        cin >> number;
    } while (number != 0);

    return 0;
}
```

---

### Break and continue statements

`break;` used to jump out of a loop.

```c++
for (int i = 0; i < 10; i++) {
  if (i == 5)
    break;

  cout << i << endl;
}
```

`continue` used to continues with the next iteration in the loop.

```c++
for (int i = 0; i < 10; i++) {
  if (i == 5)
    continue;

  cout << i << endl;
}
```

---

## Arrays

- [Creating Arrays](#creating-arrays)
- [Copying Arrays](#copying-arrays)
- [Comparing Arrays](#comparing-arrays)
- [Unpacking Arrays](#upacking-arrays-structured-binding)
- [Sorting Arrays](#sorting-arrays)

---

### Creating Arrays

```c++
int numbers[5]; // We get numbers[0], numbers[1], ..., numbers[4]
numbers[0] = 10;
numbers[1] = 20;
numbers[2] = 30;
numbers[3] = 40;
numbers[4] = 50;

cout << numbers[0] << endl
     << numbers[1] << endl
     << numbers[2] << endl
     << numbers[3] << endl
     << numbers[4] << endl:
```

```c++
int numbers[5] = {10, 20, 30, 40, 50};
```

```c++
int numbers[5];
cin >> numbers[0]
    >> numbers[1]
    >> numbers[2]
    >> numbers[3]
    >> numbers[4];

cout << numbers[0] << endl
     << numbers[1] << endl
     << numbers[2] << endl
     << numbers[3] << endl
     << numbers[4] << endl:
```

```c++
#include <iostream>
using namespace std;

int main()
{
    int n;
    cin >> n;

    int numbers[n];
    for (int i = 0; i < n; i++)
        cin >> numbers[i];

    for (int number: numbers)
        cout << number << endl;
}
```

---

### Copying Arrays

```c++
int first[3] = {10, 20, 30};
int second[3];

for (int i = 0; i < 3; i++) // ! Can't use Ranged-base for loop !
    second[i] = first[i];

for (int number: second)
    cout << number << endl;
```

---

### Comparing Arrays

```c++
int first[] = {10, 20, 30};
int second[] = {10, 20, 30};

bool isEqual = true;
for (int i = 0; i < 3; i++)
    if (first[i] != second[i])
    {
        isEqual = false;
        break;
    }

cout << boolalpha << isEqual;
```

---

### Upacking Arrays (Structured Binding)

```c++
int numbers[3] = {10, 20, 30};

// int x = numbers[0];
// int y = numbers[1];
// int z = numbers[2];
auto [x, y, z] = numbers;
```

---

### Sorting Arrays

```c++
int numbers[5] = {50, 10, 40, 20, 30};

// Bubble sort - Asecdenting order
for (int i = 0; i < 4; i++)
{
    for (int j = 0; j < 4; j++)
    {
        if (numbers[j] > numbers[j + 1])
        {
            int temp = numbers[j];
            numbers[j] = numbers[j + 1];
            numbers[j + 1] = temp;
        }
    }
}
```
