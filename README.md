/*
 Upcasting :-
Converting child object to parent reference automatically.

Downcasting:-
Converting parent reference to child reference using explicit casting.

instanceof :-
Operator used to check object type before downcasting.
 */

package casting;

class Animal {
	void sound() {
		System.out.println("Animal makes sound");
	}
}
class Dog extends Animal {
	void bark() {
		System.out.println("Dog Barking");
	}
}

class Cat extends Animal {
	void meow () {
		System.out.println("Cat Meowing");
	}
}

public class main {
	
	// 3) instanceof - which checks object type before downcasting
	 
			 // 4) Method Accepting Parent Reference + Downcasting + instanceof
		       static void checkAnimal(Animal a) {
		    	  if (a instanceof Dog) {
		    		   Dog d = (Dog) a;       // downcasting
		    		   d.bark();
		      }
		    	  else if (a instanceof Cat) {
		    		  Cat c = (Cat) a;      //downcasting
		    		  c.meow();
		    	  }
		    	  else {
		    		  System.out.println("Unknown Animal");
		    	  }
		       }
			
	public static void main(final String[] args) {
		
		
		 Animal arr [] = new Animal [2];
		 arr[0] = new Dog();
		 arr[1] = new Cat ();
		 for(Animal a : arr) {
			  if (a instanceof Dog) {
	    		   Dog d = (Dog) a;     // downcasting
	    		   d.bark();
	      }
	    	  else if (a instanceof Cat) {
	    		  Cat c = (Cat) a;     //downcasting
	    		  c.meow();
	    	  }
			 
		 }
 
	/*
	   Dog d = new Dog();
	   Cat c = new Cat();
	   checkAnimal(d);
	   checkAnimal(c);
    */
	}
	}

/* Animal Demo */
 
	class Animal
{
	void makeSound()
	{
	}
}
class Tiger extends Animal
{
	void makeSound()
	{
		System.out.println("roar");
	}
	void hunting()
	{
		System.out.println("hunt");
	}
}
class Dog extends Animal
{
	void makeSound()
	{
		System.out.println("bark");
	}
}
class Cat extends Animal
{
	void makeSound()
	{
		System.out.println("meow");
	}
}
public class AnimalDemo2
{
	static void perform(Animal ref)  // upcasting
	{
		ref.makeSound();  // polymorphic invocation
		//ref.hunting();  // compile-time error
		
		/*   logically incorrect
		Tiger temp=new Tiger();
		temp.hunting();
		*/
		if(ref instanceof Tiger)
		{
			Tiger temp=(Tiger)ref;  // downcasting
			temp.hunting();
		}

	}
	public static void main(String args[])
	{
		perform(new Tiger());
		perform(new Dog());
		perform(new Cat());
	}
}


ElectronicsAppliance1.Demo
package casting;
class ElectronicsAppliance
{
	void on()
	{
		
	}
	void off()
	{
		
	}
}
class TV extends ElectronicsAppliance
{
	void on()
	{
		System.out.println("TV on");
	}
	void off()
	{
		System.out.println("TV off");
	}
}
class Refrigerator extends ElectronicsAppliance
{
	void on()
	{
		System.out.println("Refrigerator on");
	}
	void off()
	{
		System.out.println("Refrigerator off");
	}
}
class WashingMachine extends ElectronicsAppliance
{
	void on()
	{
		System.out.println("WashingMachine on");
	}
	void off()
	{
		System.out.println("WashingMachine off");
	}
	void fillwater()
	{
		System.out.println("filling water");
	}
}
public class ElectronicsDemo {
    public static void perform (ElectronicsAppliance EA)
    {
    	EA.on();
    	EA.off();
    	if(EA instanceof WashingMachine)
    	{
    		WashingMachine W = (WashingMachine)EA;
    		W.fillwater();
    	}
    }
	public static void main(String[] args) {
		perform (new TV());
	  //  perform(new Refrigerator());
		perform(new WashingMachine());

	}

}



