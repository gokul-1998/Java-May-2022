## PPA 1

Complete the program according to the instructions provided in the comments such that the program satisfies the given test cases.

**question**

```
import java.util.*;
class Rectangle{
    int w;    //width
    int h;    //height
//LINE-1: write the function setw(int) to initialize w
	
//LINE-2: write the function seth(int) to initialize h
	
//LINE-3: write the function area() to return area of rectangle
}
public class FClass{
	public static void main(String[] args) {
        Scanner sc= new Scanner(System.in);
        int w = Integer.parseInt(sc.nextLine());
        int h = Integer.parseInt(sc.nextLine());
        Rectangle r = new Rectangle();
        r.setw(w);
        r.seth(h);
        int area = r.area();
        System.out.print(area);
    }
}
```

## Test Case 1

Input
```
10
20
```
Expected Output
```
200
```
## Test Case 2
Input
```
100
50
```
Expected Output
```
5000
```

## Submission Results (private case)
Test Case 1
Input
```
25
4
```
Expected Output
```
100
```

## PPA 2

Write a program to accept a string input from user and print the characters at even indices.

**question**

```
import java.util.*;
class FClass {
  
  public static void main(String[] args){
    Scanner sc = new Scanner(System.in);
    String s1 = sc.next();
    evenDisplay(s1);
  }
//Define evenDisplay(String) method here
}
```

## Test Case 1

Input
```
hii
```
Expected Output
```
hi
```
## Test Case 2
Input
```
Microsoft
```
Expected Output
```

Mcoot
```

## Submission Results (private case)
Test Case 1
Input
```
Generates
```
Expected Output
```

Gnrts
```

Test Case 2
Input
```
pneumonoultramicroscopicsilicovolcanoconiosis

```
Expected Output
```

pemnutairsoislcvlaooiss
```

## PPA 3

Write a program to find the sum of the following series up to n terms.
![](2023-06-20-20-38-52.png)
**question**

```
import java.util.*;
public class SeriesSum {
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    int n = sc.nextInt();
//Fill your code here
System.out.println(sum);
    
  }
}
```

## Test Case 1

Input
```
2
```
Expected Output
```
6
```
## Test Case 2
Input
```
3
```
Expected Output
```
20
```

## Submission Results (private case)
Test Case 1
Input
```
34
```
Expected Output
```
124950
```

