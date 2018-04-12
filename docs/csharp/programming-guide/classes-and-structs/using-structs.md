---
title: 使用结构（C# 编程指南）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- structs [C#], using
ms.assetid: cea4a459-9eb9-442b-8d08-490e0797ba38
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 94181c42ce913dc76c9a074e4bcbb8240764c896
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="using-structs-c-programming-guide"></a>使用结构（C# 编程指南）
`struct` 类型适用于表示轻量级对象，如 `Point`、 `Rectangle`和 `Color`。 尽管用它来表示一个点就如同具有 [Auto-Implemented Properties（自动实现的属性）](../../../csharp/language-reference/keywords/class.md) 的 [类](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)那样方便，但在某些情况下，使用 [结构](../../../csharp/language-reference/keywords/struct.md) 可能更高效。 例如，如果你声明具有 1000 个 `Point` 对象的数组，那么你将分配额外的内存用于引用每个对象；在这种情况下，使用结构将更为便宜。 因为 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 包含一个称为 <xref:System.Drawing.Point>的对象，因此在此示例中的结构改名为“CoOrds”。  
  
 [!code-csharp[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 定义结构的默认（无参数）构造函数是错误的。 在结构体中初始化实例字段也是错误的。 可以仅通过使用参数化构造函数，隐式的默认构造函数初始化从外部访问结构成员[对象初始值设定项](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)，或通过逐个访问成员之后在声明结构。 任何私有或其他不可访问的成员以独占方式需要构造函数的使用。
  
 当你创建结构对象使用[新](../../../csharp/language-reference/keywords/new.md)运算符，将会创建并适当的构造函数调用根据[构造函数的签名](../../../csharp/programming-guide/classes-and-structs/constructors.md#constructor-syntax)。 与类不同，可以对结构进行实例化，而无需使用 `new` 运算符。 在这种情况下，没有调用任何构造函数，从而提高了分配效率。 但是，字段将保持为未分配状态且必须在在初始化所有字段之后才可使用对象。 这包括无法获取或设置通过自动实现的属性的值。
 
 如果实例化使用的默认、 无参数构造函数的结构对象时，所有成员都分配根据其[默认值](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md)。
  
 当编写一个结构的参数的构造函数，你必须显式初始化所有成员;否则为保持未分配的一个或多个成员，并且不能使用结构，生成编译器错误 CS0171。  
  
 由于全都是用于类的继承，因此没有用于结构的继承。 一个结构无法继承自另一个结构或类，并且它不能为类的基类。 但是，它可以从基类 <xref:System.Object>继承。 结构也可以实现接口，且实现方法与类相同。  
  
 不能使用关键字 `struct`声明一个类。 在 C# 中，类和结构在语义上是不同的。 结构是值类型，而类是引用类型。 有关更多信息，请参阅 [值类型](../../../csharp/language-reference/keywords/value-types.md)。  
  
 除非需要引用类型语义，将较小的类声明为结构，可以提高系统的处理效率。  
  
## <a name="example-1"></a>示例 1  
  
### <a name="description"></a>描述  
 此示例同时使用了默认构造函数和参数化构造函数来演示 `struct` 初始化。  
  
### <a name="code"></a>代码  
 [!code-csharp[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 [!code-csharp[csProgGuideObjects#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_2.cs)]  
  
## <a name="example-2"></a>示例 2  
  
### <a name="description"></a>描述  
 此示例演示了一个特定于结构的功能。 此功能可以创建 CoOrds 对象，而无需使用 `new` 运算符。 如果将 `struct` 替换为 `class`，程序将不会进行编译。  
  
### <a name="code"></a>代码  
 [!code-csharp[csProgGuideObjects#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_1.cs)]  
  
 [!code-csharp[csProgGuideObjects#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-structs_3.cs)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [类和结构](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [结构](../../../csharp/programming-guide/classes-and-structs/structs.md)
