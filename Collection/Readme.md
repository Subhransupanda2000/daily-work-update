# Collection framework practice Notes
```
Array has few issues thats why collection got introduced
1. Array is fixed in size
2. Array is Homogenous can store only same data types
3. There is no standard data structre.so that there is no redymed method available. We need to write explicitly
To overcome above problems we should go for collection concept
```
# Collection:(Interface)
```
If You want to represent group of individual object as single entity then we should go for collection.
1. Collection are growable in nature. There is no fixed size.
2.Collection is also Heterogenous different type of data we can store
3. Readymed method support is avaliable.
4.Collection Interface is considered as Root Interface of Collection Framework.
5 Collection Interface defines the Most Common Methodswhich are Applicable for any
Collection Object.
Methods :add(Object),addAll(Collection)
remove(Object)
removeAll(Colection c), clear(),retainAll(),contain(obj),containAll(obj),isEmplty(),size(),iterator(),toArray()
```
# Difference between Arrays and collections
```
Arrays:
1 .Fixed size
2. Meomory wise Arrays not recomended
3. Perfomance wise Arrays  recomended
4.Homogenous
5. Redymade methods are not there
6. Arrays can hold both primitime and object type data
Collections:
1.Growable
2.Memory wise collection not recomended 
3. Perfomance wise Collections not recomended
4. Heterogenous
5. Readymade method support is there
6. Collections can hold  only  object type data

```
# Difference Between Collection (I) and Collections (C):
```
 Collection is an Interface which can be used to Represent a Group of Individual Objects as a
Single Entity.
 Whereas Collections is an Utility Class Present in java.util Package to Define Several Utility
Methods for Collection Objects.
Note: There is No Concrete Class which implements Collection Interface Directly.
```
# List:
```
It is the Child Interface of Collection.
If we want to Represent a Group of Individual Objects where Duplicates are allowed
and Insertion Order Preserved. Then we should go for List.

We can Preserve Insertion Order and we can Differentiate Duplicate Object by using
Index. Hence Index will Play Very Important Role in List.
Methods:List Interface Defines the following Specific Methods.
1) void add(int index, Object o)
2) booleanaddAll(int index, Collection c)
3) Object get(int index)
4) Object remove(int index)
5) Object set(int index, Object new):To Replace the Element Present at specified Index
with provided Object and Returns Old Object.
6) intindexOf(Object o):Returns Index of 1
st Occurrence of 'o'
7) intlastIndexOf(Object o)
8) ListIteratorlistIterator();
```
# ArrayList
```
ArrayList: 
 
 The Underlying Data Structure for ArrayList is Resizable Array ORGrowable Array. 
 Duplicate Objects are allowed. 
 Insertion Order is Preserved. 
 Heterogeneous Objects are allowed (Except TreeSet and TreeMap Everywhere 
Heterogeneous Objects are allowed). 
 null Insertion is Possible. 
1) ArrayList l = new ArrayList();
 Creates an Empty ArrayList Object with Default Initial Capacity 10. 
 If ArrayList Reaches its Max Capacity then a New ArrayList Object will be Created 
with  
New Capacity = (Current Capacity * 3/2)+1 
2) ArrayList l = new ArrayList(intinitialCapacity);
Creates an Empty ArrayList Object with specified Initial Capacity. 
3) ArrayList l = new ArrayList(Collection c);
 Creates an EqualentArrayList Object for the given Collection Object.  
 This Constructor Meant for Inter Conversion between Collection Objects.
 Usually we can Use Collections to Hold and Transfer Data (Objects) form One Location to 
Another Location.  
 To Provide Support for this Requirement Every Collection Class Implements Serializable 
and Cloneable Interfaces. 
 ArrayList and Vector Classes Implements RandomAccess Interface. So that we can Access 
any Random Element with the Same Speed. 
 RandomAccess Interface Present in java.utilPackage and it doesn't contain any Methods. 
Hence it is a Marker Interface. 
 Hence ArrayList is Best Suitable if Our Frequent Operation is Retrieval Operation.
```
# Difference between Arraylist and vector
```
ArrayList 
Every Method Present Inside ArrayListis Non – Synchronized. 
At a Time Multiple Threads are allow to Operate on ArrayList Simultaneously 
and Hence ArrayList Object is Not Thread Safe. 
Relatively Performance is High because Threads are Not required to Wait. 
Introduced in 1.2 Version and it is   Non –Legacy.
Vector 
Every Method Present in Vector is Synchronized.  
At a Time Only One Thread is allow to Operate on Vector Object and Hence 
Vector Object is Always Thread Safe. 
Relatively Performance is Low because Threads are required to Wait. 
It is legcy class
```
