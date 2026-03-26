## PPA 1

Implement the code as instructed in the comments, such that it satisfies the given test cases.

**question**

```
import java.util.*;
interface Searchable{
    public int search(int start_index, Object key);
}
class Char{
    private char c;
    public Char(char c_) {
        c = c_;
    }
    public boolean equals(Object d) {
//implement equals() for Char
    }
}
class CharArray implements Searchable{
    private Char[] carr;
    public CharArray(Char[] carr_){
        carr = carr_;
    }
    public int search(int start_index, Object key) {
        //search the key in array carr from the index start_index
        //if the key found, return index of the first occurrence of the key
        //else return -1
    }
}

class FrequencyCounter{
    public static int getFrequency(Searchable ob, Object key){
        if (ob instanceof CharArray) {
            //count occurrences of the key in ob using search function
        }
        else
            return 0;
    }
}
class FClass{
    public static void main(String[] args) {
        String str;
        char c;
        Scanner sc = new Scanner(System.in);
        str = sc.nextLine();
        c = sc.next().charAt(0);
        Char key = new Char(c);
        Char[] cA = new Char[str.length()]; 
        for(int i = 0; i < str.length(); i++) {
            cA[i] = new Char(str.charAt(i));
        }
        CharArray caObj = new CharArray(cA);
        System.out.println(FrequencyCounter.getFrequency(caObj, key));
    }
}
```

## Test Case 1

Input
```
i can write java program
a
```
Expected Output
```
4
```
## Test Case 2
Input
```
you should learn java
x
```
Expected Output
```
0
```

## Submission Results (private case)
Test Case 1
Input
```
java is an object oriented programming language
o
```
Expected Output
```
3

```

## solution for ppa 1
```
import java.util.*;
interface Searchable{
    public int search(int start_index, Object key);
}
class Char{
    private char c;
    public Char(char c_) {
        c = c_;
    }
    public boolean equals(Object d) {
if (d instanceof Char) 
            if (((Char) d).c == this.c)
                return true;
        return false;
    }
}
class CharArray implements Searchable{
    private Char[] carr;
    public CharArray(Char[] carr_){
        carr = carr_;
    }
    public int search(int start_index, Object key) {
        for(int i = start_index; i < carr.length; i++) {
            if (carr[i].equals(key))
                return i;
        }
        return -1;
    }
}

class FrequencyCounter{
    public static int getFrequency(Searchable ob, Object key){
        if (ob instanceof CharArray) {
            int findIndex = -1;
            int c = -1;
            do {
                c++;
                findIndex = ob.search(findIndex + 1, (Char)key);
            }while(findIndex != -1);
            return c;
        }
        else
            return 0;
    }
}
class FClass{
    public static void main(String[] args) {
        String str;
        char c;
        Scanner sc = new Scanner(System.in);
        str = sc.nextLine();
        c = sc.next().charAt(0);
        Char key = new Char(c);
        Char[] cA = new Char[str.length()]; 
        for(int i = 0; i < str.length(); i++) {
            cA[i] = new Char(str.charAt(i));
        }
        CharArray caObj = new CharArray(cA);
        System.out.println(FrequencyCounter.getFrequency(caObj, key));
    }
}
```
## ppa 1 solution

```
import java.util.*;
interface Searchable{
    public int search(int start_index, Object key);
}
class Char{
    private char c;
    public Char(char c_) {
        c = c_;
    }
    public boolean equals(Object d) {
if (d instanceof Char) 
            if (((Char) d).c == this.c)
                return true;
        return false;
    }
}
class CharArray implements Searchable{
    private Char[] carr;
    public CharArray(Char[] carr_){
        carr = carr_;
    }
    public int search(int start_index, Object key) {
        for(int i = start_index; i < carr.length; i++) {
            if (carr[i].equals(key))
                return i;
        }
        return -1;
    }
}

class FrequencyCounter{
    public static int getFrequency(Searchable ob, Object key){
        if (ob instanceof CharArray) {
            int findIndex = -1;
            int c = -1;
            do {
                c++;
                findIndex = ob.search(findIndex + 1, (Char)key);
            }while(findIndex != -1);
            return c;
        }
        else
            return 0;
    }
}
class FClass{
    public static void main(String[] args) {
        String str;
        char c;
        Scanner sc = new Scanner(System.in);
        str = sc.nextLine();
        c = sc.next().charAt(0);
        Char key = new Char(c);
        Char[] cA = new Char[str.length()]; 
        for(int i = 0; i < str.length(); i++) {
            cA[i] = new Char(str.charAt(i));
        }
        CharArray caObj = new CharArray(cA);
        System.out.println(FrequencyCounter.getFrequency(caObj, key));
    }
}
```

