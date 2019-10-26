---
title: "Multiple Inheritance in C++"
date: 2019-10-25T13:51:04+07:00
draft: false
categories: ["programming"]
description: "In this post, we'll discuss together what and how to implement multiple inheritance in C++."
displayInMenu: false
displayInList: true
resources:
- name: featuredImage
  src: "Multiple Inheritance in Cpp.png"
  params:
    description: "Multiple Inheritance in C++"
---

You may or never use multiple inheritance in your code design using your preferred programming language. If you use programming language like Java or C#, they do not provide it. However this is not the case in C++. C++ permits you to use multiple inheritance.

## So, what is multiple inheritance?

Multiple inheritance is one of the feature in object oriented programming language. It allows derived class to inherits members from more than one parent.

## Is there any use case of multiple inheritance?

Well, let's consider there are two parent classes and one child class, named Person, Employee, and Teacher respectively. Therefore, we can assume that Teacher is a Person and at the same time Teacher is also an Employee. To be clear, see the diagram and source code below.

{{<smallimg src="multiple-inheritance-diagram-example.png" alt="A big beautiful smile" width="250px">}}

```c++
#include <string>
using std::string;
using std::move;

class Person {
private:
    string name;
    int age;
public:
    Person(string name, int age)
            : name(move(name)), age(age) {
    }
    std::string getName() { return name; }
    int getAge() { return age; }
    string display_info() {
        return "an instance of Person Class";
    }
};

class Employee {
private:
    string employer;
    double salary;
public:
    Employee(string employer, double salary)
            : employer(move(employer)), salary(salary) {
    }
    string get_employer() { return employer; }
    double get_salary() { return salary; }
    string display_info() {
        return "an instance of Employee Class";
    }
};

// Teacher publicly inherits Person and Employee
class Teacher : public Person, public Employee {
private:
    int max_credits;
public:
    Teacher(string name, int age, string employer, double salary, int max_credits)
            : Person(move(name), age), Employee(move(employer), salary), max_credits(max_credits) {
    }
};
```

## Are there any issues with multiple inheritance feature?

If you look closely at the source code above, you'll see there's a problem called **diamond problem**. Diamond problem is an ambiguity which arises when multiple inheritance is implemented. This will make a diamond shape on your class diagram. Look here for more info: <https://en.wikipedia.org/wiki/Multiple_inheritance>.

Did you find it? If not, see both **display_info** method included in two parent classes of Teacher. display_info method will confuse the compiler and cause the compiler to produce an error. This is because compiler doesn't know which one to be used if you try to call them via instance of Teacher.

Okay there's one problem spotted now. Are there other issues regarding multiple inheritance? Well, usually when the program becomes bigger and much more complex, it'll be harder to mantain. Therefore you should avoid use multimple inheritance if possible - there are many other approaches (eg. composition).

Alright... I think this is enough for today's post. I'll see in the next post, so stay tuned.

**K.Kusumo**