ElectronicsAppliance2.Demo
package casting;
class ElectronicsAppliance_1
{
	void on()
	{
		
	}
	void off()
	{
		
	}
}
class TV_1 extends ElectronicsAppliance_1
{
	void on()
	{
		System.out.println("TV on");
	}
	void off()
	{
		System.out.println("TV off");
	}
}
class Refrigerator_1 extends ElectronicsAppliance_1
{
	void on()
	{
		System.out.println("Refrigerator on");
	}
	void off()
	{
		System.out.println("Refrigerator off");
	}
}
class WashingMachine_1 extends ElectronicsAppliance_1
{
	void on()
	{
		System.out.println("WashingMachine on");
	}
	void off()
	{
		System.out.println("WashingMachine off");
	}
	void fillwater()
	{
		System.out.println("filling water");
	}
}
public class ElectronicsDemo1 {
	public static void main(String[] args) {
	  ElectronicsAppliance_1 arr[]= new ElectronicsAppliance_1[3];
	  arr[0]=new TV_1();
	  arr[1]=new Refrigerator_1();
      arr[2]=new WashingMachine_1();
      for(int i=0;i<arr.length;i++)
      {
    	  if(arr[i] instanceof WashingMachine_1)
    	  {
    		  WashingMachine_1 w = (WashingMachine_1)arr[i];
    		  w.fillwater();
    	  }
    	  arr[i].on();
    	  arr[i].off();
      } 
	}
}


WeaponDemo
package casting;

class Weapon {
	void attack()
	{
		System.out.println("Attack With Weapon");
	}
}
class Gun extends Weapon{
	void attack()
	{
		System.out.println("Attack with Gun");
	}
	void fillBullets()
	{
		System.out.println("Filling the Bullets");
	}
}
class Sword extends Weapon{
	void attack()
	{
		System.out.println("Attack with Sword");
	}
}
class Bomb extends Weapon{
	void attack()
	{
		System.out.println("Attack with Bomb");
	}
}

public class WeaponDemo {
    public static void fight(Weapon W)
      {
    	  if(W instanceof Gun)
    	  {
    		  Gun g = (Gun)W;
    	      g.fillBullets();
    	  }
    	  W.attack();   
      }
     
	public static void main(String[] args) {
 	    fight(new Gun());
		fight(new Sword());
        fight(new Bomb());
	}
}


Weapon1Demo
package casting;

class Weapon_1{
	void attack()
	{
		System.out.println("Attack With Weapon");
	}
}
class Gun_1 extends Weapon_1{
	void attack()
	{
		System.out.println("Attack with Gun");
	}
	void fillBullets()
	{
		System.out.println("Filling the Bullets");
	}
}
class Sword_1 extends Weapon_1{
	void attack()
	{
		System.out.println("Attack with Sword");
	}
}
class Bomb_1 extends Weapon_1{
	void attack()
	{
		System.out.println("Attack with Bomb");
	}
}

public class WeaponDemo1 {
     public static void main(String[] args) {
		Weapon_1 arr[]=new Weapon_1[3];
		arr[0] = new Gun_1();
		arr[1] = new Sword_1();
		arr[2] = new Bomb_1();
		for(int i=0;i<arr.length;i++)
		{
			if(arr[i] instanceof Gun_1)
			{
				Gun_1 g =(Gun_1) arr[i];
				g.fillBullets();
			}
			arr[i].attack();
		}
	}
}

Person Demo
abstract class Person
{
	// concrete behaviour
	void walk()
	{
		System.out.println("walking");
	}
	void talk()
	{
		System.out.println("talking");
	}
	void eat()
	{
		System.out.println("eating");
	}
	void sleep()
	{
		System.out.println("sleeping");
	}
	abstract void performDuties();  // contract
}
class HouseWife extends Person
{
	void performDuties()
	{
		System.out.println("take care of family");
	}
}
class Soldier extends Person
{
	void performDuties()
	{
		System.out.println("take care of Border");
	}
	void sleep()
	{
		System.out.println("I hardly sleep");
	}
}
public class PersonDemo1
{
	static void perform(Person ref)
	{
		ref.walk();
		ref.talk();
		ref.eat();
		ref.sleep();
		ref.performDuties();
	}
	public static void main(String args[])
	{
		perform(new HouseWife());
		perform(new Soldier());
		// perform(new Person()); // abstract class cannot be instatiated
	}
}


		           GUI DEMO
interface MouseEvent
{
	void mouseClicked(); // public and abstract
	void mouseEntered();
	void mouseExited();
}

