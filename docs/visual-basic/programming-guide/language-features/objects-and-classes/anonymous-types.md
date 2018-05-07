---
title: 匿名类型 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousType
helpviewer_keywords:
- anonymous types [Visual Basic], about anonymous types
- anonymous types [Visual Basic]
- types [Visual Basic], anonymous
ms.assetid: 7b87532c-4b3e-4398-8503-6ea9d67574a4
ms.openlocfilehash: 451fe45c9b5efbeb64b1066d6ba8e5f9b27300c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="anonymous-types-visual-basic"></a>匿名类型 (Visual Basic)
Visual Basic 支持匿名类型，使你可以创建对象，而无需编写数据类型的类定义。 此时，编译器将为你生成类。 类具有没有可用的名称，直接继承自<xref:System.Object>，并包含在声明对象指定的属性。 由于未指定数据类型的名称，因此将它称为*匿名类型*。  
  
 下面的示例声明并创建变量`product`实例具有两个属性的匿名类型的形式`Name`和`Price`。  
  
 [!code-vb[VbVbalrAnonymousTypes#1](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_1.vb)]  
  
 A*查询表达式*使用匿名类型的查询所选择的数据的列组合在一起。 你不能请提前定义的结果的类型，因为你无法预测特定查询可能会选择的列。 匿名类型使你能够编写选择任意数量的列，按任何顺序的查询。 编译器创建与指定的属性和指定的顺序匹配的数据类型。  
  
 在以下示例中，`products`是 product 对象，其中每个具有许多属性的列表。 变量`namePriceQuery`包含的查询，它执行时，将返回具有两个属性的匿名类型的实例的集合定义`Name`和`Price`。  
  
 [!code-vb[VbVbalrAnonymousTypes#2](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_2.vb)]  
  
 变量`nameQuantityQuery`包含的查询，它执行时，将返回具有两个属性的匿名类型的实例的集合定义`Name`和`OnHand`。  
  
 [!code-vb[VbVbalrAnonymousTypes#3](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_3.vb)]  
  
 有关创建由编译器为匿名类型的代码的详细信息，请参阅[匿名类型定义](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)。  
  
> [!CAUTION]
>  匿名类型的名称是编译器生成和编译的不同而有所不同。 你的代码不应使用或依赖于匿名类型的名称，因为重新编译项目时，可能会更改的名称。  
  
## <a name="declaring-an-anonymous-type"></a>声明匿名类型  
 匿名类型的实例的声明使用初始值设定项列表来指定类型的属性。 当你声明匿名类型、 不如方法或事件的其他类元素时，你可以指定属性。 在下面的示例中，`product1`是具有两个属性的匿名类型的实例：`Name`和`Price`。  
  
 [!code-vb[VbVbalrAnonymousTypes#4](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_4.vb)]  
  
 如果将属性指定为键属性，你可以使用它们比较相等的两个匿名类型实例。 但是，不能更改的键属性的值。 请参阅有关详细信息的本主题后面的密钥属性一节。  
  
 请注意，声明匿名类型的实例是类似于使用对象初始值设定项声明命名类型的实例：  
  
 [!code-vb[VbVbalrAnonymousTypes#5](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_5.vb)]  
  
 指定匿名类型属性的其他方法有关的详细信息，请参阅[如何： 推断属性名和匿名类型声明中的类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)。  
  
## <a name="key-properties"></a>键属性  
 在多个重要方面情况下，键属性不同于非键属性状态：  
  
-   仅键属性的值进行比较以确定两个实例是否相等。  
  
-   键属性的值是只读的并且不能更改。  
  
-   仅在一个匿名类型的编译器生成的哈希代码算法包括键属性值。  
  
### <a name="equality"></a>相等  
 匿名类型的实例可以是相同的匿名类型的实例才相等。 编译器将两个实例视为相同类型的实例，如果只要满足以下条件：  
  
-   同一程序集声明它们。  
  
-   其属性具有相同的名称相同的推断类型和声明顺序相同。 名称比较不区分大小写。  
  
-   在每个相同的属性被标记为键属性。  
  
-   每个声明中的至少一个属性是键属性。  
  
 没有键属性的匿名类型实例是仅等于其自身。  
  
 [!code-vb[VbVbalrAnonymousTypes#6](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_6.vb)]  
  
 如果它们的键属性的值相等，则相同的匿名类型的两个实例相等。 以下示例说明如何测试相等。  
  
 [!code-vb[VbVbalrAnonymousTypes#7](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_7.vb)]  
  
### <a name="read-only-values"></a>只读的值  
 无法更改的键属性的值。 例如，在`prod8`在前面的示例中，`Name`和`Price`字段`read-only`，但`OnHand`可以更改。  
  
 [!code-vb[VbVbalrAnonymousTypes#8](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_8.vb)]  
  
## <a name="anonymous-types-from-query-expressions"></a>从查询表达式的匿名类型  
 查询表达式并不总是要求创建匿名类型。 如果可能，它们将使用现有类型以保存列的数据。 查询从数据源或只有一个字段从每个记录返回任一整条记录时，将发生这种情况。 在下面的代码示例中，`customers`是对象的集合`Customer`类。 类具有多个属性，并可以将一个或多个包含在查询结果中，按任何顺序。 在前两个示例中，没有匿名类型是必需的这是因为查询中选择命名类型的元素：  
  
-   `custs1` 将包含一个字符串，集合，因为`cust.Name`是一个字符串。  
  
     [!code-vb[VbVbalrAnonymousTypes#30](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_9.vb)]  
  
-   `custs2` 包含一套`Customer`对象，因为每个元素的`customers`是`Customer`查询选择对象，并且整个元素。  
  
     [!code-vb[VbVbalrAnonymousTypes#31](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_10.vb)]  
  
 但是，相应的命名的类型并非始终可用。 你可能想要选择客户名称和一种用途，客户 ID 号和位置，与其他地址和客户名称、 地址和订单历史记录中的第三个。 匿名类型使你能够以任何顺序选择的属性，任意组合，而无需第一个声明新的命名的类型以保存结果。 相反，编译器将创建每个编译属性的匿名类型。 以下查询从每个选择仅客户的名称和 ID 号`Customer`对象在`customers`。 因此，编译器将创建仅包含那些两个属性的匿名类型。  
  
 [!code-vb[VbVbalrAnonymousTYpes#32](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_11.vb)]  
  
 名称和匿名类型中的属性的数据类型，将从的自变量`Select`，`cust.Name`和`cust.ID`。 中创建的查询的匿名类型的属性始终是键属性。 当`custs3`在下面的示例执行`For Each`循环，结果是具有两个键属性的匿名类型的实例的集合`Name`和`ID`。  
  
 [!code-vb[VbVbalrAnonymousTypes#33](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_12.vb)]  
  
 通过所表示的集合中的元素`custs3`强类型，并以浏览可用的属性并确保其类型，可以使用 IntelliSense。  
  
 有关详细信息，请参阅[Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)。  
  
## <a name="deciding-whether-to-use-anonymous-types"></a>决定是否使用匿名类型  
 作为匿名类的实例创建的对象之前，考虑这是否是最佳选项。 例如，如果你想要创建的临时对象，以包含相关的数据，并且具有无需其他字段和完整类可能包含的方法，匿名类型是一个不错的解决方案。 匿名类型也是方便的如果你需要每个声明中，选择不同的属性或如果你想要更改属性的顺序。 但是，如果你的项目包括几个对象的固定顺序有相同的属性，你可以声明它们更轻松地通过使用类构造函数中使用命名的类型。 例如，使用适当的构造函数，它是更轻松地声明的几个实例`Product`类比声明匿名类型的几个实例。  
  
 [!code-vb[VbVbalrAnonymousTypes#9](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_13.vb)]  
  
 命名类型的另一个优点是编译器可以捕获属性名称的无意拼写错误。 在前面的示例中， `firstProd2`， `secondProd2`，和`thirdProd2`都应是相同的匿名类型的实例。 但是，如果敧意外声明`thirdProd2`在通过以下方式之一，其类型将是不同的`firstProd2`和`secondProd2`。  
  
 [!code-vb[VbVbalrAnonymousTypes#10](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_14.vb)]  
  
 更重要的是，有不适用于命名类型的实例的匿名类型的使用限制。 `firstProd2``secondProd2`，和`thirdProd2`是相同的匿名类型的实例。 但是，共享的匿名类型的名称不可用，并且不能出现的地方类型名称在代码中。 例如，匿名类型不能用于定义方法签名，若要声明另一个变量或字段，或在任何类型声明中。 因此，匿名类型是不适当，你必须在方法之间共享信息。  
  
## <a name="an-anonymous-type-definition"></a>匿名类型定义  
 在响应的匿名类型的实例声明时，编译器将创建包含指定的属性的新类定义。  
  
 如果匿名类型包含至少一个键属性，定义将重写继承自的三个成员<xref:System.Object>: <xref:System.Object.Equals%2A>， <xref:System.Object.GetHashCode%2A>，和<xref:System.Object.ToString%2A>。 代码生成测试相等性，并确定哈希代码值会考虑只是键属性。 如果匿名类型包含任何键属性，仅<xref:System.Object.ToString%2A>被重写。 匿名类型的显式命名的属性不能与这些生成的方法冲突。 也就是说，不能使用`.Equals`， `.GetHashCode`，或`.ToString`以 name 属性。  
  
 至少具有一个匿名类型定义的键属性还实现<xref:System.IEquatable%601?displayProperty=nameWithType>接口，其中`T`是匿名类型的类型。  
  
 有关由编译器和重写方法的功能创建的代码的详细信息，请参阅[匿名类型定义](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)。  
  
## <a name="see-also"></a>请参阅  
 [对象初始值设定项：命名类型和匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [如何：推断匿名类型声明中的属性名和类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 [匿名类型定义](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)  
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)
