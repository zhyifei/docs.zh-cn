---
title: 对象初始值设定项：命名类型和匿名类型 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ObjectInitializer
helpviewer_keywords:
- object initializers [Visual Basic]
- anonymous types [Visual Basic], object initializers
- initializing properties [Visual Basic]
- initializers [Visual Basic]
- named types [Visual Basic]
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
ms.openlocfilehash: 612b1dcea0f776dfd4580803e76f2785e7d28da6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655631"
---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a>对象初始值设定项：命名类型和匿名类型 (Visual Basic)
对象初始值设定项，可以通过使用单个表达式指定一个复杂对象的属性。 它们可以用于创建实例的命名类型和匿名类型。  
  
## <a name="declarations"></a>声明  
 声明命名类型和匿名类型的实例可以看起来几乎完全相同，但其效果并不相同。 每个类别都有其自己的功能和限制。 下面的示例演示一种简便方式声明和初始化命名类的实例`Customer`，通过使用对象初始值设定项列表。 请注意，在关键字后指定的类名称是`New`。  
  
 [!code-vb[VbVbalrObjectInit#1](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_1.vb)]  
  
 一个匿名类型有没有可用的名称。 因此实例化的匿名类型不能包含的类名称。  
  
 [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
 要求和的两个声明的结果并不相同。 有关`namedCust`、`Customer`具有类`Name`属性必须已经存在，并且声明会创建此类的实例。 有关`anonymousCust`，编译器定义了一个新的类具有一个属性，一个字符串称为`Name`，并创建此类的新实例。  
  
## <a name="named-types"></a>命名的类型  
 对象初始值设定项提供一种简单的方法来调用一种类型的构造函数，然后在单个语句中设置某些或所有属性的值。 编译器将调用该语句的适当构造函数： 如果未不提供任何参数，默认构造函数或参数化构造函数，如果发送一个或多个自变量。 之后，以在初始值设定项列表中出现的顺序进行初始化的指定的属性。  
  
 初始值设定项列表中的每个初始化包含的类的成员的初始值分配。 定义类时确定的名称和数据类型的成员。 在以下示例中，`Customer`类必须存在，并且必须具有成员命名`Name`和`City`，可以接受字符串值。  
  
 [!code-vb[VbVbalrObjectInit#3](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_3.vb)]  
  
 或者，你可以通过使用下面的代码来获取相同的结果：  
  
 [!code-vb[VbVbalrObjectInit#4](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_4.vb)]  
  
 每个这些声明是等效于以下示例中，这将创建`Customer`通过使用默认构造函数中，对象，然后指定初始值`Name`和`City`属性使用`With`语句。  
  
 [!code-vb[VbVbalrObjectInit#5](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_5.vb)]  
  
 如果`Customer`类包含使你能够发送中的值的参数化构造函数`Name`，例如，你可以声明和初始化`Customer`对象通过以下方式：  
  
 [!code-vb[VbVbalrObjectInit#6](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_6.vb)]  
  
 无需初始化所有属性，如以下代码所示。  
  
 [!code-vb[VbVbalrObjectInit#7](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_7.vb)]  
  
 但是，初始化列表不能为空。 未初始化的属性保留其默认值。  
  
### <a name="type-inference-with-named-types"></a>命名类型的类型推理  
 你可以缩短的声明的代码`cust1`通过组合使用对象初始值设定项和局部类型推理。 这允许你忽略`As`在变量声明中的子句。 变量的数据类型是从创建的分配的对象的类型推断出。 在下面的示例中的一种`cust6`是`Customer`。  
  
 [!code-vb[VbVbalrObjectInit#8](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_8.vb)]  
  
### <a name="remarks-about-named-types"></a>有关命名类型的备注  
  
-   不止一次在对象初始值设定项列表中，不能初始化类成员。 声明`cust7`会导致错误。  
  
     [!code-vb[VbVbalrObjectInit#9](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_9.vb)]  
  
-   成员可以用来初始化自身或另一个字段。 如果在被初始化，如下所示的以下声明之前访问成员，则`cust8`，将使用默认值。 请记住，使用对象初始值设定项的声明，处理时，第一件事是，都会调用适当的构造函数。 之后，将初始化初始值设定项列表中的各个字段。 在以下示例中，默认值为`Name`分配为`cust8`，并且初始化的值分配中`cust9`。  
  
     [!code-vb[VbVbalrObjectInit#10](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_10.vb)]  
  
     下面的示例使用参数化构造函数从`cust3`和`cust4`声明和初始化`cust10`和`cust11`。  
  
     [!code-vb[VbVbalrObjectInit#11](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_11.vb)]  
  
-   可以嵌套对象初始值设定项。 在下面的示例中，`AddressClass`是具有两个属性的类`City`和`State`，和`Customer`类具有`Address`是的一个实例的属性`AddressClass`。  
  
     [!code-vb[VbVbalrObjectInit#12](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_12.vb)]  
  
-   初始化列表不能为空。  
  
-   正在初始化的实例不能是类型对象。  
  
-   正在初始化的类成员不能共享的成员、 只读成员、 常量或方法调用。  
  
-   正在初始化的类成员无法编制索引，或可以限定。 下面的示例将引发编译器错误：  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a>匿名类型  
 匿名类型使用对象初始值设定项来创建未显式定义的新类型和名称的实例。 此时，编译器将根据你指定的属性的类型生成在对象初始值设定项列表中。 由于未指定类型的名称，因此将它称为*匿名类型*。 例如，比较和更早版本的以下声明`cust6`。  
  
 [!code-vb[VbVbalrObjectInit#13](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_13.vb)]  
  
 唯一的区别语法是后未指定任何名称`New`数据类型。 但是，会发生什么情况是有很大差异。 编译器将定义新的匿名类型具有两个属性，`Name`和`City`，并使用指定的值创建它的实例。 类型推理确定类型的`Name`和`City`在示例中为字符串。  
  
> [!CAUTION]
>  匿名类型的名称由编译器，生成和编译的不同而有所不同。 你的代码不应使用或依赖于匿名类型的名称。  
  
 类型的名称不可用，因为不能使用`As`子句来声明`cust13`。 必须推断其类型。 如果不使用后期绑定，这将限制到本地变量的匿名类型的使用。  
  
 匿名类型提供对关键支持[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询。 有关使用查询中的匿名类型的详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)和[Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)。  
  
### <a name="remarks-about-anonymous-types"></a>有关匿名类型的备注  
  
-   通常情况下，所有或大多数匿名类型声明中的属性将键属性，通过键入关键字指示`Key`属性名称的前面。  
  
     [!code-vb[VbVbalrObjectInit#14](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_14.vb)]  
  
     有关密钥属性的详细信息，请参阅[密钥](../../../../visual-basic/language-reference/modifiers/key.md)。  
  
-   对于匿名类型定义必须声明至少一个属性，如命名类型，初始值设定项列表。  
  
     [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
-   当声明匿名类型的实例时，编译器将生成匹配的匿名类型定义。 名称和数据类型的属性，将实例声明中，从包括以及中定义的编译器。 属性不是名为，并且它们必须命名类型定义，请提前。 其类型会被推断。 不能通过使用指定的属性的数据类型`As`子句。  
  
-   匿名类型还可以建立的名称和值的属性在其他几种方式。 例如，名称和变量，或名称的值和其他对象的属性的值，可能需要一个匿名类型属性。  
  
     [!code-vb[VbVbalrObjectInit#15](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_15.vb)]  
  
     有关在匿名类型中定义属性的选项的详细信息，请参阅[如何： 推断属性名和匿名类型声明中的类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)。  
  
## <a name="see-also"></a>请参阅  
 [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [如何：推断匿名类型声明中的属性名和类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)  
 [如何：使用对象初始值设定项声明对象](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
