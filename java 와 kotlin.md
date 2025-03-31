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

val data1: Any = 10
val data1: Any = "hello"
val data2: Nothing = null
```
- var: 변수 -> 값 변경 가능
- val: 상수 -> 값 변경 불가능
- Any: 모든 타입의 데이터 할당이 가능합니다.
- Unit: Java의 void와 같다고 보면 됩니다.
- Nothing: 오로지 null값만 대입할 수 있습니다.

#### lateinit과 lazy
```
private lateinit var tts: TextToSpeech
val lazyValue: String by lazy {
    "Hello"
}
```
- lateinit : kotlin에서는 변수 초기화를 나중에 한다고 선언이 가능합니다. 오로지 var만 가능합니다.
- lazy :-> 이 경우 val이 주로 사용됨. var도 사용 가능
    - 처음 사용될 때 자동으로 초기화
    - 한 번만 초기화되고 그 이후로는 캐시된 값 사용
    - 값 변경 불가

## 2. 함수 선언

### Java

```
public class Welcome {
    public static void main(String[] args) {
        System.out.println("Welcome to Java!");
    }
}
```

- java에서는 파일 이름과 public class 이름이 동일

### Kotlin

```
fun main() {
    println("Hello, World!")
}
```

- Kotlin에서는 **`fun` 키워드**를 사용

## 3. 조건문 & 반복문

### Java

```
if (a > 10) {
    System.out.println("큰 값입니다");
} else {
    System.out.println("작은 값입니다");
}
```

```
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```

### Kotlin

```
if (a > 10) {
    println("큰 값입니다")
} else {
    println("작은 값입니다")
}
```

```
for (i in 0 until 5) {
    println(i)
}
```

- Kotlin의 `until`은 **마지막 값을 포함하지 않음** -> 위의 거 출력하면, 01234만 출력됨.

## 4. 클래스 & 객체

### Java

```
class Person{
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

```
class Person(val name: String, val age: Int) {
    fun introduce() {
        println("My name is $name and I am $age years old.")
    }
}
```

- `class` 선언이 간결하며, `val` 또는 `var`를 사용하여 생성자에서 변수를 바로 선언 가능

### 클래스 활용

### Java

```
public class Main {
    public static void main(String[] args) {
        Person person = new Person("Alice", 25);
        person.introduce();
    }
}
```

### Kotlin

```
fun main() {
    val person = Person("Alice", 25)
    person.introduce()
}
```

- Kotlin에서는 `new` 키워드를 사용하지 않고 객체를 생성 가능
- `main` 함수에서 간결하게 활용 가능

## 5. Null 안전성

### Java

```
String name = null;
System.out.println(name.length()); // NullPointerException 발생 가능
```

### Kotlin

```
var name: String? = null
println(name?.length) // Null 안전 연산자 (?.) 사용 가능
```

- Kotlin은 `null` 값을 허용하려면 `?`을 명시해야 함
- `!!` 연산자를 사용하면 **NullPointerException이 발생할 수도 있음** (`name!!.length`)
- !!는 null이 확실히 아님을 알려주는 문법

## 6. 배열
### Java




### Kotlin

