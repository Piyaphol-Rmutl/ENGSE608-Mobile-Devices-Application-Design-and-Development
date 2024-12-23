# ตัวอย่างการการใช้งานภาษา Dart

## หัวข้อ
1. การใช้งาน Functions
2. การใช้งาน Classes
3. การใช้งาน Libraries and Packages
4. การใช้งาน Typedefs

---

## 1. การใช้งาน Functions
### ทฤษฎี
- **Function** เป็นส่วนหนึ่งของโปรแกรมที่สามารถนำมาใช้งานซ้ำได้
- มีรูปแบบดังนี้:
  ```dart
  returnType functionName(parameterList) {
      // code block
  }
  ```

### ตัวอย่างการใช้งาน
#### ฟังก์ชันทั่วไป
```dart
void printMessage(String message) {
  print('Message: \$message');
}

void main() {
  printMessage('สวัสดี Dart!');
}
```

#### ฟังก์ชันที่มีค่า Return
```dart
int add(int a, int b) {
  return a + b;
}

void main() {
  int result = add(5, 3);
  print('ผลบวกคือ: \$result');
}
```

#### Anonymous Function (ฟังก์ชันไม่มีชื่อ)
```dart
void main() {
  var list = ['Dart', 'Flutter', 'Programming'];
  list.forEach((item) {
    print(item);
  });
}
```

---

## 2. การใช้งาน Classes
### ทฤษฎี
- **Class** เป็นแบบแผนของวัตถุ (Object) ที่มี **Properties** และ **Methods**
- ใช้คำสั่ง `class` ในการสร้าง

### ตัวอย่างการใช้งาน
#### การสร้างคลาสและการใช้งาน
```dart
class Person {
  String name;
  int age;

  Person(this.name, this.age);

  void introduce() {
    print('สวัสดี ฉันชื่อ \$name อายุ \$age ปี');
  }
}

void main() {
  var person = Person('อนันต์', 25);
  person.introduce();
}
```

#### Inheritance (การสืบทอดคลาส)
```dart
class Animal {
  void sound() {
    print('เสียงสัตว์ทั่วไป');
  }
}

class Dog extends Animal {
  @override
  void sound() {
    print('โฮ่ง โฮ่ง');
  }
}

void main() {
  var dog = Dog();
  dog.sound();
}
```

---

## 3. การใช้งาน Libraries and Packages
### ทฤษฎี
- **Library** คือชุดของโค้ดที่สามารถนำมาใช้ซ้ำได้
- **Package** คือการรวบรวมหลาย Library ไว้ด้วยกัน
- ใช้ `import` เพื่อนำ Library เข้ามาใช้งาน

### ตัวอย่างการใช้งาน
#### การนำเข้า Library
```dart
import 'dart:math';

void main() {
  var randomNum = Random().nextInt(100);
  print('เลขสุ่มคือ: \$randomNum');
}
```

#### การใช้งาน External Package
1. เพิ่มแพ็กเกจใน `pubspec.yaml`
   ```yaml
   dependencies:
     http: ^0.15.0
   ```

2. ใช้แพ็กเกจในโปรแกรม
   ```dart
   import 'package:http/http.dart' as http;

   void main() async {
     var url = Uri.parse('https://jsonplaceholder.typicode.com/posts/1');
     var response = await http.get(url);

     if (response.statusCode == 200) {
       print('Response Body: \n\${response.body}');
     } else {
       print('Request failed with status: \${response.statusCode}');
     }
   }
   ```

---

## 4. การใช้งาน Typedefs
### ทฤษฎี
- **Typedef** ใช้กำหนดชื่อใหม่ให้กับประเภทของฟังก์ชันหรือข้อมูล

### ตัวอย่างการใช้งาน
#### การกำหนดและใช้งาน Typedefs
```dart
typedef Calculator = int Function(int a, int b);

int add(int a, int b) => a + b;
int multiply(int a, int b) => a * b;

void main() {
  Calculator calc;

  calc = add;
  print('ผลบวก: \${calc(10, 20)}');

  calc = multiply;
  print('ผลคูณ: \${calc(10, 20)}');
}
```

---

## สรุป
ในบทเรียนนี้ เราได้เรียนรู้เกี่ยวกับ:
- การสร้างและเรียกใช้งานฟังก์ชันในรูปแบบต่าง ๆ
- การออกแบบคลาสและการสืบทอด
- การใช้ Libraries และ Packages ในโปรเจกต์
- การใช้ Typedefs เพื่อกำหนดรูปแบบของฟังก์ชัน

การฝึกปฏิบัติและทดลองใช้งานตัวอย่างจะช่วยเพิ่มความเข้าใจและทักษะในการเขียนโปรแกรมภาษา Dart ได้ดียิ่งขึ้น!

