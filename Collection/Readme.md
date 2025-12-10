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
```
Difference Between Collection (I) and Collections (C):
 Collection is an Interface which can be used to Represent a Group of Individual Objects as a
Single Entity.
 Whereas Collections is an Utility Class Present in java.util Package to Define Several Utility
Methods for Collection Objects.
Note: There is No Concrete Class which implements Collection Interface Directly.
```
