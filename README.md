# 19AI304 - Fundamentals of C Programming - 2025 Odd - M4

## IAPR-4 - Module 4 - FoC

### 7. Implementation of Functions

### 8. Implementation of Passing Parameters

---

# Ex.No:16

## Date Validation Using Functions

**Date : 15/05/2026**

### Aim:
---
To implement a C program to read a date in the format DD/MM/YYYY and determine whether the entered date is valid using a function without parameters and without return value, ensuring the correctness of day, month, year, and leap year conditions.
---

## Algorithm

### Step 1:

Start

### Step 2:

Include the standard input-output library:
`#include<stdio.h>`

### Step 3:

Call the function `validateDate()`.

### Step 4:

Inside `validateDate()` function, declare variables:

* `dd`
* `mm`
* `yy`

### Step 5:

Ask the user to enter a date in `DD/MM/YYYY` format.

### Step 6:

Read the date values using `scanf`.

### Step 7:

Check whether the year is between `1900` and `9999`.

* If invalid, display:
  `Year is not valid`

### Step 8:

Check whether the month is between `1` and `12`.

* If invalid, display:
  `Month is not valid`

### Step 9:

If the month contains 31 days, check whether the day is between `1` and `31`.

### Step 10:

If the month contains 30 days, check whether the day is between `1` and `30`.

### Step 11:

If the month is February:

* Check whether the day is between `1` and `28`
* If day is `29`, verify leap year condition

### Step 12:

If all conditions are satisfied, display:
`Date is valid.`

### Step 13:

Otherwise display:
`Date is invalid.`

### Step 14:

Stop

---

## Program

```c id="v9m12e"
#include<stdio.h>

void validateDate();

int main()
{
    validateDate();
    return 0;
}

void validateDate()
{
    int dd, mm, yy;
    int valid = 0;

    printf("Enter date (DD/MM/YYYY): ");
    scanf("%d/%d/%d", &dd, &mm, &yy);

    if(yy < 1900 || yy > 9999)
    {
        printf("Year is not valid");
        return;
    }

    if(mm < 1 || mm > 12)
    {
        printf("Month is not valid");
        return;
    }

    if(mm == 1 || mm == 3 || mm == 5 || mm == 7 ||
       mm == 8 || mm == 10 || mm == 12)
    {
        if(dd >= 1 && dd <= 31)
            valid = 1;
    }
    else if(mm == 4 || mm == 6 || mm == 9 || mm == 11)
    {
        if(dd >= 1 && dd <= 30)
            valid = 1;
    }
    else if(mm == 2)
    {
        if(dd >= 1 && dd <= 28)
        {
            valid = 1;
        }
        else if(dd == 29)
        {
            if((yy % 400 == 0) || (yy % 4 == 0 && yy % 100 != 0))
            {
                valid = 1;
            }
        }
    }

    if(valid)
        printf("Date is valid.");
    else
        printf("Date is invalid.");
}
```

## Output

```text id="bq1n7k"
Enter date (DD/MM/YYYY): 29/02/2024
Date is valid.
```

## Result

Thus, the program was implemented and executed successfully, and the required output was obtained.

---

# Ex.No:17

## Maximum and Minimum Using Functions

**Date : 15/05/2026**

## Aim

To develop a C program that uses functions with parameters and return values to compute and display the maximum and minimum of two user-entered numbers.

---

## Algorithm

### Step 1:

Start

### Step 2:

Include the standard input-output library:
`#include<stdio.h>`

### Step 3:

Declare variables:

* `num1`
* `num2`
* `maximum`
* `minimum`

### Step 4:

Ask the user to enter two numbers.

### Step 5:

Read the numbers using `scanf`.

### Step 6:

Call the function `max(num1, num2)`.

### Step 7:

Inside function `max(num1, num2)`:

* Compare both numbers
* Return the larger number

### Step 8:

Store the returned value in `maximum`.

