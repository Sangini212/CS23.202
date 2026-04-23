# CS23.202

# Assignment

---

# 📌 INDEX

1. [Program 1: Calculator using class](#program-1-calculator-using-class)
2. [Program 2: Addition of two distances (m, cm, mm)](#program-2-addition-of-two-distances-m-cm-mm)
3. [Program 3: Addition of two times (hr, min, sec)](#program-3-addition-of-two-times-hr-min-sec)
4. [Program 4: Addition of two distances (m and cm)](#program-4-addition-of-two-distances-m-and-cm)
5. [Program 5: Addition of two times (hr and min)](#program-5-addition-of-two-times-hr-and-min)
6. [Program 6: Reverse a 1D array](#program-6-reverse-a-1d-array)
7. [Program 7: Matrix operations](#program-7-matrix-operations)
8. [Program 8: Factorial of a number](#program-8-factorial-of-a-number)
9. [Program 9: Check palindrome number](#program-9-check-palindrome-number)
10. [Program 10: Fibonacci series](#program-10-fibonacci-series)
11. [Program 11: Armstrong number](#program-11-armstrong-number)
12. [Program 12: Prime number](#program-12-prime-number)
13. [Program 13: Print numbers using classes A, B, C](#program-13-print-numbers-using-classes-a-b-c)
14. [Program 14: Create threads using Thread class](#program-14-create-threads-using-thread-class)
15. [Program 15: Create threads using Runnable interface](#program-15-create-threads-using-runnable-interface)
16. [Program 16: Thread execution using join()](#program-16-thread-execution-using-join)
17. [Program 17: Character stream](#program-17-character-stream)
18. [Program 18: Byte stream](#program-18-byte-stream)
19. [Program 19: Copy file using character stream](#program-19-copy-file-using-character-stream)
20. [Program 20: Copy file using byte stream](#program-20-copy-file-using-byte-stream)
21. [Program 21: Buffered stream](#program-21-buffered-stream)
22. [Program 22: File handling](#program-22-file-handling)
23. [Program 23: Data stream](#program-23-data-stream)

---

# PROGRAMS

---

## Program 1: Calculator using class

```java
import java.util.Scanner;

class Calculator {
    int add(int a, int b) { return a + b; }
    int subtract(int a, int b) { return a - b; }
    int multiply(int a, int b) { return a * b; }
    int divide(int a, int b) { return a / b; }
}

public class Program1 {
    public static void main(String[] args) {
        Calculator c = new Calculator();
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter two numbers: ");
        int a = sc.nextInt();
        int b = sc.nextInt();

        System.out.println("Addition: " + c.add(a,b));
        System.out.println("Subtraction: " + c.subtract(a,b));
        System.out.println("Multiplication: " + c.multiply(a,b));
        System.out.println("Division: " + c.divide(a,b));
    }
}
```

<img src="https://github.com/user-attachments/assets/9f8119cb-6be5-4db2-8b77-0899651becca"/>

---

## Program 2: Addition of two distances (m, cm, mm)

```java
public class dist {
    public static void main(String[] args) {
        distance d1 = new distance();
        distance d2 = new distance();
        distance d3 = new distance();

        System.out.println("Enter first distance:");
        d1.input();

        System.out.println("Enter second distance:");
        d2.input();

        d3.add(d1, d2);
        d3.output();
    }
}

class distance {
    int mtr, centimtr, millimtr;

    void input() {
        Scanner sc = new Scanner(System.in);
        System.out.print("Metre: ");
        mtr = sc.nextInt();
        System.out.print("Centimetre: ");
        centimtr = sc.nextInt();
        System.out.print("Millimetre: ");
        millimtr = sc.nextInt();
    }

    void add(distance o1, distance o2) {
        millimtr = o1.millimtr + o2.millimtr;
        centimtr = o1.centimtr + o2.centimtr;
        mtr = o1.mtr + o2.mtr;

        while (millimtr >= 10) {
            centimtr++;
            millimtr -= 10;
        }

        while (centimtr >= 100) {
            mtr++;
            centimtr -= 100;
        }
    }

    void output() {
        System.out.println("Total Distance:");
        System.out.println("Metre = " + mtr);
        System.out.println("Centimetre = " + centimtr);
        System.out.println("Millimetre = " + millimtr);
    }
}
```

<img src="https://github.com/user-attachments/assets/71a074e8-02e2-493c-85a5-119452d54e33"/>

---

## Program 3: Addition of two times (hr, min, sec)

```java
import java.util.Scanner;

public class timeadd {
    public static void main(String[] args) {
        time t1 = new time();
        time t2 = new time();
        time t3 = new time();

        System.out.println("Enter first time:");
        t1.input();

        System.out.println("Enter second time:");
        t2.input();

        t3.add(t1, t2);
        t3.output();
    }
}

class time {
    int hr, min, sec;

    void input() {
        Scanner sc = new Scanner(System.in);
        System.out.print("Hours: ");
        hr = sc.nextInt();
        System.out.print("Minutes: ");
        min = sc.nextInt();
        System.out.print("Seconds: ");
        sec = sc.nextInt();
    }

    void add(time o1, time o2) {
        sec = o1.sec + o2.sec;
        min = o1.min + o2.min;
        hr = o1.hr + o2.hr;

        while (sec >= 60) {
            min++;
            sec -= 60;
        }

        while (min >= 60) {
            hr++;
            min -= 60;
        }
    }

    void output() {
        System.out.println("Total Time:");
        System.out.println("Hours = " + hr);
        System.out.println("Minutes = " + min);
        System.out.println("Seconds = " + sec);
    }
}
```

<img src="https://github.com/user-attachments/assets/46e0d372-66ac-4b5a-afdc-f7b75c539690"/>

---

## Program 4: Addition of two distances (m and cm)

```java
class Distance2 {
    int m, cm;

    Distance2(int m, int cm) {
        this.m = m;
        this.cm = cm;
    }

    Distance2 add(Distance2 d) {
        int cm = this.cm + d.cm;
        int m = this.m + d.m + cm/100;
        cm = cm % 100;

        return new Distance2(m, cm);
    }

    void display() {
        System.out.println(m + " m " + cm + " cm");
    }

    public static void main(String[] args) {
        Distance2 d1 = new Distance2(3,60);
        Distance2 d2 = new Distance2(4,80);

        Distance2 result = d1.add(d2);
        result.display();
    }
}
```

<img src="https://github.com/user-attachments/assets/d8518bb2-557c-43dd-b29d-290cb93b7b9d"/>

---

---

## Program 5: Addition of two times (hr and min)

```java
class Time2 {
    int hr, min;

    Time2(int hr, int min) {
        this.hr = hr;
        this.min = min;
    }

    Time2 add(Time2 t) {
        int min = this.min + t.min;
        int hr = this.hr + t.hr + min/60;
        min = min % 60;

        return new Time2(hr, min);
    }

    void display() {
        System.out.println(hr + " hr " + min + " min");
    }

    public static void main(String[] args) {
        Time2 t1 = new Time2(2,50);
        Time2 t2 = new Time2(3,40);

        Time2 result = t1.add(t2);
        result.display();
    }
}
```

<img src="https://github.com/user-attachments/assets/977a2056-442e-4b47-856b-4fb373d356ba" />

---

## Program 6: Reverse a 1D array

```java
class ReverseArray {

    void reverse(int arr[]) {
        int n = arr.length;

        for(int i=n-1;i>=0;i--) {
            System.out.print(arr[i] + " ");
        }
    }

    public static void main(String[] args) {
        ReverseArray r = new ReverseArray();

        int arr[] = {1,2,3,4,5};
        r.reverse(arr);
    }
}
```

<img src="https://github.com/user-attachments/assets/242e73b3-519f-4299-b8c0-f70483377aa6" />

---

## Program 7: Matrix operations

```java
class MatrixOperation {

    void transpose(int a[][], int r, int c) {
        System.out.println("Transpose:");
        for(int i=0;i<c;i++) {
            for(int j=0;j<r;j++) {
                System.out.print(a[j][i] + " ");
            }
            System.out.println();
        }
    }

    void sumRows(int a[][], int r, int c) {
        for(int i=0;i<r;i++) {
            int sum=0;
            for(int j=0;j<c;j++) {
                sum += a[i][j];
            }
            System.out.println("Row "+i+" sum = "+sum);
        }
    }

    void sumColumns(int a[][], int r, int c) {
        for(int i=0;i<c;i++) {
            int sum=0;
            for(int j=0;j<r;j++) {
                sum += a[j][i];
            }
            System.out.println("Column "+i+" sum = "+sum);
        }
    }

    public static void main(String[] args) {
        MatrixOperation m = new MatrixOperation();

        int a[][] = {
            {1,2,3},
            {4,5,6},
            {7,8,9}
        };

        m.transpose(a,3,3);
        m.sumRows(a,3,3);
        m.sumColumns(a,3,3);
    }
}
```

<img src="https://github.com/user-attachments/assets/d9998fec-aacf-4217-84c6-59604c2d1bb9" />

---

## Program 8: Factorial of a number

```java
import java.util.Scanner;

public class Factorial {
    public static void main(String[]args){
        
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number:");
        int n = sc.nextInt();
        
        FactorialNumber Num1 = new FactorialNumber(n);
        Num1.calculate();
        
    }
}

class FactorialNumber{
    
    int num;
    int result = 1;
    FactorialNumber(int n){
        num = n;
    }
    
    void calculate(){
        while(num!=0){
            result*=num;
            num = num-1;
        }
        System.out.println("Factorial = "+result);
    }
}
```

<img src="https://github.com/user-attachments/assets/ff89f98c-7603-4096-be52-77791f400fba" />

---

## Program 9: Check palindrome number

```java
import java.util.Scanner;
public class Palindrome {
    public static void main(String[]args){
        
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the number:");
        int n = sc.nextInt();
        
        PalindromeNumber p1 = new PalindromeNumber(n);
        p1.check();
    } 
}
class PalindromeNumber{
    
    int num,num1;
    int result = 0;
    int remainder;
    
    PalindromeNumber(int n)
    {
        num = n;
    }
    
    void check()
    {
        num1 = num;
        while(num1!=0){
            remainder = num1%10;
            result = (result*10)+remainder;
            num1 = num1/10;
        }
        if(result == num){
            System.out.println("The number is palindromic");
        }
        else{
             System.out.println("The number is not a palindromic number");
        }
    }
}
```

<img src="https://github.com/user-attachments/assets/d480f0ba-b918-4044-865a-32c1d327c248" />

---

## Program 10: Fibonacci series

```java
import java.util.Scanner;

public class Fibonacci {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of terms: ");
        int num = sc.nextInt();

        FibonacciSeries obj = new FibonacciSeries(num);
        obj.printSeries();
    }
}

class FibonacciSeries {
    int n;

    FibonacciSeries(int n) {
        this.n = n;
    }

    void printSeries() {
        int a = 0;
        int b = 1;
        int c;

        System.out.print("Fibonacci Series: ");

        for (int i = 1; i <= n; i++) {
            System.out.print(a + " ");
            c = a + b;
            a = b;
            b = c;
        }
    }
}
```

<img src="https://github.com/user-attachments/assets/29c3bfdb-c933-4c5a-aba8-0c65fa52eac1" />

---

## Program 11: Armstrong number

```java
class Amstrong {

    boolean check(int n) {
        int original = n;
        int sum = 0;

        while (n != 0) {
            int digit = n % 10;
            sum = sum + (digit * digit * digit);
            n = n / 10;
        }

        if (sum == original)
            return true;
        else
            return false;
    }

    public static void main(String[] args) {
        Amstrong obj = new Amstrong();
        int num = 153;

        if (obj.check(num))
            System.out.println(num + " is an Armstrong number");
        else
            System.out.println(num + " is not an Armstrong number");
    }
}
```

<img src="https://github.com/user-attachments/assets/cdf18da4-97c3-438b-81a7-b3654951b039" />

---

## Program 12: Prime number

```java
class PrimeNumber {

    boolean check(int n) {
        if(n <= 1)
            return false;

        for(int i = 2; i <= n/2; i++) {
            if(n % i == 0)
                return false;
        }

        return true;
    }

    public static void main(String[] args) {
        PrimeNumber obj = new PrimeNumber();

        int num = 7;

        if(obj.check(num))
            System.out.println(num + " is Prime number");
        else
            System.out.println(num + " is not Prime number");
    }
}
```

<img src="https://github.com/user-attachments/assets/bb406d67-e5cd-44b0-ac41-b64cfc358eab" />

---

## Program 13: Print numbers using classes A, B, C

```java
class A {
    void fun() {
        for(int i = 1; i <= 100; i++) {
            System.out.println("a" + i);
        }
    }
}

class B {
    void fun() {
        for(int i = 1; i <= 100; i++) {
            System.out.println("b" + i);
        }
    }
}

class C {
    void fun() {
        for(int i = 1; i <= 100; i++) {
            System.out.println("c" + i);
        }
    }
}

public class MainClass {
    public static void main(String[] args) {
        A obj1 = new A();
        B obj2 = new B();
        C obj3 = new C();

        obj1.fun();
        obj2.fun();
        obj3.fun();
    }
}
```

---

## Program 14: Create threads using Thread class

```java
package com.mycompany.sangini;

class X extends Thread {
    public void run() {
        for(int i = 1; i <= 100; i++) {
            System.out.println("x" + i);
            try { sleep(100); } catch(Exception e) {}
        }
    }
}

class Y extends Thread {
    public void run() {
        for(int i = 1; i <= 100; i++) {
            System.out.println("y" + i);
            try { sleep(100); } catch(Exception e) {}
        }
    }
}

class Z extends Thread {
    public void run() {
        for(int i = 1; i <= 100; i++) {
            System.out.println("z" + i);
            try { sleep(100); } catch(Exception e) {}
        }
    }
}

public class MainThread {
    public static void main(String[] args) {
        X t1 = new X();
        Y t2 = new Y();
        Z t3 = new Z();

        t1.start();
        t2.start();
        t3.start();

        try {
            Thread.sleep(1000);
            t1.stop();
        } catch(Exception e) {}
    }
}
```

---

## Program 15: Create threads using Runnable interface

```java
package com.mycompany.sangini;

class Alpha implements Runnable {
    public void run() {
        for(int i = 1; i <= 100; i++) {
            System.out.println("alpha" + i);
            try { Thread.sleep(50); } catch(Exception e) {}
        }
    }
}

class Beta implements Runnable {
    public void run() {
        for(int i = 1; i <= 100; i++) {
            System.out.println("beta" + i);
            try { Thread.sleep(50); } catch(Exception e) {}
        }
    }
}

class Gamma implements Runnable {
    public void run() {
        for(int i = 1; i <= 100; i++) {
            System.out.println("gamma" + i);
            try { Thread.sleep(50); } catch(Exception e) {}
        }
    }
}

public class RunnableProgram {
    public static void main(String[] args) {

        Thread t1 = new Thread(new Alpha());
        Thread t2 = new Thread(new Beta());
        Thread t3 = new Thread(new Gamma());

        t1.start();
        t2.start();
        t3.start();

        try {
            Thread.sleep(500);
            t1.stop();
        } catch(Exception e) {}
    }
}
```

---

## Program 16: Thread execution using join()

```java
package com.mycompany.sangini;

class AA implements Runnable {
    public void run() {
        for(int i = 1; i <= 100; i++) {
            System.out.println("A: " + i);
        }
    }
}

class BB implements Runnable {
    public void run() {
        for(int i = 1; i <= 100; i++) {
            System.out.println("B: " + i);
        }
    }
}

class CC implements Runnable {
    public void run() {
        for(int i = 1; i <= 100; i++) {
            System.out.println("C: " + i);
        }
    }
}

public class JoinProgram {
    public static void main(String[] args) throws Exception {

        Thread t1 = new Thread(new AA());
        Thread t2 = new Thread(new BB());
        Thread t3 = new Thread(new CC());

        t1.start();
        t1.join();

        t2.start();
        t2.join();

        t3.start();
        t3.join();
    }
}
```

---

## Program 17: Character stream

```java
package com.mycompany.sangini;
import java.io.*;

public class CharStreamExample {
    public static void main(String[] args) {
        try {
            FileWriter fw = new FileWriter("char.txt");
            fw.write("Hello Java");
            fw.close();

            FileReader fr = new FileReader("char.txt");
            int ch;

            while ((ch = fr.read()) != -1) {
                System.out.print((char) ch);
            }

            fr.close();
        } catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

---

## Program 18: Byte stream

```java
package com.mycompany.sangini;
import java.io.*;

public class ByteStreamExample {
    public static void main(String[] args) throws Exception {
        FileOutputStream fos = new FileOutputStream("b.txt");
        fos.write("Hello".getBytes());
        fos.close();

        FileInputStream fis = new FileInputStream("b.txt");
        int i;
        while((i=fis.read())!=-1)
            System.out.print((char)i);
        fis.close();
    }
}
```

---

## Program 19: Copy file using character stream

```java
package com.mycompany.sangini;
import java.io.*;

public class CopyChar {
    public static void main(String[] args) throws Exception {

        FileWriter fw = new FileWriter("a.txt");
        fw.write("Hello from Java");
        fw.close();

        FileReader fr = new FileReader("a.txt");
        FileWriter fw2 = new FileWriter("b.txt");

        int ch;
        while ((ch = fr.read()) != -1) {
            fw2.write(ch);
        }

        fr.close();
        fw2.close();

        System.out.println("File copied successfully");
    }
}
```

---

## Program 20: Copy file using byte stream

```java
package com.mycompany.sangini;
import java.io.*;

public class CopyByte {
    public static void main(String[] args) throws Exception {
        FileInputStream fis = new FileInputStream("a.txt");
        FileOutputStream fos = new FileOutputStream("b.txt");
        int i;
        while((i=fis.read())!=-1)
            fos.write(i);
        fis.close();
        fos.close();
    }
}
```

---

## Program 21: Buffered stream

```java
package com.mycompany.sangini;
import java.io.*;

public class BufferedExample {
    public static void main(String[] args) throws Exception {
        BufferedWriter bw = new BufferedWriter(new FileWriter("file.txt"));
        bw.write("Hello");
        bw.close();

        BufferedReader br = new BufferedReader(new FileReader("file.txt"));
        String s;
        while((s=br.readLine())!=null)
            System.out.println(s);
        br.close();
    }
}
```

---

## Program 22: File handling

```java
package com.mycompany.sangini;
import java.io.*;

public class FileExample {
    public static void main(String[] args) throws Exception {
        File f = new File("test.txt");
        if(f.createNewFile())
            System.out.println("Created");
        else
            System.out.println("Exists");
    }
}
```

---

## Program 23: Data stream

```java
package com.mycompany.sangini;
import java.io.*;

public class DataStreamExample {
    public static void main(String[] args) throws Exception {
        DataOutputStream dos = new DataOutputStream(new FileOutputStream("data.txt"));
        dos.writeInt(10);
        dos.close();

        DataInputStream dis = new DataInputStream(new FileInputStream("data.txt"));
        System.out.println(dis.readInt());
        dis.close();
    }
}
```

---

