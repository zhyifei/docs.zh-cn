---
title: 类（C# 编程指南）
description: 了解类类型及其创建方式
ms.date: 04/05/2018
helpviewer_keywords:
- classes [C#]
- C# language, classes
ms.assetid: e8848524-7273-429f-8aba-c658d5eff5ad
ms.openlocfilehash: 688736aa8556719789b02d7db25858f442b4309e
ms.sourcegitcommit: 895c7602386a6dfe7ca4facce3d965b27e5c6e87
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2018
ms.locfileid: "34312087"
---
# <a name="classes-c-programming-guide"></a>类（C# 编程指南）
*类*属于构造，使用类，可以通过组合其他类型的变量、方法和事件创建自己的自定义类型。 类好比是蓝图。 它定义类型的数据和行为。 如果类未声明为静态，客户端代码可以创建它的实例。 这些实例是分配给变量的对象。 类实例会一直保留在内存中，直到对它的所有引用都不在作用域范围之内。 超出范围时，CLR 将对其进行标记，以便用于垃圾回收。 如果类声明为[静态](../../../csharp/language-reference/keywords/static.md)，便无法创建实例，并且客户端代码只能通过类本身来访问它。 有关详细信息，请参阅[静态类和静态类成员](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)。  

## <a name="reference-types"></a>引用类型  
定义为[类](../../../csharp/language-reference/keywords/class.md)的一个类型是*引用类型*。 在运行时，如果声明引用类型的变量，此变量就会一直包含值 [null](../../../csharp/language-reference/keywords/null.md)，直到使用 [new](../../../csharp/language-reference/keywords/new.md) 运算符显式创建类实例，或直到为此变量分配已在其他位置创建的对象，如下面的示例所示：

```csharp
MyClass mc = new MyClass();
MyClass mc2 = mc;
```

创建对象后，内存位于托管堆上，并且变量只保留对对象位置的引用。 当分配托管堆上的类型和由 CLR 的自动内存管理功能对其进行回收（称为*垃圾回收*）时，需要开销。 但是，垃圾回收已是高度优化，并且在大多数情况下，不会产生性能问题。 有关垃圾回收的详细信息，请参阅[自动内存管理和垃圾回收](../../../standard/garbage-collection/gc.md)。  
  
## <a name="declaring-classes"></a>声明类  
 使用 [class](../../../csharp/language-reference/keywords/class.md) 关键字可以声明类，如下例所示：

 ```csharp
 public class Customer
 {
    // Fields, properties, methods and events go here...
 }
```

 `class` 关键字前面是访问级别。 因为此例中使用的是 [public](../../../csharp/language-reference/keywords/public.md)，所以任何人都可以创建此类的实例。 类的名称遵循 `class` 关键字。 定义的其余部分是类的主体，其中定义了行为和数据。 类上的字段、属性、方法和事件统称为*类成员*。  
  
## <a name="creating-objects"></a>创建对象  
 虽然它们有时可以互换使用，但类和对象是不同的概念。 类定义对象类型，但不是对象本身。 对象是基于类的具体实体，有时称为类的实例。  
  
 可通过使用 [new](../../../csharp/language-reference/keywords/new.md) 关键字，后跟对象要基于的类的名称，来创建对象，如：  

 ```csharp
 Customer object1 = new Customer();
 ```
  
 创建类的实例后，会将一个该对象的引用传递回程序员。 在上一示例中，`object1` 是对基于 `Customer` 的对象的引用。 该引用指向新对象，但不包含对象数据本身。 事实上，可以创建对象引用，而完全无需创建对象本身：  
  
  ```csharp
  Customer object2;
  ```
  
 不建议创建这样一个不引用对象的对象引用，因为尝试通过这类引用访问对象会在运行时失败。 但实际上可以使用这类引用来引用某个对象，方法是创建新对象，或者将其分配给现有对象，例如：  

 ```csharp
 Customer object3 = new Customer();
 Customer object4 = object3;
 ```
  
 此代码创建指向同一对象的两个对象引用。 因此，通过 `object3` 对对象做出的任何更改都会在后续使用 `object4` 时反映出来。 由于基于类的对象是通过引用来实现其引用的，因此类被称为引用类型。  
  
## <a name="class-inheritance"></a>类继承  

 类完全支持继承，这是面向对象的编程的基本特点。 创建类时，可以继承自其他任何未定义为 [sealed](../../../csharp/language-reference/keywords/sealed.md) 的接口或类，而且其他类也可以继承自你的类并重写类虚方法。

 继承是通过使用*派生*来完成的，这意味着类是通过使用其数据和行为所派生自的*基类*来声明的。 基类通过在派生的类名称后面追加冒号和基类名称来指定，如：  

 ```csharp
 public class Manager : Employee
 {
     // Employee fields, properties, methods and events are inherited
     // New Manager fields, properties, methods and events go here...
 }
 ```
  
 类声明基类时，会继承基类除构造函数外的所有成员。 有关详细信息，请参阅[继承](../../../csharp/programming-guide/classes-and-structs/inheritance.md)。
  
 与 C++ 不同，C# 中的类只能直接从基类继承。 但是，因为基类本身可能继承自其他类，因此类可能间接继承多个基类。 此外，类还可以直接实现多个接口。 有关详细信息，请参阅[接口](../../../csharp/programming-guide/interfaces/index.md)。  
  
 类可以声明为 [abstract](../../../csharp/language-reference/keywords/abstract.md)（抽象）。 抽象类包含抽象方法，抽象方法包含签名定义但不包含实现。 抽象类不能实例化。 只能通过可实现抽象方法的派生类来使用该类。 与此相反，[sealed](../../../csharp/language-reference/keywords/sealed.md)（密封）类不允许其他类继承。 有关详细信息，请参阅[抽象类、密封类和类成员](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)。  
  
 类定义可以在不同的源文件之间分割。 有关详细信息，请参阅[分部类和方法](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md)。  
  
## <a name="example"></a>示例  
 以下示例定义了一个公共类，该类包含一个[自动实现的属性](auto-implemented-properties.md)、一个方法和一个名为构造函数的特殊方法。 有关详细信息，请参阅[属性](properties.md)、[方法](methods.md)和[构造函数](constructors.md)主题。 然后使用 `new` 关键字实例化类的实例。  
  
 [!code-csharp[Class Example](~/samples/snippets/csharp/programming-guide/classes-and-structs/class-example.cs)] 
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [面向对象的编程](../concepts/object-oriented-programming.md)  
 [多态性](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)  
 [成员](../../../csharp/programming-guide/classes-and-structs/members.md)  
 [方法](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [构造函数](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [终结器](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
 [对象](../../../csharp/programming-guide/classes-and-structs/objects.md)