### Step 9:

Call the function `min(num1, num2)`.

### Step 10:

Inside function `min(num1, num2)`:

* Compare both numbers
* Return the smaller number

### Step 11:

Store the returned value in `minimum`.

### Step 12:

Display maximum and minimum values.

### Step 13:

Stop

---

## Program

```c id="m8r4dz"
#include<stdio.h>

int max(int num1, int num2);
int min(int num1, int num2);

int main()
{
    int num1, num2, maximum, minimum;

    printf("Enter two numbers: ");
    scanf("%d %d", &num1, &num2);

    maximum = max(num1, num2);
    minimum = min(num1, num2);

    printf("Maximum = %d\n", maximum);
    printf("Minimum = %d\n", minimum);

    return 0;
}

int max(int num1, int num2)
{
    if(num1 > num2)
        return num1;
    else
        return num2;
}

int min(int num1, int num2)
{
    if(num1 > num2)
        return num2;
    else
        return num1;
}
```

## Output

```text id="s4wz2x"
Enter two numbers: 25 10
Maximum = 25
Minimum = 10
```

## Result

Thus, the program was implemented and executed successfully, and the required output was obtained.

---

# Ex.No:18

## Temperature Conversion Using Functions

**Date : 15/05/2026**

## Aim

To develop a C program that converts temperatures between Celsius and Fahrenheit using functions with return values.

---

## Algorithm

### Step 1:

Start

### Step 2:

Include the standard input-output library:
`#include<stdio.h>`

### Step 3:

Declare function prototypes:

* `float celtof();`
* `float ftocel();`

### Step 4:

Enter the `main()` function.

### Step 5:

Call `celtof()` function.

### Step 6:

Inside `celtof()`:

* Read Celsius temperature
* Convert using:
  `F = (C * 9 / 5) + 32`
* Return Fahrenheit value

### Step 7:

Display Fahrenheit value.

### Step 8:

Call `ftocel()` function.

### Step 9:

Inside `ftocel()`:

* Read Fahrenheit temperature
* Convert using:
  `celsius = (f - 32) * 5 / 9`
* Return Celsius value

### Step 10:

Display Celsius value.

### Step 11:

Stop

---

## Program

```c id="n5q2kt"
#include<stdio.h>

float celtof();
float ftocel();

int main()
{
    float fahrenheit, celsius;

    fahrenheit = celtof();
    printf("Temperature in Fahrenheit = %.2f\n", fahrenheit);

    celsius = ftocel();
    printf("Temperature in Celsius = %.2f\n", celsius);

    return 0;
}

float celtof()
{
    float C, F;

    printf("Enter the temperature in Celsius: ");
    scanf("%f", &C);

    F = (C * 9 / 5) + 32;

    return F;
}

float ftocel()
{
    float f, celsius;

    printf("Enter the temperature in Fahrenheit: ");
    scanf("%f", &f);

    celsius = (f - 32) * 5 / 9;

    return celsius;
}
```

## Output

```text id="r7x3lf"
Enter the temperature in Celsius: 25
Temperature in Fahrenheit = 77.00

Enter the temperature in Fahrenheit: 98
Temperature in Celsius = 36.67
```

## Result

Thus, the program was implemented and executed successfully, and the required output was obtained.

---

# Ex.No:19

## Spiral Order Matrix Traversal

**Date : 15/05/2026**

## Aim

To build a C program to display the elements of a 2D array in spiral form, traversing the outer elements first and then moving inward in a clockwise direction, using a user-defined parameterized function without return `spiralPrint()`.

---

## Algorithm

### Step 1:

Start

### Step 2:

Include the standard input-output library:
`#include<stdio.h>`

### Step 3:

Define constants:

* `R`
* `C`

### Step 4:

Declare function:
`spiralPrint(int m, int n, int a[R][C])`

### Step 5:

Inside `spiralPrint()`:

* Initialize:

  * `k = 0`
  * `l = 0`

