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