## PPA 2

Both the Voter and EVM classes must be created in such a way that they enforce the existence of only a single instance at a time. Each Voter object must be mapped with a unique EVM object and vice versa. A Voter must be allocated an EVM and then the voting process should start, once voting is completed that particular EVM should be freed and the next voter should be called.
Again a new EVM must be allocated to the next voter like previously and the process continues till all the voters cast their votes.

**question**

```
import java.util.Scanner;	

class Voter{	

// Define appropriate variables for implementing singleton behaviour
    // in accordance with the given coded parts and sample output

    private Voter() {                           
		        current_voter_count++;					
    }

    public static Voter getVoter() {
        //implement singleton behaviour
    }

    public void firstVoter(){
		        if(new_voter != null) {
			            EVM new_machine = EVM.getEVM(new_voter);
			            new_machine.startVoting();
		        }
    }

    public void callNewVoter() {
        // Write code to setup a new EVM object for the new voter
    
        //Ignore the following 6 lines of code
        //but do not delete this code in your submission 
//======================================================================== 
        try {
		            EVM x = EVM.getEVM(null);
			            x.startVoting();
		        }catch(NullPointerException e) {
			            System.out.println("EVM is Singleton");
	        }
//========================================================================  	
	        // Resume writing your code here
	   
	        // Hint: Write code to start voting for the new user on the new EVM
    }
}

class EVM{

    // Define appropriate variables for implementing singleton behaviour
    // in accordance with the given coded parts and sample output


        private EVM(Voter v) {
            current_voter = v;
		            evm_count++;
        }
        public static EVM getEVM(Voter v) {
            // Implement singleton behaviour
        }

        public void startVoting() {
            // Complete voting for the current voter and call the next voter
            // Hint : Use callback here
        }
}


public class Election{
	        public static void main(String args[]) {
		            Scanner s = new Scanner(System.in);
		            Voter.total_no_of_voters =  s.nextInt();
		            // Assume input is always non zero
		            Voter v = Voter.getVoter();
		
		            //Trying to create another voter when one voter is in the middle of 
		            //voting process, students can ignore this try-catch block of code
		
				            try {
					                Voter x = Voter.getVoter();
					                x.callNewVoter();
				            } catch(NullPointerException e) {
					                System.out.println("Voter is Singleton");
				            }
				
		            //Starting the first vote of the day
		                v.firstVoter();
	        }
}
```

## Test Case 1

Input
```
4
```
Expected Output
```
Voter is Singleton
voting under process on EVM number 1
Voting completed for voter 1
EVM is Singleton
voting under process on EVM number 2
Voting completed for voter 2
EVM is Singleton
voting under process on EVM number 3
Voting completed for voter 3
EVM is Singleton
voting under process on EVM number 4
Voting completed for voter 4
```
## Test Case 2
Input
```
3
```
Expected Output
```
Voter is Singleton
voting under process on EVM number 1
Voting completed for voter 1
EVM is Singleton
voting under process on EVM number 2
Voting completed for voter 2
EVM is Singleton
voting under process on EVM number 3
Voting completed for voter 3
```

