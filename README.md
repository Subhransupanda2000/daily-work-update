# Interview Questions:
* Java Reflection
```
package org.example.array;

import java.lang.reflect.Field;
import java.lang.reflect.InvocationTargetException;
import java.lang.reflect.Method;

public class Cat {
    private final String name;
    private final int age;

    public Cat(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
    public void meow(){
        System.out.println("meow");
    }
    public static void privatestatic(){
        System.out.println("meow private static");
    }
}
class myclass{
    public static void main(String[] args) throws IllegalAccessException, InvocationTargetException {
        Cat mycat=new Cat("jimmy",34);
        Field[]fields=mycat.getClass().getFields();
        for (Field field:fields){
            field.setAccessible(true);
            if(field.getName().equals("name")){
              field.set(mycat,"jiju");
            }
        }
        Method []methods=mycat.getClass().getDeclaredMethods();
        for (Method meth:methods){
            if (meth.getName().equals("privatestatic")){
                meth.setAccessible(true);
                meth.invoke(null);
            }
        }
    }
}

```
# Constructer rule
* Class name and constructer name must be same.
* If we will add return type in constructer then it will treat as method
* public default protected private these modifiers are allowed. or else we will get ce. like static sychronized final etc not allowed
# Default constructer
* This is always no arg constructer
* Modifie will be same as class modifier . Default constructer has only one line that is super . 
* If we are not writing any constructer then default constructer will take super method in firstline.
* First line must be super or this else constructer will take super
* We can not write super in second line.
* We can not use super and this simultanesly. [call to super must be first line]
* Super method and this method we can use only in constructer not in method  [call to super must be first line]
* We can call constructer from a constructer but not from a method
