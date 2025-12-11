# Cursor
```
The 3 Cursors of Java: 
 If we want to get Objects One by One from the Collection then we should go for Cursors. 
 There are 3 Types of Cursors Available in Java. 
1) Enumeration 
2) Iterator 
3) ListIterator 
```
# 1) Enumeration: 
```
 We can Use Enumeration to get Objects One by One from the Collection. 
 We can Create Enumeration Object by using elements(). 
 public Enumeration elements(); 
Eg:Enumeration e = v.elements(); //v is Vector Object. 
Methods: 
1) public booleanhasMoreElements(); 
2) public Object nextElement(); 

importjava.util.*; 
classEnumerationDemo { 
 public static void main(String[] args) { 
  Vector v = new Vector(); 
  for(int i=0; i<=10; i++) { 
   v.addElement(i); 
  } 
  System.out.println(v); 
  Enumeration e = v.elements(); 
  while(e.hasMoreElements()) { 
   Integer I = (Integer)e.nextElement(); 
   if(I%2 == 0) 
    System.out.println(I); 
  } 
  System.out.println(v); 
 } 
}
```
# Limitation of enumaration
* Enumeration Concept is Applicable Only for Legacy Classes and it is Not a Universal 
Cursor. 
* By using Enumeration we can Perform Read Operation and we can't Perform Remove 
Operation. 
 
* To Overcome Above Limitations we should go for Iterator
