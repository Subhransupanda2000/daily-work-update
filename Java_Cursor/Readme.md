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
# Iterator
```
2) Iterator: 
 
 We can Use Iterator to get Objects One by One from Collection. 
 We can Apply Iterator Concept for any Collection Object. Hence it is Universal Cursor. 
 By using Iterator we can Able to Perform Both Read and Remove Operations. 
 We can Create Iterator Object by using iterator() of Collection Interface. 
 public Iterator iterator(); 
 
Eg:Iterator itr = c.iterator(); //c Means any Collection Object. 
 
Methods: 
1) public booleanhasNext() 
2) public Object next() 
3) public void remove() 
importjava.util.*; 
classIteratorDemo { 
 public static void main(String[] args) { 
  ArrayList l = new ArrayList(); 
  for (int i=0; i<=10; i++) { 
   l.add(i); 
  } 
  System.out.println(l); 
  Iterator itr = l.iterator(); 
  while(itr.hasNext()) { 
   Integer I = (Integer)itr.next(); 
   if(I%2 == 0) 
    System.out.println(I); 
   else 
    itr.remove(); 
  } 
  System.out.println(l); 
 } 
}
```
# Limitation 
* By using Enumeration and Iterator we can Move Only towards Forward Direction and we 
can’t Move Backward Direction. That is these are Single Direction Cursors but NotBi
Direction. 
* By using Iterator we can Perform Only Read and Remove Operations and we can't Perform 
Addition of New Objects and Replacing Existing Objects. 
* To Overcome these Limitations we should go for ListIterator.
# ListIterator
```
3) ListIterator:
 ListIterator is the Child Interface of Iterator. 
 By using ListIterator we can Move Either to the Forward Direction OR to the 
Backward Direction. That is it is a Bi-Directional Cursor. 
 By using ListIterator we can Able to Perform Addition of New Objects andReplacing 
existing Objects. In Addition to Read and Remove Operations. 
 We can Create ListIterator Object by using listIterator(). 
publicListIteratorlistIterator(); 
Eg:
ListIteratorltr = l.listIterator(); //l is Any List Object 
Methods:
 ListIteratoris the Child Interface of Iterator and Hence All Iterator Methods by Default 
It is applicable only for list.
Available to the ListIterator. 
publicbooleanhasNext() 
public Object next() 
publicintnextIndex() 
publicbooleanhasPrevious() 
public Object previous() 
publicintpreviousIndex() 
Forward Direction 
public void remove() 
public void set(Object new) 
public void add(Object new) 
```
```
importjava.util.*; 
classListIteratorDemo { 
 public static void main(String[] args) { 
  LinkedList l = new LinkedList(); 
  l.add("Baala"); 
  l.add("Venki"); 
  l.add("Chiru"); 
  l.add("Naag"); 
  System.out.println(l); 
  ListIteratorltr = l.listIterator(); 
  while(ltr.hasNext()) { 
   String s = (String)ltr.next(); 
   if(s.equals("Venki")) 
    ltr.remove(); 
   if(s.equals("Naag")) 
    ltr.add("Chaitu"); 
   if(s.equals("Chiru")) 
    ltr.add("Charan"); 
  } 
  System.out.println(l); 
 } 
} 
```
