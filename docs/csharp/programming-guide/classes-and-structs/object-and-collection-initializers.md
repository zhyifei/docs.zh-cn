---
title: 对象和集合初始值设定项（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
ms.openlocfilehash: ad8127bfdd7178051077e6f3fe75c777acf5d345
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33321943"
---
# <a name="object-and-collection-initializers-c-programming-guide"></a><span data-ttu-id="5e3af-102">对象和集合初始值设定项（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="5e3af-102">Object and Collection Initializers (C# Programming Guide)</span></span>
<span data-ttu-id="5e3af-103">使用对象初始值设定项，你可以在创建对象时向对象的任何可访问字段或属性分配值，而无需调用后跟赋值语句行的构造函数。</span><span class="sxs-lookup"><span data-stu-id="5e3af-103">Object initializers let you assign values to any accessible fields or properties of an object at creation time without having to invoke a constructor followed by lines of assignment statements.</span></span> <span data-ttu-id="5e3af-104">利用对象初始值设定项语法，你可为构造函数指定参数或忽略参数（以及括号语法）。</span><span class="sxs-lookup"><span data-stu-id="5e3af-104">The object initializer syntax enables you to specify arguments for a constructor or omit the arguments (and parentheses syntax).</span></span>  <span data-ttu-id="5e3af-105">以下示例演示如何使用具有命名类型 `Cat` 的对象初始值设定项以及如何调用默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="5e3af-105">The following example shows how to use an object initializer with a named type, `Cat` and how to invoke the default constructor.</span></span> <span data-ttu-id="5e3af-106">请注意，自动实现的属性在 `Cat` 类中的用法。</span><span class="sxs-lookup"><span data-stu-id="5e3af-106">Note the use of auto-implemented properties in the `Cat` class.</span></span> <span data-ttu-id="5e3af-107">有关详细信息，请参阅[自动实现的属性](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="5e3af-107">For more information, see [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>  
  
 [!code-csharp[csProgGuideLINQ#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_1.cs)]  
  
 [!code-csharp[csProgGuideLINQ#45](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_2.cs)] 
 
<span data-ttu-id="5e3af-108">对象初始值设定项语法允许你创建一个实例，然后将具有其分配属性的新建对象指定给赋值中的变量。</span><span class="sxs-lookup"><span data-stu-id="5e3af-108">The object initializers syntax allows you to create an instance, and after that it assigns the newly created object, with its assigned properties, to the variable in the assignment.</span></span>
  
## <a name="object-initializers-with-anonymous-types"></a><span data-ttu-id="5e3af-109">具有匿名类型的对象初始值设定项</span><span class="sxs-lookup"><span data-stu-id="5e3af-109">Object Initializers with anonymous types</span></span>  
 <span data-ttu-id="5e3af-110">尽管对象初始值设定项可用于任何上下文中，但它们在 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 查询表达式中特别有用。</span><span class="sxs-lookup"><span data-stu-id="5e3af-110">Although object initializers can be used in any context, they are especially useful in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="5e3af-111">查询表达式常使用只能通过使用对象初始值设定项进行初始化的[匿名类型](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)，如下面的声明所示。</span><span class="sxs-lookup"><span data-stu-id="5e3af-111">Query expressions make frequent use of [anonymous types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md), which can only be initialized by using an object initializer, as shown in the following declaration.</span></span>  
  
```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```  
  
 <span data-ttu-id="5e3af-112">利用匿名类型，[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 查询表达式中的 `select` 子句可以将原始序列的对象转换为其值和形状可能不同于原始序列的对象。</span><span class="sxs-lookup"><span data-stu-id="5e3af-112">Anonymous types enable the `select` clause in a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expression to transform objects of the original sequence into objects whose value and shape may differ from the original.</span></span> <span data-ttu-id="5e3af-113">如果你只想存储某个序列中每个对象的部分信息，则这很有用。</span><span class="sxs-lookup"><span data-stu-id="5e3af-113">This is useful if you want to store only a part of the information from each object in a sequence.</span></span> <span data-ttu-id="5e3af-114">在下面的示例中，假定产品对象 (`p`) 包含很多字段和方法，而你只想创建包含产品名和单价的对象序列。</span><span class="sxs-lookup"><span data-stu-id="5e3af-114">In the following example, assume that a product object (`p`) contains many fields and methods, and that you are only interested in creating a sequence of objects that contain the product name and the unit price.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_3.cs)]  
  
 <span data-ttu-id="5e3af-115">执行此查询时，`productInfos` 变量将包含一系列对象，这些对象可以在 `foreach` 语句中进行访问，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="5e3af-115">When this query is executed, the `productInfos` variable will contain a sequence of objects that can be accessed in a `foreach` statement as shown in this example:</span></span>  
  
```csharp
foreach(var p in productInfos){...}  
```  
  
 <span data-ttu-id="5e3af-116">新的匿名类型中的每个对象都具有两个公共属性，这两个属性接收与原始对象中的属性或字段相同的名称。</span><span class="sxs-lookup"><span data-stu-id="5e3af-116">Each object in the new anonymous type has two public properties which receive the same names as the properties or fields in the original object.</span></span> <span data-ttu-id="5e3af-117">你还可在创建匿名类型时重命名字段；下面的示例将 `UnitPrice` 字段重命名为 `Price`。</span><span class="sxs-lookup"><span data-stu-id="5e3af-117">You can also rename a field when you are creating an anonymous type; the following example renames the `UnitPrice` field to `Price`.</span></span>  
  
```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```  
  
## <a name="object-initializers-with-nullable-types"></a><span data-ttu-id="5e3af-118">具有可以为 null 的类型的对象初始值设定项</span><span class="sxs-lookup"><span data-stu-id="5e3af-118">Object initializers with nullable types</span></span>  
 <span data-ttu-id="5e3af-119">使用具有可以为 null 的结构的对象初始值设定项会导致编译时错误。</span><span class="sxs-lookup"><span data-stu-id="5e3af-119">It is a compile-time error to use an object initializer with a nullable struct.</span></span>  
  
## <a name="collection-initializers"></a><span data-ttu-id="5e3af-120">集合初始值设定项</span><span class="sxs-lookup"><span data-stu-id="5e3af-120">Collection initializers</span></span>  
 <span data-ttu-id="5e3af-121">在初始化实现 <xref:System.Collections.IEnumerable> 的集合类型和初始化使用适当的签名作为实例方法或扩展方法的 `Add` 时，集合初始值设定项允许指定一个或多个元素初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="5e3af-121">Collection initializers let you specify one or more element initializers when you initialize a collection type that implements <xref:System.Collections.IEnumerable> and has `Add` with the appropriate signature as an instance method or an extension method.</span></span> <span data-ttu-id="5e3af-122">元素初始值设定项可以是简单的值、表达式或对象初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="5e3af-122">The element initializers can be a simple value, an expression or an object initializer.</span></span> <span data-ttu-id="5e3af-123">通过使用集合初始值设定项，你将无需在源代码中指定对该类的 `Add` 方法的多个调用；编译器将添加这些调用。</span><span class="sxs-lookup"><span data-stu-id="5e3af-123">By using a collection initializer you do not have to specify multiple calls to the `Add` method of the class in your source code; the compiler adds the calls.</span></span>  
  
 <span data-ttu-id="5e3af-124">下面的示例演示了两个简单的集合初始值设定项：</span><span class="sxs-lookup"><span data-stu-id="5e3af-124">The following examples shows two simple collection initializers:</span></span>  
  
```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```  
  
 <span data-ttu-id="5e3af-125">下面的集合初始值设定项使用对象初始值设定项来初始化上一个示例中定义的 `Cat` 类的对象。</span><span class="sxs-lookup"><span data-stu-id="5e3af-125">The following collection initializer uses object initializers to initialize objects of the `Cat` class defined in a previous example.</span></span> <span data-ttu-id="5e3af-126">请注意，各个对象初始值设定项分别括在大括号中且用逗号隔开。</span><span class="sxs-lookup"><span data-stu-id="5e3af-126">Note that the individual object initializers are enclosed in braces and separated by commas.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_4.cs)]  
  
 <span data-ttu-id="5e3af-127">如果集合的 `Add` 方法允许，则可以将 [null](../../../csharp/language-reference/keywords/null.md) 指定为集合初始值设定项中的一个元素。</span><span class="sxs-lookup"><span data-stu-id="5e3af-127">You can specify [null](../../../csharp/language-reference/keywords/null.md) as an element in a collection initializer if the collection's `Add` method allows it.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_5.cs)]  
  
 <span data-ttu-id="5e3af-128">如果集合支持索引，可以指定索引元素。</span><span class="sxs-lookup"><span data-stu-id="5e3af-128">You can specify indexed elements if the collection supports indexing.</span></span>  
  
```csharp
var numbers = new Dictionary<int, string> {   
    [7] = "seven",   
    [9] = "nine",   
    [13] = "thirteen"   
};  
```  
  
## <a name="examples"></a><span data-ttu-id="5e3af-129">示例</span><span class="sxs-lookup"><span data-stu-id="5e3af-129">Examples</span></span>

 <span data-ttu-id="5e3af-130">下例结合了对象和集合初始值设定项的概念。</span><span class="sxs-lookup"><span data-stu-id="5e3af-130">The following example combines the concepts of object and collection initializers.</span></span>

 [!code-csharp[csProgGuideLINQ#46](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_6.cs)]  
 
 <span data-ttu-id="5e3af-131">在下面的示例中，实现包含 `Add` 方法（具有多个参数）的 <xref:System.Collections.IEnumerable> 的对象允许在列表中每项具有多个元素的集合初始值设定项与 `Add` 方法的签名对应。</span><span class="sxs-lookup"><span data-stu-id="5e3af-131">Shown in the following example, an object which implements <xref:System.Collections.IEnumerable> containing an `Add` method with multiple parameters allows for collection initializers with multiple elements per item in the list corresponding to the signature of the `Add` method.</span></span> 
 
 [!code-csharp[csProgGuideLINQ#84](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_7.cs)]
 
 <span data-ttu-id="5e3af-132">`Add` 方法可使用 `params` 关键字来获取可变数量的自变量，如下例中所示。</span><span class="sxs-lookup"><span data-stu-id="5e3af-132">`Add` methods can use the `params` keyword to take a variable number of arguments as shown in the following example.</span></span> <span data-ttu-id="5e3af-133">此示例还演示了索引器的自定义实现，以及使用索引初始化集合。</span><span class="sxs-lookup"><span data-stu-id="5e3af-133">This example demonstrates the custom implementation of an indexer as well to initialize a collection using indexes.</span></span>
 
 [!code-csharp[csProgGuideLINQ#85](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_8.cs)]
 
## <a name="see-also"></a><span data-ttu-id="5e3af-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e3af-134">See Also</span></span>  
 [<span data-ttu-id="5e3af-135">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5e3af-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5e3af-136">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="5e3af-136">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="5e3af-137">匿名类型</span><span class="sxs-lookup"><span data-stu-id="5e3af-137">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