### Step 6:

Repeat while `k < m` and `l < n`:

#### a.

Print top row from left to right.

#### b.

Print last column from top to bottom.

#### c.

Print bottom row from right to left.

#### d.

Print first column from bottom to top.

### Step 7:

Call `spiralPrint()` from `main()`.

### Step 8:

Stop

---

## Program

```c id="f8w0ma"
#include<stdio.h>

#define R 4
#define C 4

void spiralPrint(int m, int n, int a[R][C]);

int main()
{
    int a[R][C] = {
        {1, 2, 3, 4},
        {5, 6, 7, 8},
        {9, 10, 11, 12},
        {13, 14, 15, 16}
    };

    printf("Spiral Order:\n");

    spiralPrint(R, C, a);

    return 0;
}

void spiralPrint(int m, int n, int a[R][C])
{
    int i, k = 0, l = 0;

    while(k < m && l < n)
    {
        // Print top row
        for(i = l; i < n; ++i)
        {
            printf("%d ", a[k][i]);
        }
        k++;

        // Print last column
        for(i = k; i < m; ++i)
        {
            printf("%d ", a[i][n - 1]);
        }
        n--;

        // Print bottom row
        if(k < m)
        {
            for(i = n - 1; i >= l; --i)
            {
                printf("%d ", a[m - 1][i]);
            }
            m--;
        }

        // Print first column
        if(l < n)
        {
            for(i = m - 1; i >= k; --i)
            {
                printf("%d ", a[i][l]);
            }
            l++;
        }
    }
}
```

## Output

```text id="d2l6qs"
Spiral Order:
1 2 3 4 8 12 16 15 14 13 9 5 6 7 11 10
```

## Result

Thus, the program was implemented and executed successfully, and the required output was obtained.

---

# Ex.No:20

## Convert First and Last Characters to Uppercase

**Date : 15/05/2026**

## Aim

To build a C program to convert a string such that the first and last characters, as well as the characters before and after each space, are converted to uppercase using a user-defined parameterized function without return.

---

## Algorithm

### Step 1:

Start

### Step 2:

Include the standard input-output library:
`#include<stdio.h>`

### Step 3:

Declare function:
`convertFirstCLastC(char str[])`

### Step 4:

Inside the function:

* Find string length
* Convert first character to uppercase
* Convert characters before and after spaces
* Convert last character to uppercase

### Step 5:

In `main()`:

* Read input string
* Call function
* Print modified string

### Step 6:

Stop

---

## Program

```c id="y7k1nb"
#include<stdio.h>
#include<string.h>

void convertFirstCLastC(char str[]);

int main()
{
    char str[100];

    printf("Enter a string: ");
    scanf("%[^\n]", str);

    convertFirstCLastC(str);

    printf("Modified string: %s", str);

    return 0;
}

void convertFirstCLastC(char str[])
{
    int i, len;

    len = strlen(str);

    // Convert first character to uppercase
    if(str[0] >= 'a' && str[0] <= 'z')
    {
        str[0] = str[0] - 32;
    }

    // Convert characters before and after space
    for(i = 1; i < len - 1; i++)
    {
        if(str[i] == ' ')
        {
            if(str[i - 1] >= 'a' && str[i - 1] <= 'z')
            {
                str[i - 1] = str[i - 1] - 32;
            }

            if(str[i + 1] >= 'a' && str[i + 1] <= 'z')
            {
                str[i + 1] = str[i + 1] - 32;
            }
        }
    }

    // Convert last character to uppercase
    if(str[len - 1] >= 'a' && str[len - 1] <= 'z')
    {
        str[len - 1] = str[len - 1] - 32;
    }
}
```

## Output

```text id="j4u8pc"
Enter a string: saveetha engineering college
Modified string: SaveethA EngineerinG CollegE
```

## Result

Thus, the program was implemented and executed successfully, and the required output was obtained.
