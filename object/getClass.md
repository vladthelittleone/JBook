# java.lang.Object#getClass

## Введение

Возвращает класс объекта, который содержит методы для определения свойств класса и получения информации о классе.
Например, мы можем получить имя класса, список объявленных методов и т.д

Сигнатура метода выглядит как:

```java
public final native Class<?> getClass();
```

> Ключевое слово `native` означает, что метод реализован в платформенно-зависимом коде, чаще всего на `C/C++`, и скомпонован в виде динамической библиотеки.
>
> Эта реализация зависит от `JVM`.

> Возможно, вас сейчас это напугало, но на самом деле достаточно просто понимать, что 
> `native` означает лишь то, что вызываемый код, реализован не на `Java`.

Данный метод является финальным и переопределить его нельзя.

В `Java`, в отличии от многих других языков программирования, очень мощный `runtime`. Во время выполнения кода возможно через специальный механизм, который называется `Reflection API` или **рефлексия**.

> Рефлексия - это механизм исследования данных о программе во время её выполнения. Рефлексия позволяет получить и провести какие-то манипуляции с полями, методами и конструкторами класса.

И рассматриваемый метод - `getClass` - важная часть работы с рефлексией.

Например, выведем имя класса:

```java
void printClassName(Object obj) {
    System.out.println("The object's" + " class is " +
        obj.getClass().getSimpleName());
}
```
