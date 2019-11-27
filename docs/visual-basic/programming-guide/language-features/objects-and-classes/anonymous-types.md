---
title: 匿名类型
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousType
helpviewer_keywords:
- anonymous types [Visual Basic], about anonymous types
- anonymous types [Visual Basic]
- types [Visual Basic], anonymous
ms.assetid: 7b87532c-4b3e-4398-8503-6ea9d67574a4
ms.openlocfilehash: 064c43274069be3951f816eaafafac0bbece7651
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347160"
---
# <a name="anonymous-types-visual-basic"></a>匿名类型 (Visual Basic)
Visual Basic 支持匿名类型，这使您无需为数据类型编写类定义即可创建对象。 此时，编译器将为你生成类。 该类没有可使用的名称，直接从 <xref:System.Object>继承，并且包含在声明对象时指定的属性。 由于未指定数据类型的名称，因此它被称为*匿名类型*。  
  
 下面的示例声明一个变量 `product`，并将其创建为具有两个属性 `Name` 和 `Price`的匿名类型的实例。  
  
 [!code-vb[VbVbalrAnonymousTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#1)]  
  
 *查询表达式*使用匿名类型来合并查询选择的数据列。 不能提前定义结果类型，因为无法预测特定查询可能选择的列。 利用匿名类型，您可以编写一个查询，以任意顺序选择任意数量的列。 编译器将创建与指定的属性和指定的顺序相匹配的数据类型。  
  
 在下面的示例中，`products` 是产品对象的列表，其中每个对象都具有许多属性。 变量 `namePriceQuery` 包含查询的定义，该查询在执行时返回具有两个属性 `Name` 和 `Price`的匿名类型的实例的集合。  
  
 [!code-vb[VbVbalrAnonymousTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#2)]  
  
 变量 `nameQuantityQuery` 包含查询的定义，该查询在执行时返回具有两个属性 `Name` 和 `OnHand`的匿名类型的实例的集合。  
  
 [!code-vb[VbVbalrAnonymousTypes#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#3)]  
  
 有关编译器为匿名类型创建的代码的详细信息，请参阅[匿名类型定义](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)。  
  
> [!CAUTION]
> 匿名类型的名称是编译器生成的，可能因编译而异。 你的代码不应使用或依赖于匿名类型的名称，因为在重新编译项目时，名称可能会更改。  
  
## <a name="declaring-an-anonymous-type"></a>声明匿名类型  
 匿名类型的实例的声明使用初始值设定项列表指定该类型的属性。 当你声明匿名类型而不是其他类元素（如方法或事件）时，只能指定属性。 在下面的示例中，`product1` 是具有两个属性的匿名类型的实例： `Name` 和 `Price`。  
  
 [!code-vb[VbVbalrAnonymousTypes#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#4)]  
  
 如果将属性指定为键属性，则可以使用这些属性来比较两个匿名类型实例是否相等。 但是，不能更改键属性的值。 有关详细信息，请参阅本主题后面的 "关键属性" 一节。  
  
 请注意，声明匿名类型的实例类似于通过使用对象初始值设定项声明命名类型的实例：  
  
 [!code-vb[VbVbalrAnonymousTypes#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#5)]  
  
 有关指定匿名类型属性的其他方法的详细信息，请参阅[如何：推断匿名类型声明中的属性名称和类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)。  
  
## <a name="key-properties"></a>键属性  
 键属性在几个基本方面不同于非键属性：  
  
- 仅比较键属性的值，以确定两个实例是否相等。  
  
- 键属性的值是只读的，无法更改。  
  
- 编译器生成的匿名类型的哈希代码算法中只包含密钥属性值。  
  
### <a name="equality"></a>相等  
 仅当匿名类型的实例是同一匿名类型的实例时，才可以相等。 如果两个实例满足以下条件，则编译器会将两个实例视为相同类型的实例：  
  
- 它们是在同一程序集中声明的。  
  
- 它们的属性具有相同的名称、相同的推断类型，并按相同顺序进行声明。 名称比较不区分大小写。  
  
- 每个中的相同属性都标记为键属性。  
  
- 每个声明中至少有一个属性是键属性。  
  
 没有键属性的匿名类型的实例仅等于其自身。  
  
 [!code-vb[VbVbalrAnonymousTypes#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#6)]  
  
 如果其键属性的值相等，则同一匿名类型的两个实例相等。 下面的示例演示如何测试相等性。  
  
 [!code-vb[VbVbalrAnonymousTypes#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#7)]  
  
### <a name="read-only-values"></a>只读值  
 键属性的值不能更改。 例如，在上一示例的 `prod8` 中，"`Name`" 和 "`Price`" 字段都是 `read-only`的，但 `OnHand` 可以更改。  
  
 [!code-vb[VbVbalrAnonymousTypes#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#8)]  
  
## <a name="anonymous-types-from-query-expressions"></a>查询表达式中的匿名类型  
 查询表达式并不总是需要创建匿名类型。 如果可能，它们使用现有类型来保存列数据。 如果查询返回数据源中的全部记录，或者只返回每个记录中的一个字段，则会发生这种情况。 在下面的代码示例中，`customers` 是 `Customer` 类的对象的集合。 类具有很多属性，并且可以按任意顺序在查询结果中包含一个或多个属性。 在前两个示例中，不需要匿名类型，因为查询选择了命名类型的元素：  
  
- `custs1` 包含字符串的集合，因为 `cust.Name` 是一个字符串。  
  
     [!code-vb[VbVbalrAnonymousTypes#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#30)]  
  
- `custs2` 包含 `Customer` 对象的集合，因为 `customers` 的每个元素都是一个 `Customer` 对象，并且整个元素都由查询选择。  
  
     [!code-vb[VbVbalrAnonymousTypes#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#31)]  
  
 但是，相应的命名类型并不始终可用。 你可能想要选择客户名称和地址以实现一个目的、为其他客户 ID 编号和位置，并为第三个帐户选择客户名称、地址和订单历史记录。 匿名类型使你可以按任意顺序选择任何属性组合，而无需首先声明新的命名类型来保存结果。 相反，编译器会为每个属性编译创建一个匿名类型。 下面的查询从 `customers`中的每个 `Customer` 对象中仅选择客户的名称和 ID 号。 因此，编译器将创建仅包含这两个属性的匿名类型。  
  
 [!code-vb[VbVbalrAnonymousTYpes#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#32)]  
  
 匿名类型中的属性的名称和数据类型都是从参数 `Select`、`cust.Name` 和 `cust.ID`获取的。 由查询创建的匿名类型中的属性始终是键属性。 当在以下 `For Each` 循环中执行 `custs3` 时，结果是具有两个键属性的匿名类型的实例的集合 `Name` 和 `ID`。  
  
 [!code-vb[VbVbalrAnonymousTypes#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#33)]  
  
 `custs3` 所表示的集合中的元素是强类型化的，你可以使用 IntelliSense 浏览可用属性并验证其类型。  
  
 有关详细信息，请参阅[Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)。  
  
## <a name="deciding-whether-to-use-anonymous-types"></a>确定是否使用匿名类型  
 在将对象创建为匿名类的实例之前，请考虑这是否是最佳选项。 例如，如果想要创建一个临时对象来包含相关数据，并且不需要完整类可能包含的其他字段和方法，则匿名类型是一个不错的解决方案。 如果需要为每个声明选择不同的属性，或者要更改属性的顺序，则匿名类型也是非常方便的。 但是，如果你的项目包含多个具有相同属性的对象（按固定顺序），则可以通过将命名类型用于类构造函数来更轻松地声明它们。 例如，使用适当的构造函数时，可以更轻松地声明 `Product` 类的多个实例，而不是声明匿名类型的多个实例。  
  
 [!code-vb[VbVbalrAnonymousTypes#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#9)]  
  
 命名类型的另一个优点是编译器可能会捕获属性名称的意外的误。 在前面的示例中，`firstProd2`、`secondProd2`和 `thirdProd2` 应为同一匿名类型的实例。 但是，如果您不小心通过以下方法之一声明 `thirdProd2`，其类型将不同于 `firstProd2` 和 `secondProd2`的类型。  
  
 [!code-vb[VbVbalrAnonymousTypes#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#10)]  
  
 更重要的是，对不适用于命名类型实例的匿名类型的使用存在一些限制。 `firstProd2`、`secondProd2`和 `thirdProd2` 是同一匿名类型的实例。 但是，共享匿名类型的名称不可用，因此不能出现在代码中需要类型名称的位置。 例如，匿名类型不能用于定义方法签名，也不能声明其他变量或字段，也不能用于任何类型声明。 因此，当必须跨方法共享信息时，匿名类型不适用。  
  
## <a name="an-anonymous-type-definition"></a>匿名类型定义  
 在响应匿名类型的实例的声明时，编译器会创建一个新的类定义，其中包含指定的属性。  
  
 如果匿名类型至少包含一个键属性，则定义将重写从 <xref:System.Object>继承的三个成员： <xref:System.Object.Equals%2A>、<xref:System.Object.GetHashCode%2A>和 <xref:System.Object.ToString%2A>。 为测试相等性和确定哈希代码值而生成的代码只考虑键属性。 如果匿名类型不包含键属性，则只会重写 <xref:System.Object.ToString%2A>。 匿名类型的显式命名属性不能与这些生成的方法冲突。 也就是说，不能使用 `.Equals`、`.GetHashCode`或 `.ToString` 来命名属性。  
  
 至少具有一个键属性的匿名类型定义也实现 <xref:System.IEquatable%601?displayProperty=nameWithType> 接口，其中 `T` 是匿名类型的类型。  
  
 有关编译器创建的代码和重写的方法的功能的详细信息，请参阅[匿名类型定义](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)。  
  
## <a name="see-also"></a>另请参阅

- [对象初始值设定项：命名类型和匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [如何：推断匿名类型声明中的属性名和类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [匿名类型定义](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [Key](../../../../visual-basic/language-reference/modifiers/key.md)
