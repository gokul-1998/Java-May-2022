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
      |

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
