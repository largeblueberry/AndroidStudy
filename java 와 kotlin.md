## 1. 변수 선언

### Java

```
int num = 10;
double pi = 3.14;
String text = "Hello";
boolean isTrue = true;
```

### Kotlin

```
val num: Int = 10
val pi: Double = 3.14
val text: String = "Hello"
val isTrue: Boolean = true
private lateinit var tts: TextToSpeech
```

## 2. 함수 선언

### Java

```java
public class Welcome {
    public static void main(String[] args) {
        System.out.println("Welcome to Java!");
    }
}
```

- java에서는 파일 이름과 public class 이름이 동일

### Kotlin

```kotlin
fun main() {
    println("Hello, World!")
}
```

- Kotlin에서는 **`fun` 키워드**를 사용

## 3. 조건문 & 반복문

### Java

```java
if (a > 10) {
    System.out.println("큰 값입니다");
} else {
    System.out.println("작은 값입니다");
}
```

```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```

### Kotlin

```kotlin
if (a > 10) {
    println("큰 값입니다")
} else {
    println("작은 값입니다")
}
```

```kotlin
for (i in 0 until 5) {
    println(i)
}
```

- Kotlin의 `until`은 **마지막 값을 포함하지 않음**
- `downTo`, `step`을 활용할 수 있음 → `for (i in 10 downTo 1 step 2)`

## 4. 클래스 & 객체

### Java

```java
class Person {
    String name;
    int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void introduce() {
        System.out.println("My name is " + name + " and I am " + age + " years old.");
    }
}
```

### Kotlin

```kotlin
class Person(val name: String, val age: Int) {
    fun introduce() {
        println("My name is $name and I am $age years old.")
    }
}
```

- `class` 선언이 간결하며, `val` 또는 `var`를 사용하여 생성자에서 변수를 바로 선언 가능

### 클래스 활용

### Java

```java
public class Main {
    public static void main(String[] args) {
        Person person = new Person("Alice", 25);
        person.introduce();
    }
}
```

### Kotlin

```kotlin
fun main() {
    val person = Person("Alice", 25)
    person.introduce()
}
```

- Kotlin에서는 `new` 키워드를 사용하지 않고 객체를 생성 가능
- `main` 함수에서 간결하게 활용 가능

## 5. Null 안전성

### Java

```java
String name = null;
System.out.println(name.length()); // NullPointerException 발생 가능
```

### Kotlin

```kotlin
var name: String? = null
println(name?.length) // Null 안전 연산자 (?.) 사용 가능
```

- Kotlin은 `null` 값을 허용하려면 `?`을 명시해야 함
- `!!` 연산자를 사용하면 **NullPointerException이 발생할 수도 있음** (`name!!.length`)
- !!는 null이 확실히 아님을 알려주는 문법

## 6. 람다식

### Java (익명 클래스 사용)

```java
interface Greeting {
    void sayHello();
}

public class Main {
    public static void main(String[] args) {
        Greeting greeting = new Greeting() {
            @Override
            public void sayHello() {
                System.out.println("Hello!");
            }
        };
        greeting.sayHello();
    }
}
```

### Kotlin (람다 표현식)

```kotlin
val greeting: () -> Unit = { println("Hello!") }
greeting()
```

- Kotlin에서는 간단한 람다식으로 표현 가능

## Java와 Kotlin 비교 요약

| 비교 항목 | Java | Kotlin |
| --- | --- | --- |
| 변수 선언 | `int num = 10;` | `val num: Int = 10` |
| 함수 선언 | `public int add(int a, int b)` | `fun add(a: Int, b: Int): Int` |
| Null 안전성 | `null` 허용, NPE 가능 | `?` 타입 지정 (ex: `String?`) |
| 클래스 | `class Person {}` | `class Person(val name: String)` |
| 람다 표현식 | 익명 클래스 필요 | 간단한 `{}` 람다 표현식 사용 |
| 확장 함수 | 제공되지 않음 | `fun String.greet()` 활용 가능 |
