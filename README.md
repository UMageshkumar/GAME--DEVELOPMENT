# EX 3 : Circle Drawing Algorithm
### NAME: U MAGESHKUMAR
### REG NO: 212224240085

**AIM :**

To  implement the Bresenham’s  algorithm for circle using a c coding.


**ALGORITHM :**

Step 1 : Start.
    
Step 2 : Initialize the graphics header files and functions.
   
Step 3 : Declare the required variables and functions.
 
Step 4 : Get the co-ordinates and radius of the circle.

Step 5 : Draw the circle using the algorithm.

Step  6 : Display the output.
  
Step 7 : stop.

**Program :**
```
#include <stdio.h>
#include <conio.h>
#include <graphics.h>
#include <math.h>

void plotpoints(int xcenter, int ycenter, int x, int y);

int main() 
{
    int gd = DETECT, gm;
    int xcenter, ycenter, radius;
    int p, x, y;

    initgraph(&gd, &gm, "C:\\Turboc3\\BGI");

    printf("Enter the Radius Value:\n");
    scanf("%d", &radius);

    printf("Enter the xcenter and ycenter Values:\n");
    scanf("%d%d", &xcenter, &ycenter);

    x = 0;
    y = radius;
    p = 1 - radius;

    plotpoints(xcenter, ycenter, x, y);

    while (x < y)
    {
        x++;
        if (p < 0)
            p = p + 2 * x + 1;
        else
        {
            y--;
            p = p + 2 * (x - y) + 1;
        }
        plotpoints(xcenter, ycenter, x, y);
    }

    getch();
    closegraph();
    return 0;
}

void plotpoints(int xcenter, int ycenter, int x, int y)
{
    putpixel(xcenter + x, ycenter + y, WHITE);
    putpixel(xcenter - x, ycenter + y, WHITE);
    putpixel(xcenter + x, ycenter - y, WHITE);
    putpixel(xcenter - x, ycenter - y, WHITE);
    putpixel(xcenter + y, ycenter + x, WHITE);
    putpixel(xcenter - y, ycenter + x, WHITE);
    putpixel(xcenter + y, ycenter - x, WHITE);
    putpixel(xcenter - y, ycenter - x, WHITE);
}

```



**Output :**
![Screenshot (32)](https://github.com/user-attachments/assets/c2d1e188-7c0e-4885-91ef-5020d75534c7)

**Result :**
Successfully implemented the Bresenham’s  algorithm for circle using a c coding.
