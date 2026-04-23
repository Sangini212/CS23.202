# CS23.202
# Assignment
[Program 1: Class with add, subtract, multiply, divide](#Program1)
## Program 1
```import java.util.Scanner;

class Calculator {
    int add(int a, int b) {
        return a + b;
    }

    int subtract(int a, int b) {
        return a - b;
    }

    int multiply(int a, int b) {
        return a * b;
    }

    int divide(int a, int b) {
        return a / b;
    }
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
<img width="524" height="225" alt="image" src="https://github.com/user-attachments/assets/9f8119cb-6be5-4db2-8b77-0899651becca" />

[Program 2: Addition of two distances (m, cm, mm)](#Program2)
## Program 2
```

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

    // convert millimetre to centimetre
    while (millimtr >= 10) {
        centimtr++;
        millimtr -= 10;
    }

    // convert centimetre to metre
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

<img width="715" height="317" alt="image" src="https://github.com/user-attachments/assets/71a074e8-02e2-493c-85a5-119452d54e33" />

[Program 3:Addition of two times (hr, min, sec)](#Program3)
## Program 3
```
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

        // seconds to minutes
        while (sec >= 60) {
            min++;
            sec -= 60;
        }

        // minutes to hours
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
<img width="626" height="323" alt="image" src="https://github.com/user-attachments/assets/46e0d372-66ac-4b5a-afdc-f7b75c539690" />

[Program 4:Addition of two distances (m and cm)](#Program4)
## Program 4
```
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

<img width="523" height="151" alt="image" src="https://github.com/user-attachments/assets/d8518bb2-557c-43dd-b29d-290cb93b7b9d" />

[Program 5:Addition of two distances (m and cm)](#Program5)
## Program 5
```
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

<img width="537" height="150" alt="image" src="https://github.com/user-attachments/assets/977a2056-442e-4b47-856b-4fb373d356ba" />

[Program 6:Reverse a 1D array](#Program6)
## Program 6
```
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
<img width="534" height="144" alt="image" src="https://github.com/user-attachments/assets/242e73b3-519f-4299-b8c0-f70483377aa6" />

[Program 7:Matrix operations](#Program7)
## Program 7
```
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
<img width="520" height="296" alt="image" src="https://github.com/user-attachments/assets/d9998fec-aacf-4217-84c6-59604c2d1bb9" />

[Program 8:Convert C programs to OOP](#Factorial)
## Factorial
```
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

<img width="512" height="156" alt="image" src="https://github.com/user-attachments/assets/ff89f98c-7603-4096-be52-77791f400fba" />

[Palindrome](#Palindrome)
## Palindrome
```
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
<img width="515" height="173" alt="image" src="https://github.com/user-attachments/assets/d480f0ba-b918-4044-865a-32c1d327c248" />

[Fabonacci](#Fabonacci)
## Fabonacci
```
import java.util.Scanner;

public class Fibonacci {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of terms: ");
        int num = sc.nextInt();

        FibonacciSeries obj = new FibonacciSeries(num); // object creation
        obj.printSeries(); // method call
    }
    
}

class FibonacciSeries {
    int n;

    // Constructor
    FibonacciSeries(int n) {
        this.n = n;
    }

    // print Fibonacci series
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
<img width="517" height="165" alt="image" src="https://github.com/user-attachments/assets/29c3bfdb-c933-4c5a-aba8-0c65fa52eac1" />

[Amstrong](#Amstrong)
## Amstrong 
```
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

<img width="540" height="132" alt="image" src="https://github.com/user-attachments/assets/cdf18da4-97c3-438b-81a7-b3654951b039" />

[Prime Number](#Primenumber)
## Prime Number
```
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

<img width="525" height="156" alt="image" src="https://github.com/user-attachments/assets/bb406d67-e5cd-44b0-ac41-b64cfc358eab" />


[Program 9: Write a Java program that contains three classes. Each class should have a method named fun() which prints numbers from 1 to 100 along with the class name as a prefix. For example, if the class name is A, the output should be a1, a2, a3, …, a100; if the class name is B, the output should be b1, b2, b3, …, b100, and similarly for class C.
Create objects of all the classes in the main class and call the fun() method for each class to display the output.](#Program9)
## Program 9
```class A {
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
<img width="304" height="733" alt="image" src="https://github.com/user-attachments/assets/7963316c-533c-46f9-833f-1587866eeb02" />
<img width="316" height="788" alt="image" src="https://github.com/user-attachments/assets/0ffe83e4-4b3f-419b-9d8e-5ef87ab7f5fe" />
<img width="218" height="792" alt="image" src="https://github.com/user-attachments/assets/358c3058-1def-4ac3-bb7e-8c4a18f13752" />
<img width="401" height="784" alt="image" src="https://github.com/user-attachments/assets/70fc899c-29cc-4792-aa33-f4b8ada77dcd" />
<img width="246" height="787" alt="image" src="https://github.com/user-attachments/assets/1b33d3d3-cc1e-448d-9b76-be29113fe0c8" />
<img width="314" height="788" alt="image" src="https://github.com/user-attachments/assets/c3d1d2c4-ee68-4367-843d-5c56c8f27347" />
<img width="280" height="766" alt="image" src="https://github.com/user-attachments/assets/13ad4128-d56a-4c34-a0fa-2c6287cd984d" />


[Program 10: Write a Java program to create three threads using the Thread class. Each thread should print a sequence of characters (x, y, z) from 1 to 100 with a delay. Start all threads simultaneously and stop one thread after some time.](#Program10)
## Program 10
```package com.mycompany.sangini;

/**
 *
 * @author IBM26
 */
class X extends Thread {
    public void run() {
        for(int i = 1; i <= 100; i++) {
            System.out.println("x" + i);
            try {
                sleep(100);
            } catch(Exception e) {}
        }
    }
}

class Y extends Thread {
    public void run() {
        for(int i = 1; i <= 100; i++) {
            System.out.println("y" + i);
            try {
                sleep(100);
            } catch(Exception e) {}
        }
    }
}

class Z extends Thread {
    public void run() {
        for(int i = 1; i <= 100; i++) {
            System.out.println("z" + i);
            try {
                sleep(100);
            } catch(Exception e) {}
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
<img width="219" height="772" alt="image" src="https://github.com/user-attachments/assets/94ef0364-76dc-4515-a66a-dded1b1c3954" />

[Program 11: Write a Java program to create three threads using the Runnable interface. Each thread should print a sequence of strings (alpha, beta, gamma) from 1 to 100 with a delay. Start all threads and stop one thread after some time.](#Program11)
## Program 11
```/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package com.mycompany.sangini;

/**
 *
 * @author IBM26
 */
class Alpha implements Runnable {
    public void run() {
        for(int i = 1; i <= 100; i++) {
            System.out.println("alpha" + i);
            try {
                Thread.sleep(50);
            } catch(Exception e) {}
        }
    }
}

class Beta implements Runnable {
    public void run() {
        for(int i = 1; i <= 100; i++) {
            System.out.println("beta" + i);
            try {
                Thread.sleep(50);
            } catch(Exception e) {}
        }
    }
}

class Gamma implements Runnable {
    public void run() {
        for(int i = 1; i <= 100; i++) {
            System.out.println("gamma" + i);
            try {
                Thread.sleep(50);
            } catch(Exception e) {}
        }
    }
}

public class RunnableProgram {
    public static void main(String[] args) {

        Alpha a = new Alpha();
        Beta b = new Beta();
        Gamma c = new Gamma();

        Thread t1 = new Thread(a);
        Thread t2 = new Thread(b);
        Thread t3 = new Thread(c);

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
<img width="318" height="788" alt="image" src="https://github.com/user-attachments/assets/40c5068f-b9ca-4077-b6cb-5e4269815231" />


[Program 11: Write a Java program to create three threads using the Runnable interface. Each thread should print a sequence of strings (alpha, beta, gamma) from 1 to 100 with a delay. Start all threads and stop one thread after some time.](#Program11)
## Program 11
```/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package com.mycompany.sangini;

/**
 *
 * @author IBM26
 */
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package com.mycompany.sangini;

/**
 *
 * @author IBM26
 */
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
<img width="307" height="401" alt="image" src="https://github.com/user-attachments/assets/8ba2d854-6663-4013-949f-8b5839fbd4e7" />

[Program 11: Write a Java program to create three threads using the Runnable interface. Each thread should print a sequence of strings (alpha, beta, gamma) from 1 to 100 with a delay. Start all threads and stop one thread after some time.](#Program11)
## Program 11
```/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package com.mycompany.sangini;

/**
 *
 * @author IBM26
 */
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package com.mycompany.sangini;

/**
 *
 * @author IBM26
 */
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
<img width="307" height="401" alt="image" src="https://github.com/user-attachments/assets/8ba2d854-6663-4013-949f-8b5839fbd4e7" />

[Program 11: Write a Java program to create three threads using the Runnable interface. Each thread should print a sequence of strings (alpha, beta, gamma) from 1 to 100 with a delay. Start all threads and stop one thread after some time.](#Program11)
## Program 11
```
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package com.mycompany.sangini;

/**
 *
 * @author IBM26
 */
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

<img width="752" height="243" alt="image" src="https://github.com/user-attachments/assets/b050aff2-d8be-48a7-bece-bf1b4817de53" />

[Program 11: Write a Java program to create three threads using the Runnable interface. Each thread should print a sequence of strings (alpha, beta, gamma) from 1 to 100 with a delay. Start all threads and stop one thread after some time.](#Program11)
## Program 11
```
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package com.mycompany.sangini;

/**
 *
 * @author IBM26
 */
import java.io.*;

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

<img width="897" height="381" alt="image" src="https://github.com/user-attachments/assets/5779fb2c-58bf-4fc7-a852-e5075d3b123d" />



[Program 11: Write a Java program to create three threads using the Runnable interface. Each thread should print a sequence of strings (alpha, beta, gamma) from 1 to 100 with a delay. Start all threads and stop one thread after some time.](#Program11)
## Program 11
```
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package com.mycompany.sangini;

/**
 *
 * @author IBM26
 */
import java.io.*;
public class CopyChar {
    public static void main(String[] args) throws Exception {

        // create file first
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
<img width="903" height="396" alt="image" src="https://github.com/user-attachments/assets/02c81706-db22-4fba-a30a-9a959fab84f8" />



[Program 11: Write a Java program to create three threads using the Runnable interface. Each thread should print a sequence of strings (alpha, beta, gamma) from 1 to 100 with a delay. Start all threads and stop one thread after some time.](#Program11)
## Program 11
```
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package com.mycompany.sangini;

/**
 *
 * @author IBM26
 */
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

<img width="889" height="407" alt="image" src="https://github.com/user-attachments/assets/2a271a7d-04a2-4822-b6df-d1d5ac87b9e1" />

[Program 11: Write a Java program to create three threads using the Runnable interface. Each thread should print a sequence of strings (alpha, beta, gamma) from 1 to 100 with a delay. Start all threads and stop one thread after some time.](#Program11)
## Program 11
```
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package com.mycompany.sangini;

/**
 *
 * @author IBM26
 */
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
<img width="979" height="392" alt="image" src="https://github.com/user-attachments/assets/21b9e653-09b3-4f62-814d-96fa0c370585" />


[Program 11: Write a Java program to create three threads using the Runnable interface. Each thread should print a sequence of strings (alpha, beta, gamma) from 1 to 100 with a delay. Start all threads and stop one thread after some time.](#Program11)
## Program 11
```
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package com.mycompany.sangini;

/**
 *
 * @author IBM26
 */
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
<img width="879" height="393" alt="image" src="https://github.com/user-attachments/assets/20c02b39-10e2-4cd4-b0cc-db4a6aba9134" />


[Program 11: Write a Java program to create three threads using the Runnable interface. Each thread should print a sequence of strings (alpha, beta, gamma) from 1 to 100 with a delay. Start all threads and stop one thread after some time.](#Program11)
## Program 11
```
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package com.mycompany.sangini;

/**
 *
 * @author IBM26
 */
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

<img width="880" height="398" alt="image" src="https://github.com/user-attachments/assets/c3cb78b7-970c-454c-abf4-79fbdc88535b" />
