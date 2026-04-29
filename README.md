# ☕ CS-23.202 — Advanced Programming Laboratory
### B.Tech 2nd Year | Mody University of Science & Technology

![Java](https://img.shields.io/badge/Language-Java-orange?style=flat-square&logo=java)
![Status](https://img.shields.io/badge/Status-In%20Progress-yellow?style=flat-square)
![Course](https://img.shields.io/badge/Course-CS--23.202-blue?style=flat-square)

---

## 📋 About

This repository contains all lab assignments for the **Advanced Programming Laboratory (CS-23.202)** course, 2nd Year B.Tech, AI & DL — Mody University of Science & Technology. Each program demonstrates core Object-Oriented Programming concepts in Java.

---

## 📂 Assignment Index


| # | Topic | Jump To |
|---|-------|---------|
| 01 | Basic Arithmetic Operations Class | [Assignment 1](#assignment-1) |
| 02 | Addition of Two Distances (m, cm, mm) | [Assignment 2](#assignment-2) |
| 03 | Addition of Two Times (hr, min, sec) | [Assignment 3](#assignment-3) |
| 04 | Addition of Two Distances (m, cm) | [Assignment 4](#assignment-4) |
| 05 | Addition of Two Times (hr, min) | [Assignment 5](#assignment-5) |
| 06 | Reverse a 1D Array | [Assignment 6](#assignment-6) |
| 07 | Matrix Operations | [Assignment 7](#assignment-7) |
| 08 | Common C Programs Converted to Java OOP | [Assignment 8](#assignment-8) |
| 09 | Method Overriding with Parent Class Reference | [Assignment 9](#assignment-9) |
| 10 | Java Swing – Draw and Fill Shapes | [Assignment 10](#assignment-10) |
| 11 | Java Swing – Simple Calculator GUI | [Assignment 11](#assignment-11) |
| 12 | Program on Inheritance | [Assignment 12](#assignment-12) |
| 13 | Division Class with Exception Handling | [Assignment 13](#assignment-13) |
| 14 | Operations on 2D Array| [Assignment 14](#assignment-14) |
| 15 | JFrame with 10 Buttons | [Assignment 15](#assignment-15) |
| 16 | Three Classes Printing 1 to 100 with Class Name | [Assignment 16](#assignment-16) |
| 17 | Three Classes Printing 1 to 10 (Without Threads) | [Assignment 17](#assignment-17) |
| 18 | Three Classes Printing 1 to 10 (Using Runnable) | [Assignment 18](#assignment-18) |
| 19 | File Copy using Byte Stream and Character Stream | [Assignment 19](#assignment-19) |
| 20 | ArrayList Operations | [Assignment 20](#assignment-20) |
| 21 | LinkedList Operations | [Assignment 21](#assignment-21) |
| 22 | Stack Operations using Collections | [Assignment 22](#assignment-22) |
| 23 | HashMap Operations | [Assignment 23](#assignment-23) |
| 24 | TreeMap Operations | [Assignment 24](#assignment-24) |
| 25 | Stack Implementation using Arrays | [Assignment 25](#assignment-25) |

---

## 🧪 Assignments

---

### Assignment 1

**A class with `add`, `subtract`, `multiply`, `divide` methods tested in `main`.**

| Code | Output |
|------|--------|
| <pre>public class Arithmetic {<br><br>    public int add(int a, int b) {<br>        return a + b;<br>    }<br><br>    public int subtract(int a, int b) {<br>        return a - b;<br>    }<br><br>    public int multiply(int a, int b) {<br>        return a * b;<br>    }<br><br>    public double divide(int a, int b) {<br>        if (b == 0) {<br>            System.out.println("Division by zero not allowed!");<br>            return 0;<br>        }<br>        return (double) a / b;<br>    }<br><br>    public static void main(String[] args) {<br>        Arithmetic obj = new Arithmetic();<br>        int a = 20, b = 4;<br>        System.out.println("Add: " + obj.add(a, b));<br>        System.out.println("Subtract: " + obj.subtract(a, b));<br>        System.out.println("Multiply: " + obj.multiply(a, b));<br>        System.out.println("Divide: " + obj.divide(a, b));<br>    }<br>}</pre> | <img src="https://github.com/user-attachments/assets/bdc02208-4126-4028-afbf-e00ee8f8c381" alt="image" width="800" /> |

---

### Assignment 2

**A class for adding two distances given in meters, centimeters, and millimeters.**

| Code | Output |
|------|--------|
| <pre>public class Distance3 {<br>    int meters, centimeters, millimeters;<br><br>    Distance3(int m, int cm, int mm) {<br>        this.meters = m;<br>        this.centimeters = cm;<br>        this.millimeters = mm;<br>    }<br><br>    public static Distance3 add(Distance3 d1, Distance3 d2) {<br>        int totalMM = d1.millimeters + d2.millimeters;<br>        int totalCM = d1.centimeters + d2.centimeters + totalMM / 10;<br>        totalMM = totalMM % 10;<br>        int totalM = d1.meters + d2.meters + totalCM / 100;<br>        totalCM = totalCM % 100;<br>        return new Distance3(totalM, totalCM, totalMM);<br>    }<br><br>    public void display() {<br>        System.out.println(meters + " m, " + centimeters + " cm, " + millimeters + " mm");<br>    }<br><br>    public static void main(String[] args) {<br>        Distance3 d1 = new Distance3(3, 75, 8);<br>        Distance3 d2 = new Distance3(2, 45, 6);<br>        System.out.print("Distance 1: "); d1.display();<br>        System.out.print("Distance 2: "); d2.display();<br>        Distance3 result = Distance3.add(d1, d2);<br>        System.out.print("Sum: "); result.display();<br>    }<br>}</pre> | <img src="https://github.com/user-attachments/assets/e56ec927-a785-41ac-b394-eaddf6ac6edf" alt="image" width="800" /> |

---

### Assignment 3

**A class for adding two time values given in hours, minutes, and seconds.**

| Code | Output |
|------|--------|
| <pre>public class Time3 {<br>    int hours, minutes, seconds;<br><br>    Time3(int h, int m, int s) {<br>        this.hours = h;<br>        this.minutes = m;<br>        this.seconds = s;<br>    }<br><br>    public static Time3 add(Time3 t1, Time3 t2) {<br>        int totalSec = t1.seconds + t2.seconds;<br>        int totalMin = t1.minutes + t2.minutes + totalSec / 60;<br>        totalSec = totalSec % 60;<br>        int totalHr = t1.hours + t2.hours + totalMin / 60;<br>        totalMin = totalMin % 60;<br>        return new Time3(totalHr, totalMin, totalSec);<br>    }<br><br>    public void display() {<br>        System.out.println(hours + " hr, " + minutes + " min, " + seconds + " sec");<br>    }<br><br>    public static void main(String[] args) {<br>        Time3 t1 = new Time3(2, 45, 50);<br>        Time3 t2 = new Time3(1, 30, 25);<br>        System.out.print("Time 1: "); t1.display();<br>        System.out.print("Time 2: "); t2.display();<br>        Time3 result = Time3.add(t1, t2);<br>        System.out.print("Sum: "); result.display();<br>    }<br>}</pre> | <img src="https://github.com/user-attachments/assets/0555f53c-4b30-416b-b401-29b91fc38f08" alt="image" width="800" /> |

---

### Assignment 4

**A class for adding two distances given in meters and centimeters.**

| Code | Output |
|------|--------|
| <pre>public class Distance2 {<br>    int meters, centimeters;<br><br>    Distance2(int m, int cm) {<br>        this.meters = m;<br>        this.centimeters = cm;<br>    }<br><br>    public static Distance2 add(Distance2 d1, Distance2 d2) {<br>        int totalCM = d1.centimeters + d2.centimeters;<br>        int totalM = d1.meters + d2.meters + totalCM / 100;<br>        totalCM = totalCM % 100;<br>        return new Distance2(totalM, totalCM);<br>    }<br><br>    public void display() {<br>        System.out.println(meters + " m, " + centimeters + " cm");<br>    }<br><br>    public static void main(String[] args) {<br>        Distance2 d1 = new Distance2(5, 80);<br>        Distance2 d2 = new Distance2(3, 60);<br>        System.out.print("Distance 1: "); d1.display();<br>        System.out.print("Distance 2: "); d2.display();<br>        Distance2 result = Distance2.add(d1, d2);<br>        System.out.print("Sum: "); result.display();<br>    }<br>}</pre> | <img src="https://github.com/user-attachments/assets/c35e74b2-c8cd-4a44-bc57-bcb10c689cef" alt="image" width="800" /> |

---

### Assignment 5

**A class for adding two time values given in hours and minutes.**

| Code | Output |
|------|--------|
| <pre>public class Time2 {<br>    int hours, minutes;<br><br>    Time2(int h, int m) {<br>        this.hours = h;<br>        this.minutes = m;<br>    }<br><br>    public static Time2 add(Time2 t1, Time2 t2) {<br>        int totalMin = t1.minutes + t2.minutes;<br>        int totalHr = t1.hours + t2.hours + totalMin / 60;<br>        totalMin = totalMin % 60;<br>        return new Time2(totalHr, totalMin);<br>    }<br><br>    public void display() {<br>        System.out.println(hours + " hr, " + minutes + " min");<br>    }<br><br>    public static void main(String[] args) {<br>        Time2 t1 = new Time2(3, 50);<br>        Time2 t2 = new Time2(2, 40);<br>        System.out.print("Time 1: "); t1.display();<br>        System.out.print("Time 2: "); t2.display();<br>        Time2 result = Time2.add(t1, t2);<br>        System.out.print("Sum: "); result.display();<br>    }<br>}</pre> | <img src="https://github.com/user-attachments/assets/ab35b2d2-821a-4956-a5b3-4e3dfed898af" alt="image" width="800" /> |

---

### Assignment 6

**A class with necessary methods to reverse a 1D array.**

| Code | Output |
|------|--------|
| <pre>public class ReverseArray {<br><br>    public void inputArray(int[] arr) {<br>        System.out.print("Original Array: ");<br>        for (int val : arr) System.out.print(val + " ");<br>        System.out.println();<br>    }<br><br>    public void reverseArray(int[] arr) {<br>        int left = 0, right = arr.length - 1;<br>        while (left < right) {<br>            int temp = arr[left];<br>            arr[left] = arr[right];<br>            arr[right] = temp;<br>            left++;<br>            right--;<br>        }<br>    }<br><br>    public void displayArray(int[] arr) {<br>        System.out.print("Reversed Array: ");<br>        for (int val : arr) System.out.print(val + " ");<br>        System.out.println();<br>    }<br><br>    public static void main(String[] args) {<br>        ReverseArray ra = new ReverseArray();<br>        int[] arr = {10, 20, 30, 40, 50};<br>        ra.inputArray(arr);<br>        ra.reverseArray(arr);<br>        ra.displayArray(arr);<br>    }<br>}</pre> | <img src="https://github.com/user-attachments/assets/60b8ffcc-bcb4-4e0c-8342-2af4497130d1" alt="image" width="800" /> |

---

### Assignment 7

**A class with methods for Transpose, Addition, Multiplication, Sum of rows, columns, and diagonals.**

| Code | Output |
|------|--------|
| <pre>public class MatrixOps {<br>    int rows, cols;<br>    int[][] matrix;<br><br>    MatrixOps(int[][] mat) {<br>        this.matrix = mat;<br>        this.rows = mat.length;<br>        this.cols = mat[0].length;<br>    }<br><br>    public void display() {<br>        for (int[] row : matrix) {<br>            for (int val : row) System.out.printf("%5d", val);<br>            System.out.println();<br>        }<br>    }<br><br>    public int[][] transpose() {<br>        int[][] result = new int[cols][rows];<br>        for (int i = 0; i < rows; i++)<br>            for (int j = 0; j < cols; j++)<br>                result[j][i] = matrix[i][j];<br>        return result;<br>    }<br><br>    public int[][] add(MatrixOps other) {<br>        int[][] result = new int[rows][cols];<br>        for (int i = 0; i < rows; i++)<br>            for (int j = 0; j < cols; j++)<br>                result[i][j] = matrix[i][j] + other.matrix[i][j];<br>        return result;<br>    }<br><br>    public int[][] multiply(MatrixOps other) {<br>        int[][] result = new int[rows][other.cols];<br>        for (int i = 0; i < rows; i++)<br>            for (int j = 0; j < other.cols; j++)<br>                for (int k = 0; k < cols; k++)<br>                    result[i][j] += matrix[i][k] * other.matrix[k][j];<br>        return result;<br>    }<br><br>    public void sumOfRows() {<br>        System.out.println("Sum of each row:");<br>        for (int i = 0; i < rows; i++) {<br>            int sum = 0;<br>            for (int j = 0; j < cols; j++) sum += matrix[i][j];<br>            System.out.println("Row " + (i+1) + ": " + sum);<br>        }<br>    }<br><br>    public void sumOfCols() {<br>        System.out.println("Sum of each column:");<br>        for (int j = 0; j < cols; j++) {<br>            int sum = 0;<br>            for (int i = 0; i < rows; i++) sum += matrix[i][j];<br>            System.out.println("Col " + (j+1) + ": " + sum);<br>        }<br>    }<br><br>    public void sumOfDiagonals() {<br>        int mainDiag = 0, antiDiag = 0;<br>        for (int i = 0; i < rows; i++) {<br>            mainDiag += matrix[i][i];<br>            antiDiag += matrix[i][cols - 1 - i];<br>        }<br>        System.out.println("Main Diagonal Sum: " + mainDiag);<br>        System.out.println("Anti Diagonal Sum: " + antiDiag);<br>    }<br><br>    public static void main(String[] args) {<br>        int[][] m1 = {{1,2,3},{4,5,6},{7,8,9}};<br>        int[][] m2 = {{9,8,7},{6,5,4},{3,2,1}};<br>        MatrixOps mat1 = new MatrixOps(m1);<br>        MatrixOps mat2 = new MatrixOps(m2);<br><br>        System.out.println("Matrix 1:"); mat1.display();<br>        System.out.println("Transpose:"); new MatrixOps(mat1.transpose()).display();<br>        System.out.println("Addition:"); new MatrixOps(mat1.add(mat2)).display();<br>        System.out.println("Multiplication:"); new MatrixOps(mat1.multiply(mat2)).display();<br>        mat1.sumOfRows();<br>        mat1.sumOfCols();<br>        mat1.sumOfDiagonals();<br>    }<br>}</pre> | <img src="https://github.com/user-attachments/assets/18c5c6bb-8635-401d-b3cd-454b6bb1b2d0" alt="image" width="800" /> |

---

### Assignment 8

**Five common C programs (Factorial, Armstrong, Palindrome, Fibonacci, Prime) converted to Java OOP.**

| Code | Output |
|------|--------|
| <pre>public class CommonPrograms {<br><br>    // 1. Factorial<br>    public long factorial(int n) {<br>        if (n <= 1) return 1;<br>        return n * factorial(n - 1);<br>    }<br><br>    // 2. Armstrong Number<br>    public boolean isArmstrong(int num) {<br>        int temp = num, sum = 0, digits = String.valueOf(num).length();<br>        while (temp != 0) {<br>            int d = temp % 10;<br>            sum += Math.pow(d, digits);<br>            temp /= 10;<br>        }<br>        return sum == num;<br>    }<br><br>    // 3. Palindrome<br>    public boolean isPalindrome(int num) {<br>        int reversed = 0, temp = num;<br>        while (temp != 0) {<br>            reversed = reversed * 10 + temp % 10;<br>            temp /= 10;<br>        }<br>        return reversed == num;<br>    }<br><br>    // 4. Fibonacci Series<br>    public void fibonacci(int n) {<br>        int a = 0, b = 1;<br>        System.out.print("Fibonacci: ");<br>        for (int i = 0; i < n; i++) {<br>            System.out.print(a + " ");<br>            int c = a + b;<br>            a = b;<br>            b = c;<br>        }<br>        System.out.println();<br>    }<br><br>    // 5. Prime Number<br>    public boolean isPrime(int num) {<br>        if (num < 2) return false;<br>        for (int i = 2; i <= Math.sqrt(num); i++)<br>            if (num % i == 0) return false;<br>        return true;<br>    }<br><br>    public static void main(String[] args) {<br>        ClassicPrograms cp = new ClassicPrograms();<br><br>        System.out.println("Factorial of 6: " + cp.factorial(6));<br>        System.out.println("153 is Armstrong: " + cp.isArmstrong(153));<br>        System.out.println("121 is Palindrome: " + cp.isPalindrome(121));<br>        cp.fibonacci(10);<br>        System.out.println("17 is Prime: " + cp.isPrime(17));<br>    }<br>}</pre> | <img src="https://github.com/user-attachments/assets/43bc38c6-747a-4654-bbe8-c2f192c31597" alt="image" width="800" /> |

---

### Assignment 9

**A parent class and two child classes with the same overridden method called via parent reference.**

| Code | Output |
|------|--------|
| <pre>class Animal {<br>    public void sound() {<br>        System.out.println("Animal makes a sound");<br>    }<br>}<br><br>class Dog extends Animal {<br>    @Override<br>    public void sound() {<br>        System.out.println("Dog says: Woof!");<br>    }<br>}<br><br>class Cat extends Animal {<br>    @Override<br>    public void sound() {<br>        System.out.println("Cat says: Meow!");<br>    }<br>}<br><br>public class OverrideDemo {<br>    public static void main(String[] args) {<br>        Animal ref;<br><br>        ref = new Dog();<br>        ref.sound();   // Calls Dog's sound()<br><br>        ref = new Cat();<br>        ref.sound();   // Calls Cat's sound()<br><br>        ref = new Animal();<br>        ref.sound();   // Calls Animal's sound()<br>    }<br>}</pre> | <img src="https://github.com/user-attachments/assets/6b6c8868-a76a-4a68-afb6-e2cfa55e5794" alt="image" width="800" /> |

---

### Assignment 10

**A Swing GUI with buttons to draw/fill rectangle and oval, and change colors.**

| Code | Output |
|------|--------|
| <pre>import javax.swing.*;<br>import java.awt.*;<br>import java.awt.event.*;<br><br>public class ShapeDrawer extends JFrame {<br>    String shape = "Rectangle";<br>    Color color = Color.RED;<br>    boolean fill = false;<br><br>    DrawPanel panel = new DrawPanel();<br><br>    ShapeDrawer() {<br>        setTitle("Shape Drawer");<br>        setSize(600, 500);<br>        setDefaultCloseOperation(EXIT_ON_CLOSE);<br>        setLayout(new BorderLayout());<br><br>        JPanel controls = new JPanel();<br>        JButton drawRect = new JButton("Rectangle");<br>        JButton drawOval = new JButton("Oval");<br>        JButton fillBtn  = new JButton("Fill");<br>        JButton red      = new JButton("Red");<br>        JButton black    = new JButton("Black");<br><br>        drawRect.addActionListener(e -> { shape = "Rectangle"; fill = false; panel.repaint(); });<br>        drawOval.addActionListener(e -> { shape = "Oval";      fill = false; panel.repaint(); });<br>        fillBtn .addActionListener(e -> { fill = !fill;        panel.repaint(); });<br>        red     .addActionListener(e -> { color = Color.RED;   panel.repaint(); });<br>        black   .addActionListener(e -> { color = Color.BLACK; panel.repaint(); });<br><br>        controls.add(drawRect); controls.add(drawOval);<br>        controls.add(fillBtn);  controls.add(red); controls.add(black);<br><br>        add(controls, BorderLayout.NORTH);<br>        add(panel, BorderLayout.CENTER);<br>        setVisible(true);<br>    }<br><br>    class DrawPanel extends JPanel {<br>        protected void paintComponent(Graphics g) {<br>            super.paintComponent(g);<br>            g.setColor(color);<br>            if (shape.equals("Rectangle")) {<br>                if (fill) g.fillRect(150, 100, 250, 150);<br>                else      g.drawRect(150, 100, 250, 150);<br>            } else {<br>                if (fill) g.fillOval(150, 100, 250, 150);<br>                else      g.drawOval(150, 100, 250, 150);<br>            }<br>        }<br>    }<br><br>    public static void main(String[] args) {<br>        new ShapeDrawer();<br>    }<br>}</pre> | <img width="878" height="445" alt="image" src="https://github.com/user-attachments/assets/b087799f-9555-4a3a-a4f3-4a24c41947bb" /> <img width="873" height="442" alt="image" src="https://github.com/user-attachments/assets/8b3675f3-d04c-41df-aa22-ac10dbc43f53" /> <img width="871" height="448" alt="image" src="https://github.com/user-attachments/assets/03c78b20-d7e6-4a20-b354-2be20cb36fe6" /> <img width="857" height="443" alt="image" src="https://github.com/user-attachments/assets/a6a57eb6-102e-45d3-9b08-1e8a2ef820c9" /> |

---

### Assignment 11

**A Swing calculator that takes two inputs and performs +, -, *, /.**

| Code | Output |
|------|--------|
| <pre>import javax.swing.*;<br>import java.awt.*;<br>import java.awt.event.*;<br><br>public class Calculator extends JFrame {<br>    JTextField num1   = new JTextField(10);<br>    JTextField num2   = new JTextField(10);<br>    JTextField result = new JTextField(15);<br><br>    Calculator() {<br>        setTitle("Simple Calculator");<br>        setSize(400, 200);<br>        setDefaultCloseOperation(EXIT_ON_CLOSE);<br>        setLayout(new GridLayout(5, 2, 5, 5));<br><br>        result.setEditable(false);<br><br>        add(new JLabel("Number 1:")); add(num1);<br>        add(new JLabel("Number 2:")); add(num2);<br><br>        JButton add = new JButton("+");<br>        JButton sub = new JButton("-");<br>        JButton mul = new JButton("*");<br>        JButton div = new JButton("/");<br><br>        add.addActionListener(e -> compute('+'));<br>        sub.addActionListener(e -> compute('-'));<br>        mul.addActionListener(e -> compute('*'));<br>        div.addActionListener(e -> compute('/'));<br><br>        add(add); add(sub); add(mul); add(div);<br>        add(new JLabel("Result:")); add(result);<br>        setVisible(true);<br>    }<br><br>    void compute(char op) {<br>        try {<br>            double a = Double.parseDouble(num1.getText());<br>            double b = Double.parseDouble(num2.getText());<br>            double res = switch (op) {<br>                case '+' -> a + b;<br>                case '-' -> a - b;<br>                case '*' -> a * b;<br>                case '/' -> b != 0 ? a / b : Double.NaN;<br>                default  -> 0;<br>            };<br>            result.setText(b == 0 && op == '/' ? "Error: Div by 0" : String.valueOf(res));<br>        } catch (NumberFormatException ex) {<br>            result.setText("Invalid Input");<br>        }<br>    }<br><br>    public static void main(String[] args) {<br>        new Calculator();<br>    }<br>}</pre> | <img width="1061" height="463" alt="image" src="https://github.com/user-attachments/assets/948640da-48ce-4246-8214-d4cfdff3fe66" /> <img width="1023" height="476" alt="image" src="https://github.com/user-attachments/assets/1b466fee-c721-42dc-bc57-29a8203d3ca1" /> <img width="1052" height="460" alt="image" src="https://github.com/user-attachments/assets/d3dcebce-dd4c-4c88-aa0a-2b3c851244a0" /> <img width="1065" height="490" alt="image" src="https://github.com/user-attachments/assets/1b997426-3691-4048-939d-09d6b7f922b0" /> |

---

### Assignment 12

| Code | Output |
|------|--------|
| <pre>class Employee {<br>    String name;<br>    int id;<br>    void setData(String name, int id) {<br>        this.name = name;<br>        this.id = id;<br>    }<br>    void display() {<br>        System.out.println("Employee Name: " + name);<br>        System.out.println("Employee ID: " + id);<br>    }<br>    public static void main(String[] args) {<br>        Employee e = new Employee();<br>        e.setData("Test", 1);<br>        e.display();<br>    }<br>}</pre> | <img width="1158" height="627" alt="image" src="https://github.com/user-attachments/assets/868dbcf8-00ef-4223-bd23-6915b779a4fa" /> |

---

### Assignment 13

**A Division class with integer division, float division, remainder, and batch division — all with divide-by-zero handling.**

| Code | Output |
|------|--------|
| <pre>public class Division {<br><br>    public int intDivide(int a, int b) throws ArithmeticException {<br>        if (b == 0) throw new ArithmeticException("Integer division by zero!");<br>        return a / b;<br>    }<br><br>    public double floatDivide(double a, double b) throws ArithmeticException {<br>        if (b == 0) throw new ArithmeticException("Float division by zero!");<br>        return a / b;<br>    }<br><br>    public int remainder(int a, int b) throws ArithmeticException {<br>        if (b == 0) throw new ArithmeticException("Modulo by zero!");<br>        return a % b;<br>    }<br><br>    public void divideAll(int[] numbers, int divisor) {<br>        if (divisor == 0) {<br>            System.out.println("Cannot divide: divisor is zero.");<br>            return;<br>        }<br>        System.out.println("Dividing all by " + divisor + ":");<br>        for (int num : numbers)<br>            System.out.println(num + " / " + divisor + " = " + (double) num / divisor);<br>    }<br><br>    public static void main(String[] args) {<br>        Division d = new Division();<br>        try {<br>            System.out.println("Int Divide: " + d.intDivide(20, 4));<br>            System.out.println("Float Divide: " + d.floatDivide(22.5, 4.5));<br>            System.out.println("Remainder: " + d.remainder(17, 5));<br>            d.divideAll(new int[]{10, 20, 30}, 3);<br>            System.out.println(d.intDivide(10, 0)); // Test exception<br>        } catch (ArithmeticException e) {<br>            System.out.println("Exception caught: " + e.getMessage());<br>        }<br>    }<br>}</pre> | <img src="https://github.com/user-attachments/assets/95a0ec99-409e-4ac6-b8de-b168ed967d4c" alt="image" width="800" /> |

---

### Assignment 14

| Code | Output |
|------|--------|
| <pre>import java.util.Scanner;<br>public class MatrixOperations {<br>    public static void main(String[] args) {<br>        Scanner sc = new Scanner(System.in);<br>        int rows, cols;<br>        System.out.print("Enter number of rows: ");<br>        rows = sc.nextInt();<br>        System.out.print("Enter number of columns: ");<br>        cols = sc.nextInt();<br>        int[][] A = new int[rows][cols];<br>        int[][] B = new int[rows][cols];<br>        int[][] sum = new int[rows][cols];<br>        int[][] multiply = new int[rows][cols];<br>        System.out.println("\nEnter elements of First Matrix:");<br>        for (int i = 0; i < rows; i++) {<br>            for (int j = 0; j < cols; j++) {<br>                A[i][j] = sc.nextInt();<br>            }<br>        }<br>        System.out.println("\nEnter elements of Second Matrix:");<br>        for (int i = 0; i < rows; i++) {<br>            for (int j = 0; j < cols; j++) {<br>                B[i][j] = sc.nextInt();<br>            }<br>        }<br>        for (int i = 0; i < rows; i++) {<br>            for (int j = 0; j < cols; j++) {<br>                sum[i][j] = A[i][j] + B[i][j];<br>            }<br>        }<br>        for (int i = 0; i < rows; i++) {<br>            for (int j = 0; j < cols; j++) {<br>                multiply[i][j] = 0;<br>                for (int k = 0; k < cols; k++) {<br>                    multiply[i][j] += A[i][k] * B[k][j];<br>                }<br>            }<br>        }<br>        System.out.println("\nAddition of Matrices:");<br>        for (int i = 0; i < rows; i++) {<br>            for (int j = 0; j < cols; j++) {<br>                System.out.print(sum[i][j] + " ");<br>            }<br>            System.out.println();<br>        }<br>        System.out.println("\nMultiplication of Matrices:");<br>        for (int i = 0; i < rows; i++) {<br>            for (int j = 0; j < cols; j++) {<br>                System.out.print(multiply[i][j] + " ");<br>            }<br>            System.out.println();<br>        }<br>        sc.close();<br>    }<br>}</pre> | <img width="848" height="821" alt="image" src="https://github.com/user-attachments/assets/ce3121e8-9893-491c-911e-5de5983f0079" />
 |

---

### Assignment 15

**A GUI using JFrame with 10 buttons each performing a different functionality.**

| Code | Output |
|------|--------|
| <pre>import javax.swing.*;<br>import java.awt.*;<br><br>public class TenButtons extends JFrame {<br><br>    TenButtons() {<br>        setTitle("10 Buttons Demo");<br>        setSize(500, 400);<br>        setDefaultCloseOperation(EXIT_ON_CLOSE);<br>        setLayout(new GridLayout(5, 2, 10, 10));<br><br>        JButton b1 = new JButton("1. Show Message");<br>        b1.addActionListener(e -> JOptionPane.showMessageDialog(this, "Hello from Button 1!"));<br><br>        JButton b2 = new JButton("2. Date & Time");<br>        b2.addActionListener(e -> JOptionPane.showMessageDialog(this, new java.util.Date().toString()));<br><br>        JButton b3 = new JButton("3. Random Number");<br>        b3.addActionListener(e -> JOptionPane.showMessageDialog(this, "Random: " + (int)(Math.random()*100)));<br><br>        JButton b4 = new JButton("4. Change BG Color");<br>        b4.addActionListener(e -> getContentPane().setBackground(<br>            new Color((int)(Math.random()*255),(int)(Math.random()*255),(int)(Math.random()*255))));<br><br>        JButton b5 = new JButton("5. Count Characters");<br>        b5.addActionListener(e -> {<br>            String input = JOptionPane.showInputDialog("Enter a string:");<br>            if (input != null) JOptionPane.showMessageDialog(this, "Length: " + input.length());<br>        });<br><br>        JButton b6 = new JButton("6. Reverse String");<br>        b6.addActionListener(e -> {<br>            String input = JOptionPane.showInputDialog("Enter a string:");<br>            if (input != null)<br>                JOptionPane.showMessageDialog(this, new StringBuilder(input).reverse().toString());<br>        });<br><br>        JButton b7 = new JButton("7. Even / Odd");<br>        b7.addActionListener(e -> {<br>            String input = JOptionPane.showInputDialog("Enter a number:");<br>            if (input != null) {<br>                int n = Integer.parseInt(input);<br>                JOptionPane.showMessageDialog(this, n + " is " + (n%2==0 ? "Even" : "Odd"));<br>            }<br>        });<br><br>        JButton b8 = new JButton("8. Quick Calc");<br>        b8.addActionListener(e -> {<br>            double a = Double.parseDouble(JOptionPane.showInputDialog("Enter num 1:"));<br>            double b2 = Double.parseDouble(JOptionPane.showInputDialog("Enter num 2:"));<br>            JOptionPane.showMessageDialog(this, "Sum=" + (a+b2) + "  Product=" + (a*b2));<br>        });<br><br>        JButton b9 = new JButton("9. Exit");<br>        b9.addActionListener(e -> {<br>            int res = JOptionPane.showConfirmDialog(this, "Exit?");<br>            if (res == JOptionPane.YES_OPTION) System.exit(0);<br>        });<br><br>        JButton b10 = new JButton("10. About");<br>        b10.addActionListener(e -> JOptionPane.showMessageDialog(this,<br>            "Java Swing Demo\nProgram 15\nNetBeans"));<br><br>        add(b1); add(b2); add(b3); add(b4); add(b5);<br>        add(b6); add(b7); add(b8); add(b9); add(b10);<br>        setVisible(true);<br>    }<br><br>    public static void main(String[] args) {<br>        new TenButtons();<br>    }<br>}</pre> | <img width="703" height="500" alt="image" src="https://github.com/user-attachments/assets/27b3ccc2-d209-4673-8bfe-90fd066a99ba" /> <img width="646" height="472" alt="image" src="https://github.com/user-attachments/assets/2d3479c6-716d-4345-a6df-4db8cd692e55" /> <img width="545" height="466" alt="image" src="https://github.com/user-attachments/assets/bf5c9ac5-4b61-4d68-b456-f113896075b4"/> <img width="795" height="545" alt="image" src="https://github.com/user-attachments/assets/fea891b4-a3e2-4bd6-937c-34239cb3a4af" /> <img width="1087" height="497" alt="image" src="https://github.com/user-attachments/assets/ede03e2b-d8e3-414c-8c83-69562dcc4d97" /> <img width="747" height="523" alt="image" src="https://github.com/user-attachments/assets/9c6c8cbf-72d2-495f-98d1-ae226cca5722" /> |

---

### Assignment 16

**Three classes each with a method printing 1 to 100 along with the class name.**

| Code | Output |
|------|--------|
| <pre>class ClassA {<br>    public void printNumbers() {<br>        for (int i = 1; i <= 100; i++)<br>            System.out.println("ClassA: " + i);<br>    }<br>}<br><br>class ClassB {<br>    public void printNumbers() {<br>        for (int i = 1; i <= 100; i++)<br>            System.out.println("ClassB: " + i);<br>    }<br>}<br><br>class ClassC {<br>    public void printNumbers() {<br>        for (int i = 1; i <= 100; i++)<br>            System.out.println("ClassC: " + i);<br>    }<br>}<br><br>public class MultiClassPrint {<br>    public static void main(String[] args) {<br>        new ClassA().printNumbers();<br>        new ClassB().printNumbers();<br>        new ClassC().printNumbers();<br>    }<br>}</pre> | <img src="https://github.com/user-attachments/assets/06bdef87-d398-4e17-9cfa-006f831f9435" alt="image" width="200" /> <img src="https://github.com/user-attachments/assets/23f82a82-11b3-4759-ab35-759f532edd00" alt="image" width="200" /> <img src="https://github.com/user-attachments/assets/0f6a7992-1cfd-49c7-84e5-2fa0362dede7" alt="image" width="200" /> <img src="https://github.com/user-attachments/assets/bbe11a24-fc61-430b-8648-a80e9bf2aecc" alt="image" width="200" /> <img src="https://github.com/user-attachments/assets/ff9b2d26-bd03-461a-a076-aae43f3c7afe" alt="image" width="200" /> <img src="https://github.com/user-attachments/assets/edc6fd7b-bf8b-4156-bb80-07d9538962af" alt="image" width="200" /> <img src="https://github.com/user-attachments/assets/719eb63f-ec0a-4b5d-b065-237f0c0ad318" alt="image" width="200" /> <img src="https://github.com/user-attachments/assets/39420c1c-db6e-4689-9497-67a384b4366f" alt="image" width="200" /> <img src="https://github.com/user-attachments/assets/d20cf0ad-1238-45ff-a9f6-ccf1c03640cb" alt="image" width="200" /> <img src="https://github.com/user-attachments/assets/5ff39710-2fff-4537-bce4-59529e88a13f" alt="image" width="200" /> |

---

### Assignment 17

**Three classes with methods printing 1 to 10, run sequentially without threads.**

| Code | Output |
|------|--------|
| <pre>class PrinterX {<br>    public void print() {<br>        System.out.println("\n--- PrinterX ---");<br>        for (int i = 1; i <= 10; i++)<br>            System.out.println("PrinterX: " + i);<br>    }<br>}<br><br>class PrinterY {<br>    public void print() {<br>        System.out.println("\n--- PrinterY ---");<br>        for (int i = 1; i <= 10; i++)<br>            System.out.println("PrinterY: " + i);<br>    }<br>}<br><br>class PrinterZ {<br>    public void print() {<br>        System.out.println("\n--- PrinterZ ---");<br>        for (int i = 1; i <= 10; i++)<br>            System.out.println("PrinterZ: " + i);<br>    }<br>}<br><br>public class SequentialPrint {<br>    public static void main(String[] args) {<br>        System.out.println("Running without threads - strictly sequential:");<br>        new PrinterX().print();<br>        new PrinterY().print();<br>        new PrinterZ().print();<br>        System.out.println("\nAll done. Output is always in order (X -> Y -> Z).");<br>    }<br>}</pre> | <img src="https://github.com/user-attachments/assets/b651a7b1-f68c-4827-a113-04dd01052325" alt="image" width="500" /> <img src="https://github.com/user-attachments/assets/9778159d-8241-4aa6-9c4f-7d2649e04727" alt="image" width="500" /> |

---

### Assignment 18

**Same as Program-17 but implemented using the `Runnable` interface.**

| Code | Output |
|------|--------|
| <pre>class RunnableX implements Runnable {<br>    public void run() {<br>        for (int i = 1; i <= 10; i++) {<br>            System.out.println("RunnableX: " + i);<br>            try { Thread.sleep(10); } catch (InterruptedException e) {}<br>        }<br>    }<br>}<br><br>class RunnableY implements Runnable {<br>    public void run() {<br>        for (int i = 1; i <= 10; i++) {<br>            System.out.println("RunnableY: " + i);<br>            try { Thread.sleep(10); } catch (InterruptedException e) {}<br>        }<br>    }<br>}<br><br>class RunnableZ implements Runnable {<br>    public void run() {<br>        for (int i = 1; i <= 10; i++) {<br>            System.out.println("RunnableZ: " + i);<br>            try { Thread.sleep(10); } catch (InterruptedException e) {}<br>        }<br>    }<br>}<br><br>public class RunnableDemo {<br>    public static void main(String[] args) throws InterruptedException {<br>        Thread t1 = new Thread(new RunnableX());<br>        Thread t2 = new Thread(new RunnableY());<br>        Thread t3 = new Thread(new RunnableZ());<br><br>        t1.start(); t2.start(); t3.start();<br><br>        t1.join(); t2.join(); t3.join();<br>        System.out.println("All threads finished!");<br>    }<br>}</pre> | <img src="https://github.com/user-attachments/assets/8801f754-938c-404a-aa99-df1fea65881d" alt="image" width="500" /> |

---

### Assignment 19

**Java program demonstrating file copy using both Byte Stream and Character Stream.**

| Code | Output |
|------|--------|
| <pre>import java.io.*;<br><br>public class FileCopy {<br><br>    // Method 1: Copy using Byte Stream<br>    public static void copyByteStream(String src, String dest) {<br>        try (FileInputStream fis = new FileInputStream(src);<br>             FileOutputStream fos = new FileOutputStream(dest)) {<br>            byte[] buffer = new byte[1024];<br>            int bytesRead;<br>            while ((bytesRead = fis.read(buffer)) != -1)<br>                fos.write(buffer, 0, bytesRead);<br>            System.out.println("Byte Stream copy done: " + dest);<br>        } catch (IOException e) {<br>            System.out.println("Error (Byte Stream): " + e.getMessage());<br>        }<br>    }<br><br>    // Method 2: Copy using Character Stream<br>    public static void copyCharStream(String src, String dest) {<br>        try (FileReader fr = new FileReader(src);<br>             FileWriter fw = new FileWriter(dest)) {<br>            char[] buffer = new char[1024];<br>            int charsRead;<br>            while ((charsRead = fr.read(buffer)) != -1)<br>                fw.write(buffer, 0, charsRead);<br>            System.out.println("Character Stream copy done: " + dest);<br>        } catch (IOException e) {<br>            System.out.println("Error (Char Stream): " + e.getMessage());<br>        }<br>    }<br><br>    public static void main(String[] args) throws IOException {<br>        // Create a test file<br>        try (FileWriter fw = new FileWriter("source.txt")) {<br>            fw.write("Hello, this is test content for file copy demonstration!\n");<br>            fw.write("Java file I/O is simple and powerful.");<br>        }<br>        copyByteStream("source.txt", "copy_byte.txt");<br>        copyCharStream("source.txt", "copy_char.txt");<br>    }<br>}</pre> | <img src="https://github.com/user-attachments/assets/1b2a8a0b-b5e2-4e09-8c10-2bcb13d42392" alt="image" width="800" /> |

---

### Assignment 20

**Demonstrating add, remove, search, update, and iteration on `ArrayList`.**

| Code | Output |
|------|--------|
| <pre>import java.util.ArrayList;<br>import java.util.Iterator;<br><br>public class ArrayListDemo {<br>    public static void main(String[] args) {<br>        ArrayList&lt;String&gt; list = new ArrayList&lt;&gt;();<br><br>        // Adding elements<br>        list.add("Apple"); list.add("Banana"); list.add("Cherry");<br>        list.add("Date");  list.add("Elderberry");<br>        System.out.println("After adding: " + list);<br><br>        // Removing element<br>        list.remove("Date");<br>        System.out.println("After removing 'Date': " + list);<br><br>        // Searching<br>        System.out.println("Contains 'Cherry': " + list.contains("Cherry"));<br>        System.out.println("Index of 'Banana': " + list.indexOf("Banana"));<br><br>        // Updating<br>        list.set(1, "Blueberry");<br>        System.out.println("After updating index 1: " + list);<br><br>        // Iterating using Iterator<br>        System.out.print("Iterating: ");<br>        Iterator&lt;String&gt; it = list.iterator();<br>        while (it.hasNext()) System.out.print(it.next() + " ");<br>        System.out.println();<br><br>        // Size<br>        System.out.println("Size: " + list.size());<br>    }<br>}</pre> | <img src="https://github.com/user-attachments/assets/adac79d7-1b7d-4707-b1a6-f46a4498d233" alt="image" width="800" /> |

---

### Assignment 21

**Implementing `LinkedList` with insert at beginning, middle, end, delete, search, display.**

| Code | Output |
|------|--------|
| <pre>import java.util.LinkedList;<br>import java.util.ListIterator;<br><br>public class LinkedListDemo {<br>    public static void main(String[] args) {<br>        LinkedList&lt;Integer&gt; list = new LinkedList&lt;&gt;();<br><br>        // Insert at end<br>        list.add(10); list.add(20); list.add(40); list.add(50);<br>        System.out.println("Initial: " + list);<br><br>        // Insert at beginning<br>        list.addFirst(5);<br>        System.out.println("After addFirst(5): " + list);<br><br>        // Insert at middle (index 3)<br>        list.add(3, 30);<br>        System.out.println("After add(3, 30): " + list);<br><br>        // Insert at end<br>        list.addLast(60);<br>        System.out.println("After addLast(60): " + list);<br><br>        // Delete first and last<br>        list.removeFirst();<br>        list.removeLast();<br>        System.out.println("After removing first & last: " + list);<br><br>        // Search<br>        System.out.println("Contains 30: " + list.contains(30));<br>        System.out.println("Index of 30: " + list.indexOf(30));<br><br>        // Display using ListIterator<br>        System.out.print("Forward traversal: ");<br>        ListIterator&lt;Integer&gt; it = list.listIterator();<br>        while (it.hasNext()) System.out.print(it.next() + " ");<br>        System.out.println();<br>    }<br>}</pre> | <img src="https://github.com/user-attachments/assets/edda7a66-0ea8-40e0-8c54-729c63c216e0" alt="image" width="500" /> |

---

### Assignment 22

**Demonstrating `Stack` push, pop, peek, isEmpty using Java Collections Framework.**

| Code | Output |
|------|--------|
| <pre>import java.util.Stack;<br><br>public class StackDemo {<br>    public static void main(String[] args) {<br>        Stack&lt;Integer&gt; stack = new Stack&lt;&gt;();<br><br>        // Check if empty<br>        System.out.println("Is empty: " + stack.isEmpty());<br><br>        // Push elements<br>        stack.push(10); stack.push(20); stack.push(30);<br>        stack.push(40); stack.push(50);<br>        System.out.println("After push: " + stack);<br><br>        // Peek (top element)<br>        System.out.println("Peek (top): " + stack.peek());<br><br>        // Pop element<br>        System.out.println("Pop: " + stack.pop());<br>        System.out.println("After pop: " + stack);<br><br>        // Search (1 = top)<br>        System.out.println("Search 20 (position from top): " + stack.search(20));<br><br>        // Is empty?<br>        System.out.println("Is empty: " + stack.isEmpty());<br><br>        // Pop all<br>        while (!stack.isEmpty())<br>            System.out.print("Popped: " + stack.pop() + "  ");<br>        System.out.println("\nStack is now empty: " + stack.isEmpty());<br>    }<br>}</pre> | <img src="https://github.com/user-attachments/assets/422eb15b-3076-4826-a780-9097be2d8562" alt="image" width="800" /> |

---

### Assignment 23

**Insert, retrieve, remove, and iterate key-value pairs using `HashMap`.**

| Code | Output |
|------|--------|
| <pre>import java.util.HashMap;<br>import java.util.Map;<br><br>public class HashMapDemo {<br>    public static void main(String[] args) {<br>        HashMap&lt;Integer, String&gt; map = new HashMap&lt;&gt;();<br><br>        // Insert<br>        map.put(1, "Alice");<br>        map.put(2, "Bob");<br>        map.put(3, "Charlie");<br>        map.put(4, "Diana");<br>        System.out.println("HashMap: " + map);<br><br>        // Retrieve by key<br>        System.out.println("Key 2 -> " + map.get(2));<br><br>        // Check key/value existence<br>        System.out.println("Contains key 3: " + map.containsKey(3));<br>        System.out.println("Contains value 'Bob': " + map.containsValue("Bob"));<br><br>        // Remove<br>        map.remove(1);<br>        System.out.println("After removing key 1: " + map);<br><br>        // Iterate using entrySet<br>        System.out.println("Iterating:");<br>        for (Map.Entry&lt;Integer, String&gt; entry : map.entrySet())<br>            System.out.println("  " + entry.getKey() + " => " + entry.getValue());<br><br>        System.out.println("Size: " + map.size());<br>    }<br>}</pre> | <img src="https://github.com/user-attachments/assets/87752e54-c317-4b1e-95a0-8d0c926b66d5" alt="image" width="800" /> |

---

### Assignment 24

**Inserting, displaying in sorted order, searching, and removing from `TreeMap`.**

| Code | Output |
|------|--------|
| <pre>import java.util.TreeMap;<br>import java.util.Map;<br><br>public class TreeMapDemo {<br>    public static void main(String[] args) {<br>        TreeMap&lt;Integer, String&gt; tmap = new TreeMap&lt;&gt;();<br><br>        // Insert (unsorted order)<br>        tmap.put(5, "Eve");<br>        tmap.put(2, "Bob");<br>        tmap.put(8, "Henry");<br>        tmap.put(1, "Alice");<br>        tmap.put(4, "Diana");<br><br>        // Display in sorted order (TreeMap auto-sorts by key)<br>        System.out.println("TreeMap (sorted): " + tmap);<br><br>        // First and Last keys<br>        System.out.println("First key: " + tmap.firstKey());<br>        System.out.println("Last key:  " + tmap.lastKey());<br><br>        // Search<br>        System.out.println("Contains key 4: " + tmap.containsKey(4));<br>        System.out.println("Value at key 2: " + tmap.get(2));<br><br>        // Remove<br>        tmap.remove(5);<br>        System.out.println("After removing key 5: " + tmap);<br><br>        // Iterate<br>        System.out.println("Iterate:");<br>        for (Map.Entry&lt;Integer, String&gt; e : tmap.entrySet())<br>            System.out.println("  " + e.getKey() + " -> " + e.getValue());<br>    }<br>}</pre> | <img src="https://github.com/user-attachments/assets/42aab4fb-c2a8-4ca7-93b0-d03f402d3001" alt="image" width="500" /> |

---

### Assignment 25

**Stack using arrays with push, pop, display, overflow and underflow handling.**

| Code | Output |
|------|--------|
| <pre>public class ArrayStack {<br>    int[] stack;<br>    int top;<br>    int maxSize;<br><br>    ArrayStack(int size) {<br>        maxSize = size;<br>        stack = new int[maxSize];<br>        top = -1;<br>    }<br><br>    public void push(int val) {<br>        if (top == maxSize - 1) {<br>            System.out.println("Stack OVERFLOW! Cannot push " + val);<br>            return;<br>        }<br>        stack[++top] = val;<br>        System.out.println("Pushed: " + val);<br>    }<br><br>    public int pop() {<br>        if (top == -1) {<br>            System.out.println("Stack UNDERFLOW! Stack is empty.");<br>            return -1;<br>        }<br>        return stack[top--];<br>    }<br><br>    public int peek() {<br>        if (top == -1) { System.out.println("Stack is empty."); return -1; }<br>        return stack[top];<br>    }<br><br>    public boolean isEmpty() { return top == -1; }<br><br>    public void display() {<br>        if (top == -1) { System.out.println("Stack is empty."); return; }<br>        System.out.print("Stack (top to bottom): ");<br>        for (int i = top; i >= 0; i--) System.out.print(stack[i] + " ");<br>        System.out.println();<br>    }<br><br>    public static void main(String[] args) {<br>        ArrayStack s = new ArrayStack(5);<br><br>        s.push(10); s.push(20); s.push(30); s.push(40); s.push(50);<br>        s.push(60);   // Overflow test<br>        s.display();<br>        System.out.println("Peek: " + s.peek());<br>        System.out.println("Pop: " + s.pop());<br>        s.display();<br><br>        // Empty and underflow test<br>        s.pop(); s.pop(); s.pop(); s.pop();<br>        s.pop();  // Underflow test<br>        System.out.println("Is Empty: " + s.isEmpty());<br>    }<br>}</pre> | <img src="https://github.com/user-attachments/assets/0ea38d59-9be3-4fe8-8512-bb860aa2470b" alt="image" width="800" /> |



---

## 👩‍💻 Author

**Sangini Garg**  
B.Tech — AI & Data Science, Mody University of Science & Technology 

---

> *Repository maintained as part of academic coursework. New assignments added progressively.*