interface WindowEvent
{
	void windowClosing();
	void windowOpening();
}
abstract class WindowsApp implements MouseEvent,WindowEvent
{
	/*public void mouseClicked()
	{
		System.out.println("in WindowsApp mouse clicked");
	}*/
	public void mouseExited()
	{
		System.out.println("in WindowsApp mouse exited");
	}
	public void mouseEntered()
	{
		System.out.println("in WindowsApp mouse entered");
	}
	public void windowClosing()
	{
		System.out.println("in WindowsApp window closing");
	}
	public void windowOpening()
	{
		System.out.println("in WindowsApp window opening");
	}
}

class LinuxApp implements MouseEvent,WindowEvent
{
	public void mouseClicked()
	{
		System.out.println("in LinuxApp mouse clicked");
	}
	public void mouseExited()
	{
		System.out.println("in LinuxApp mouse exited");
	}
	public void mouseEntered()
	{
		System.out.println("in LinuxApp mouse entered");
	}
	public void windowClosing()
	{
		System.out.println("in LinuxApp window closing");
	}
	public void windowOpening()
	{
		System.out.println("in LinuxApp window opening");
	}
}

public class GUIDemo1
{
	public static void main(String args[])
	{
		//WindowsApp w=new WindowsApp();
		w.mouseClicked();
		w.mouseEntered();
		w.mouseExited();
		w.windowOpening();
		w.windowClosing();

		System.out.println("*********");
		LinuxApp l=new LinuxApp();
		l.mouseEntered();
		l.mouseExited();
		l.windowOpening();
		l.windowClosing();
	}
}



			        *******EXCEPTION HANDLING*********
1) define your exception class by name "MyArithException"
(MyArithException.java)
define class "Calculator"   (Calculator.java)
In this class define a function,which will accept an int and return double of it.
e.g int caldouble(int)
This function will check an int which is passed to it
It will raise the  exception if 0 is passed or negative passed
in case of 0 caller of this method should get error message
"Zero not allowed" 
in case of negative caller of this method should get error message
"negative not allowed"
In case of positive value it should simply return the double value.
	[ this method shouldn't handle the exception]

Now define class "MyCalcApp" (MyCalcApp.java)
In this class you accept a number from user and pass that no. to
caldouble() method which is mentioned above.

package pack1;

class MyArithException extends Exception {
	public MyArithException(String message) {
		super(message);
	}
}


package pack1;



class MyCalc {
	public double caldouble(int num) throws MyArithException {
		if (num==0) {
			throw new MyArithException("Zero not allowed");
		}
		if(num<0) {
			throw new MyArithException("Negative not allowed");
		}
		return num * 2.0;
	}
}


package pack1;
import java.util.Scanner;

public class Demo {

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
	    MyCalc c =new MyCalc();
	    System.out.println("Enter a number: ");
	    int num = sc.nextInt();
	    
	    try {
	    	double result= c.caldouble(num);
	    	System.out.println("Result: " + result);
	    }
	    catch(MyArithException e) {
	    	e.printStackTrace();
	    }
	    System.out.println("Program Continues...");

	}

}



2)3) define "MyException" as a checked exception.

define a class "Demo" with 
	public void show1(), public void show2() , public void show3() and main functions.

inside "show3()" accept a number and if it is greater than 10 raise "MyException" else display the number.
	[ this method shouldn't handle the exception]

main() function should call "show1()" , 
show1() function should call "show2()",
show2() function should call "show3()"

show2() should not handle the exception but show1() should handle.

package pack2;

class MyException extends Exception {
  public MyException(String message) {
	  super(message);
  }
}

package pack2;
import java.util.Scanner;
public class Demo {
    public void show3() throws MyException {
    	Scanner sc =  new Scanner (System.in);
    	System.out.println("Enter a Number");
    	int num = sc.nextInt();
    	if(num>10) {
    		throw new MyException("Number greater than 10 not allowed");
    	}
    	else {
    		System.out.println("Number is: " + num);
    	}
    }
    public void show2() throws MyException{
    	show3();
    }
    public void show1() {
    	try {
    		show2();
    	}
    	catch(MyException e) {
    		e.printStackTrace();
    	}
    }
	public static void main(String[] args) {
	Demo d = new Demo();
	d.show1();
	}
}



3)5)
Create a custom checked exception InsufficientFundsException, which extends Exception.

Create a class BankAccount with:

Fields: int accountNumber, String accountHolder, double balance.

Method withdraw(double amount), which:

	raises InsufficientFundsException if balance < amount.