## Submission Results (private case)
Test Case 1
Input
```
6

```
Expected Output
```
Voter is Singleton
voting under process on EVM number 1
Voting completed for voter 1
EVM is Singleton
voting under process on EVM number 2
Voting completed for voter 2
EVM is Singleton
voting under process on EVM number 3
Voting completed for voter 3
EVM is Singleton
voting under process on EVM number 4
Voting completed for voter 4
EVM is Singleton
voting under process on EVM number 5
Voting completed for voter 5
EVM is Singleton
voting under process on EVM number 6
Voting completed for voter 6

```

## ppa 2 solution
```
import java.util.Scanner;	

class Voter{	

public static int total_no_of_voters;		
	    private static Voter new_voter;             
	    private static int current_voter_count = 0; 
	
	    private Voter() {                           
		        current_voter_count++;					
	    }
	    public static Voter getVoter() {			
		        if(new_voter == null) {					
			            new_voter = new Voter();
			            return new_voter;
		        }
		        else {
			            return null;
		        }
	    }											
	
	    public void firstVoter(){
		        if(new_voter != null) {
			            EVM new_machine = EVM.getEVM(new_voter);
			            new_machine.startVoting();
		        }
    }
			
    public void callNewVoter() {
        // This statement finishes off the voting process for previous voter
        new_voter = null; 
        
		        System.out.println("Voting completed for voter " + 
		        current_voter_count);
		        
		        // Calling new voter and allocating EVM for him
		        if(current_voter_count < total_no_of_voters) {
			            
			            //EVM - Voter mapping is bijective
			            EVM new_machine = EVM.getEVM(getVoter());
			
			            try {
				                EVM x = EVM.getEVM(null);
				                x.startVoting();
			            } catch(NullPointerException e) {
				                System.out.println("EVM is Singleton");
			            }
			            new_machine.startVoting();
		        }
	    }
}
class EVM{
	    private Voter current_voter;
	    private static int evm_count = 0;
	    private static EVM current_evm;
	
	    private EVM(Voter v) {
		        current_voter = v;
		        evm_count++;
	    }
	    public static EVM getEVM(Voter v) {
		        if(current_evm == null) {
			            current_evm = new EVM(v);
			            return current_evm;	
			            //this particular evm is binded to the current voter
		        }
		        else
			            return null;
			 
	    }
	    public void startVoting() {
		
		        System.out.println("voting under process on EVM number "+ evm_count);
		        current_evm = null; 	//voting on current evm is done  
		        current_voter.callNewVoter(); 
	    }
}

public class Election{
	        public static void main(String args[]) {
		            Scanner s = new Scanner(System.in);
		            Voter.total_no_of_voters =  s.nextInt();
		            // Assume input is always non zero
		            Voter v = Voter.getVoter();
		
		            //Trying to create another voter when one voter is in the middle of 
		            //voting process, students can ignore this try-catch block of code
		
				            try {
					                Voter x = Voter.getVoter();
					                x.callNewVoter();
				            } catch(NullPointerException e) {
					                System.out.println("Voter is Singleton");
				            }
				
		            //Starting the first vote of the day
		                v.firstVoter();
	        }
}
```

## GRPA 1

Create an abstract class StringOperations that has the following abstract methods:
    String reverse(String s)
    int vowelCount(String s)

Create StringReverse class that extends StringOperations class but defines only String reverse(String s) method. It reverses the string which is passed as parameter and returns the reversed string.
Create UpdatedStrings class that extends StringReverse class and defines int vowelCount(String s) method.  It counts the vowels in the string which is passed as parameter and returns the count.
**question**

```
import java.util.*;
abstract class StringOperations{
  public abstract String reverse(String s);
  public abstract int vowelCount(String s);
}
//Fill the code here
class Example {
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    String s = sc.next();
    UpdatedStrings str = new UpdatedStrings();
    System.out.println("Reverse of "+ s + " is "+ str.reverse(s));
    System.out.println("Vowel count of "+ s + " is "+ str.vowelCount(s));
  }
}
```

## Test Case 1

Input
```
Java
```
Expected Output
```
Reverse of Java is avaJ
Vowel count of Java is 2
```
## Test Case 2
Input
```
Madam
```
Expected Output
```
Reverse of Madam is madaM
Vowel count of Madam is 2
```

