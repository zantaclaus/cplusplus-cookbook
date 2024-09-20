## Contents

- Chapter 1 - Fundamental
  - [Variables](#variables)
  - [Constants](#constants)
  - [Naming conventions](#naming-conventions)
  - [Order of Operators](#order-of-operation)
- [Writing output to the console](#writing-output-to-the-console)
- [Reading input from the console](#reading-input-from-the-console)
- [CMath library](#cmath-library)
- [Comments](#comments)

## Variables

วิธีสร้างตัวแปร กำหนดค่าเริ่มต้น และแสดงผล

```c++
#include <iostream>
using namespace std;

int main()
{
    int money = 100;
    int count; = 0;
    double height = 160.5;
    cout << money;

    return 0;
}
```

สร้างตัวแปร แต่ไม่ได้กำหนดค่าเริ่มต้น ค่าเริ่มต้นจะถูก random ให้กับตัวแปร

```c++
#include <iostream>
using namespace std;

int main()
{
    int money;
    cout << money; // Some random number

    return 0;
}
```

#### Challenge - Swap value of two variables

```c++
#include <iostream>
using namespace std;

int main()
{
    int a = 1;
    int b = 2;

    // Logic to swap variable //

    cout << a << " " << b; // 2 1

    return 0;
}
```

## Constants

การสร้าง**ค่าคงที่**

```c++
#include <iostream>

int main()
{
    const int number = 999;
    number = 199; // can't update value

    return 0;
}
```

## Naming conventions

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

## Mathematical expressions

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
    x++;
    ++x;

    return 0;
}
```

## Order of Operation

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

## Writing output to the console

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

สามารถรวบคำสั่งได้ แนะนำให้ tab ให้ตรงกับผลลัพธ์

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

#### ​Challenge - Tax and Service charge calcualtor

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

## Reading input from the console

อ่านค่าจาก console ด้วยคำสั่ง `cin`

```c++
#include <iostream>
using namespace std;

int main()
{
    cout << "Enter a value: "; // Try input integer/floating number

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

เหมือนกับการ `cout` เราสามารถรวบคำสั่งได้

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

#### Challenge - Celsius to Fahrenheit

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

## Cmath library

> document : https://cplusplus.com/reference/cmath/

```c++
#include <iostream>
#include <cmath>
using namespace std;

int main()
{
    int p = pow(2, 5);
    cout << "Power = " << p << endl;

    double c = ceil(1.34);
    cout << "Ceil  = " << c << endl;

    double f = floor(1.74);
    cout << "Floor = " << f;
    return 0;
}
```

#### Challenge - Calculate area of a circle

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

## Comments

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
