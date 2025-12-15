# Конспект: Типы данных в Java для начинающих

## 1. Что такое тип данных?
Тип данных определяет:
- Какие значения может хранить переменная
- Сколько памяти она занимает
- Какие операции можно с ней выполнять

## 2. Два основных вида типов данных

### 2.1 Примитивные (простые) типы (8 типов)

| Тип | Размер | Диапазон | Пример |
|-----|--------|----------|---------|
| `byte` | 1 байт | -128 до 127 | `byte b = 100;` |
| `short` | 2 байта | -32,768 до 32,767 | `short s = 1000;` |
| `int` | 4 байта | -2³¹ до 2³¹-1 | `int i = 100000;` |
| `long` | 8 байт | -2⁶³ до 2⁶³-1 | `long l = 100000L;` |
| `float` | 4 байта | ~6-7 знаков после запятой | `float f = 3.14f;` |
| `double` | 8 байт | ~15 знаков после запятой | `double d = 3.14159;` |
| `char` | 2 байта | символы Unicode | `char c = 'A';` |
| `boolean` | 1 бит | true/false | `boolean flag = true;` |

### 2.2 Ссылочные типы
- Хранят ссылку на объект в памяти
- Примеры: String, массивы, классы

## 3. Примеры кода с примитивными типами

```java
public class DataTypesExample {
    public static void main(String[] args) {
        // Целочисленные типы
        byte myByte = 127;
        short myShort = 32000;
        int myInt = 1000000;
        long myLong = 10000000000L; // L в конце для long
        
        // Вещественные (дробные) типы
        float myFloat = 3.14f; // f в конце для float
        double myDouble = 3.14159265359;
        
        // Символьный тип
        char myChar = 'J';
        char unicodeChar = '\u0041'; // Символ 'A' в Unicode
        
        // Логический тип
        boolean isJavaFun = true;
        boolean isFishBird = false;
        
        // Вывод значений
        System.out.println("byte: " + myByte);
        System.out.println("short: " + myShort);
        System.out.println("int: " + myInt);
        System.out.println("long: " + myLong);
        System.out.println("float: " + myFloat);
        System.out.println("double: " + myDouble);
        System.out.println("char: " + myChar);
        System.out.println("Unicode char: " + unicodeChar);
        System.out.println("isJavaFun: " + isJavaFun);
    }
}
```

## 4. Строки (String) - ссылочный тип

```java
public class StringExample {
    public static void main(String[] args) {
        String greeting = "Hello, Java!";
        String name = "Alex";
        
        System.out.println(greeting);
        System.out.println("My name is " + name);
        System.out.println("Length of greeting: " + greeting.length());
    }
}
```

## 5. Автоматическое преобразование типов (приведение)

```java
public class TypeConversion {
    public static void main(String[] args) {
        // Неявное приведение (автоматическое)
        int smallInt = 100;
        long bigLong = smallInt; // автоматически
        
        // Явное приведение (ручное, может потерять данные)
        double price = 19.99;
        int intPrice = (int) price; // будет 19
        
        System.out.println("smallInt: " + smallInt);
        System.out.println("bigLong: " + bigLong);
        System.out.println("price: " + price);
        System.out.println("intPrice: " + intPrice);
    }
}
```

## 6. Литералы - способы записи значений

```java
public class LiteralsExample {
    public static void main(String[] args) {
        // Разные форматы записи чисел
        int decimal = 100;        // десятичная
        int binary = 0b1100100;   // двоичная (0b в начале)
        int octal = 0144;         // восьмеричная (0 в начале)
        int hex = 0x64;           // шестнадцатеричная (0x в начале)
        
        // Числа с подчеркиваниями для читаемости
        int million = 1_000_000;
        long creditCard = 1234_5678_9012_3456L;
        
        System.out.println("Десятичное: " + decimal);
        System.out.println("Двоичное: " + binary);
        System.out.println("Шестнадцатеричное: " + hex);
        System.out.println("Миллион: " + million);
    }
}
```

## 7. Особенности и советы для начинающих

### 7.1 Частые ошибки
```java
public class CommonMistakes {
    public static void main(String[] args) {
        // Ошибка: забыли 'f' для float
        // float wrongFloat = 3.14; // ОШИБКА!
        float correctFloat = 3.14f; // Правильно
        
        // Ошибка: забыли 'L' для больших long
        // long wrongLong = 3000000000; // ОШИБКА!
        long correctLong = 3000000000L; // Правильно
        
        // Ошибка: переполнение типа
        byte overflow = (byte) 200; // Будет -56!
        System.out.println("Переполнение byte: " + overflow);
    }
}
```

### 7.2 Ключевое слово `var` (с Java 10)
```java
public class VarExample {
    public static void main(String[] args) {
        // Java сама определяет тип
        var number = 10;          // int
        var text = "Hello";       // String
        var price = 9.99;         // double
        
        System.out.println(number + " - " + text + " - " + price);
    }
}
```

## 8. Сравнение примитивных и ссылочных типов

| Примитивные | Ссылочные |
|-------------|-----------|
| Хранят значение | Хранят ссылку на объект |
| Всегда имеют значение | Могут быть `null` |
| Начинаются с маленькой буквы | Начинаются с большой буквы |
| `int`, `double`, `char` | `String`, `Integer`, `Array` |

## 9. Практические задания

1. Создайте программу, которая объявляет все примитивные типы
2. Попробуйте сложить разные типы чисел (int + double)
3. Создайте программу для конвертации температуры из Цельсия в Фаренгейт
4. Поэкспериментируйте с переполнением типов данных

## 10. Ключевые выводы

1. В Java есть 8 примитивных типов и бесконечное количество ссылочных
2. Примитивные типы хранят значения, ссылочные - адреса объектов
3. Для float и больших long нужно добавлять 'f' и 'L'
4. Автоматическое приведение работает от меньшего типа к большему
5. Всегда следите за переполнением типов!

---
*Для продолжения изучения: массивы, оберточные классы (Integer, Double), enum*