## Submission Results (private case)
Test Case 1
Input
```
Carbondioxide
```
Expected Output
```
Reverse of Carbondioxide is edixoidnobraC
Vowel count of Carbondioxide is 6
```


## GRPA 1 solution

```
import java.util.*;
abstract class StringOperations{
  public abstract String reverse(String s);
  public abstract int vowelCount(String s);
}
abstract class StringReverse extends StringOperations{
  public String reverse(String s){
    String s1 = "";
    for(int i = s.length() - 1; i >= 0; i--){
      s1 = s1 + s.charAt(i);
    }
    return s1;
  }
}

class UpdatedStrings extends StringReverse{
  public int vowelCount(String s){
    int count = 0;
    char[] arr = {'a','e','i','o','u'};
    for(int i = 0; i < s.length(); i++){
      for(int j = 0; j <arr.length; j++){
        if(s.charAt(i) == arr[j]){
          count = count + 1; 
        }
      }
    }
    return count;
  }
}
class Example {
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    String s = sc.next();
    UpdatedStrings str = new UpdatedStrings();
    System.out.println("Reverse of "+ s + " is "+ str.reverse(s));
    System.out.println("Vowel count of "+ s + " is "+ str.vowelCount(s));
  }
}
```

## GRPA 2


Consider the following Java program. 
Implement the code as instructed in the comment, such that it satisfies the given test cases.
**question**

```
import java.util.*;

interface Iterator{
    public boolean has_next();
    public Object get_next();
}

class Sequence{
    private final int maxLimit = 80;
    private SeqIterator _iter = null;
    int[] iArr; 
    int size;
//implement the parameterized constructor to initialize size
//implement addTo(elem) to add an int elem to the sequence 
//implement get_Iterator() to return Iterator object
 
    private class SeqIterator implements Iterator{
        int indx;
        public SeqIterator(){
            indx = -1;
        }
        //implement has_next()
        //implement get_next()
    }
}

class FClass{
    public static void main(String[] args) {
        Sequence sObj = new Sequence(5);
        Scanner sc = new Scanner(System.in); 
        for(int i = 0; i < 5; i++) {
            sObj.addTo(sc.nextInt());
        }
        Iterator i = sObj.get_Iterator();
        while(i.has_next())
            System.out.print(i.get_next() + ", ");
    }
}
```

## Test Case 1

Input
```
1 2 3 4 5
```
Expected Output
```

1, 2, 3, 4, 5,
```
## Test Case 2
Input
```
50 40 30 20 10
```
Expected Output
```

50, 40, 30, 20, 10,
```

## Submission Results (private case)
Test Case 1
Input
```
1 2 3 5 8
```
Expected Output
```

1, 2, 3, 5, 8,
```

## GRPA 2 solution

```
import java.util.*;

interface Iterator{
    public boolean has_next();
    public Object get_next();
}

class Sequence{
    private final int maxLimit = 80;
    private SeqIterator _iter = null;
    int[] iArr; 
    int size;
public Sequence(int size_) {
        iArr = new int[80];
        size = 0;
    }
	
    public void addTo(int elem) {
        iArr[size] = elem;
        size++;
    }
	
    public Iterator get_Iterator() {
        _iter = new SeqIterator();
        return _iter;
    }
    private class SeqIterator implements Iterator{
        int indx;
        public SeqIterator(){
            indx = -1;
        }
        public boolean has_next() {
            if(indx < size - 1)
                return true;
            return false;
        }
        public Object get_next() {
            return iArr[++indx];
        }
    }
}

class FClass{
    public static void main(String[] args) {
        Sequence sObj = new Sequence(5);
        Scanner sc = new Scanner(System.in); 
        for(int i = 0; i < 5; i++) {
            sObj.addTo(sc.nextInt());
        }
        Iterator i = sObj.get_Iterator();
        while(i.has_next())
            System.out.print(i.get_next() + ", ");
    }
}
```