Deducts the amount from balance if funds are sufficient.

Method deposit(double amount), which adds money to the balance.

Create a main() method to:
Create a BankAccount object with an initial balance.

Try withdrawing an amount greater than the balance (handle the exception using try-catch).
Deposit money and retry the withdrawal.

package pack3;

class InsufficientFundsException extends Exception {
	public InsufficientFundsException(String message) { 
		  super(message);
	} 
}



package pack3;

 class BankAccount {
     int accountNumber;
     String accountHolder;
     double balance;
     //constructor
	public BankAccount(int accountNumber, String accountHolder, double balance) {
		super();
		this.accountNumber = accountNumber;
		this.accountHolder = accountHolder;
		this.balance = balance;
	}

public void withdraw (double amount) throws InsufficientFundsException{
	if(balance<amount) {
		throw new InsufficientFundsException("Insufficient Balance");
	}
	balance=balance-amount;
	System.out.println("Withdraw Successful.Remaining Balance: " + balance);
  }
public void deposit (double amount) {
	balance=balance+amount;
	System.out.println("Deposit Successful.New Balance: " + balance);
}
}


package pack3;
public class main {
	public static void main(String[] args) {
		BankAccount acc = new BankAccount(101,"Sankalp",5000);
        try {
        	acc.withdraw(10000);
        }
        catch(InsufficientFundsException e) {
        	e.printStackTrace();; 	
        }
        
        acc.deposit(3000);
        try {
        	acc.withdraw(7000);
        }
        catch(InsufficientFundsException e) {
        	e.printStackTrace();
        }
	}

}


4)INVALID AGE EXCEPTION 

package pack4;

public class InvalidAgeException extends Exception {
	public InvalidAgeException(String Message) {
		super(Message);
	}

}


package pack4;

public class AgeValidator {
   public void check (int age) throws InvalidAgeException{
	   if(age<18) {
		   throw new InvalidAgeException("Age must be 18 or above");
	   }
	   else {
		   System.out.println("Eligible for voting");
	   }
	   
   }
}


package pack4;

public class AgeChecker {
	public void verifyAge(int age) {
		
    AgeValidator av = new AgeValidator();
    
    try {
    	av.check(age);
    }
    catch(InvalidAgeException e) {
    	e.printStackTrace();
    }
  }
}

package pack4;
import java.util.Scanner;
public class TestAgeApp {

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		System.out.println("Enter age: ");
		int age =sc.nextInt();
		AgeChecker ac = new AgeChecker();
		ac.verifyAge(age);
	
	}
}



5)INVALIDMARKSEXCEPTION

package pack5;

public class InvalidMarksException  extends Exception{
      public InvalidMarksException (String Message) {
    	  super(Message);
	}

}


package pack5;

public class Student {
   public void setMarks(int marks) throws InvalidMarksException {
	   if(marks<0 || marks>100) {
		   throw new InvalidMarksException ("Invalid Marks. must be between 0 and 100");
	   }
	   else {
		   System.out.println("Marks Accepted");
	   }
   }
}


package pack5;
import java.util.Scanner;

public class StudentApp {

	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		Student s = new Student();
		System.out.println("Enter Marks: ");
		int marks = sc.nextInt();
		
		try {
			s.setMarks(marks);
		}
		catch (InvalidMarksException e){
          e.printStackTrace();
	}
	}
}


6)INVALID STUDENT AGE EXCEPTION

package pack6;

public class InvalidStudentAgeException  extends Exception{
 public InvalidStudentAgeException(String Message) {
	 super(Message);
 }
}

package pack6;

public class Student {
String name;
int age;

public Student(String name, int age) throws InvalidStudentAgeException {
	super();
	this.name = name;
	this.age = age;
 
    if(age<18 || age>60) {
	  throw new InvalidStudentAgeException("Invalid Student age:");
}
    System.out.println("Student Created Successfully");
  }
}


package pack6;
import java.util.Scanner;
public class StudentApp {
     public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		System.out.println("Enter Student Name: ");
		String name = sc.nextLine();
		System.out.println("Enter age: ");
		int age = sc.nextInt();
		try {
			Student s = new Student(name,age);
		}
		catch(InvalidStudentAgeException e) {
			e.printStackTrace();
		}

	}

}


 **********************LOGIC**********************************************************************






				   



