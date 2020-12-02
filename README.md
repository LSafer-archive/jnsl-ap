# JNSL-AP
Java New Standard Library | Annotation Processor


# **NOTE!!!**
This project is still under development and It will not work.
Please do not depend on it until it gets a release tag! 

Imagine it!
If you want a function that accepts any thing as a parameter (primitives included).
You will not have to overload it many times with the same logic if there is an
annotation processor that does the work for you!


```java
//Standard
public static void doSomething(Object value) {
}
public static void doSomething(boolean value) {
}
public static void doSomething(byte value) {
}
public static void doSomething(char value) {
}
public static void doSomething(double value) {
}
public static void doSomething(float value) {
}
public static void doSomething(int value) {
}
public static void doSomething(long value) {
}
public static void doSomething(short value) {
}
```

```java
//With this annotation processor
public static void doSomething(@Overload(boolean.class, byte.class, char.class, double.class, float.class, int.class, long.class, short.class) Object value) {
}
//Or
public static void doSomething(@Overload Object value) {
}
```

```java
//The annotation definition
public @interface Overload {
  Class[] value() default {boolean.class, byte.class, char.class, double.class, float.class, int.class, long.class, short.class};
}
```
