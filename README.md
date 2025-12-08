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

