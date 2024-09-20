# C++ Cookbook

## Table of Contents

1. [Fundamental]
2. [Data Types]
3. [Decision Making]
4. [Loops]
5. [Array]
6. [String]

<!-- - Fundamental

  - [Variables](#variables)
  - [Constants](#constants)
  - [Naming conventions](#naming-conventions)
  - [Mathematical expressions](#mathematical-expressions)
  - [Order of Operation](#order-of-operation)
  - [Writing output to the console](#writing-output-to-the-console)
  - [Reading input from the console](#reading-input-from-the-console)
  - [CMath library](#cmath-library)
  - [Comments](#comments)

  - [Fundamental Types] -->

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

### Variables

**วิธีการสร้างตัวแปร จะอยู่ในรูปแบบของ `VAR_TYPE VAR_NAME = VALUE;` เช่น**

```c++
#include <iostream>

int main()
{
    int money = 100;
    double height = 160.5;

    return 0;
}
```

**หรือเราจะไม่กำหนดค่าเริ่มต้นให้กับตัวแปรก็ได้ แต่ compiler ทำการสุ่มค่าให้**

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

**Program Example : สลับค่าตัวแปร**

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

**สามารถรวบคำสั่งได้ (แนะนำให้ tab บรรทัดที่ 2 ขึ้นไปให้ตำแหน่งอยู่ตรงกับผลลัพธ์)**

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

**Program Example : โปรแกรมคำนวน vat 7% + service charge 10%**

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

### Reading input from the console

**อ่านค่าจาก console ด้วยคำสั่ง `cin`**

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

**ในการรับค่าตัวแปรมากกว่า 1 ตัวสามารถใช้คั่นด้วย space หรือ enter ก็ได้**

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

**เช่นเดียวกับการใช้งาน `cout` เราสามารถรวบคำสั่ง `cin` ได้**

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

**Program Exmaple : Fahrenheit to Celsius**

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

### Cmath library

> document : https://cplusplus.com/reference/cmath/

**ตัวอย่างการใช้งานฟังก์ชันจาก cmath library**

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

**Program Example - คำนวณพื้นที่วงกลม**

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
