---
title: "支持 LINQ 的 C# 功能"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: LINQ [C#], features supporting LINQ
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2f5accb188e54e0d3e2b941832637ec33afc26b2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="c-features-that-support-linq"></a><span data-ttu-id="abaab-102">支持 LINQ 的 C# 功能</span><span class="sxs-lookup"><span data-stu-id="abaab-102">C# Features That Support LINQ</span></span>
<span data-ttu-id="abaab-103">下一节介绍 C# 3.0 中引入的新语言构造。</span><span class="sxs-lookup"><span data-stu-id="abaab-103">The following section introduces new language constructs introduced in C# 3.0.</span></span> <span data-ttu-id="abaab-104">虽然这些新功能在一定程度上都用于 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 查询，但并不限于 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]，如果认为有用，在任何情况下都可以使用这些新功能。</span><span class="sxs-lookup"><span data-stu-id="abaab-104">Although these new features are all used to a degree with [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, they are not limited to [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] and can be used in any context where you find them useful.</span></span>  
  
## <a name="query-expressions"></a><span data-ttu-id="abaab-105">查询表达式</span><span class="sxs-lookup"><span data-stu-id="abaab-105">Query Expressions</span></span>  
 <span data-ttu-id="abaab-106">查询表达式使用类似于 SQL 或 XQuery 的声明性语法来查询 IEnumerable 集合。</span><span class="sxs-lookup"><span data-stu-id="abaab-106">Queries expressions use a declarative syntax similar to SQL or XQuery to query over IEnumerable collections.</span></span> <span data-ttu-id="abaab-107">在编译时，查询语法转换为对 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 提供程序的标准查询运算符扩展方法实现的方法调用。</span><span class="sxs-lookup"><span data-stu-id="abaab-107">At compile time query syntax is converted to method calls to a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider's implementation of the standard query operator extension methods.</span></span> <span data-ttu-id="abaab-108">应用程序通过使用 `using` 指令指定适当的命名空间来控制范围内的标准查询运算符。</span><span class="sxs-lookup"><span data-stu-id="abaab-108">Applications control the standard query operators that are in scope by specifying the appropriate namespace with a `using` directive.</span></span> <span data-ttu-id="abaab-109">下面的查询表达式获取一个字符串数组，按字符串中的第一个字符对字符串进行分组，然后对各组进行排序。</span><span class="sxs-lookup"><span data-stu-id="abaab-109">The following query expression takes an array of strings, groups them according to the first character in the string, and orders the groups.</span></span>  
  
```  
var query = from str in stringArray  
            group str by str[0] into stringGroup  
            orderby stringGroup.Key  
            select stringGroup;  
```  
  
 <span data-ttu-id="abaab-110">有关详细信息，请参阅 [LINQ 查询表达式](../../../../csharp/programming-guide/linq-query-expressions/index.md)。</span><span class="sxs-lookup"><span data-stu-id="abaab-110">For more information, see [LINQ Query Expressions](../../../../csharp/programming-guide/linq-query-expressions/index.md).</span></span>  
  
## <a name="implicitly-typed-variables-var"></a><span data-ttu-id="abaab-111">隐式类型化变量 (var)</span><span class="sxs-lookup"><span data-stu-id="abaab-111">Implicitly Typed Variables (var)</span></span>  
 <span data-ttu-id="abaab-112">可以使用 [var](../../../../csharp/language-reference/keywords/var.md) 修饰符来指示编译器推断并分配类型，而不必在声明并初始化变量时显式指定类型，如下所示：</span><span class="sxs-lookup"><span data-stu-id="abaab-112">Instead of explicitly specifying a type when you declare and initialize a variable, you can use the [var](../../../../csharp/language-reference/keywords/var.md) modifier to instruct the compiler to infer and assign the type, as shown here:</span></span>  
  
```  
var number = 5;  
var name = "Virginia";  
var query = from str in stringArray  
            where str[0] == 'm'  
            select str;  
```  
  
 <span data-ttu-id="abaab-113">声明为 `var` 的变量与显式指定其类型的变量一样都是强类型。</span><span class="sxs-lookup"><span data-stu-id="abaab-113">Variables declared as `var` are just as strongly-typed as variables whose type you specify explicitly.</span></span> <span data-ttu-id="abaab-114">通过使用 `var`，可以创建匿名类型，但它可用于任何本地变量。</span><span class="sxs-lookup"><span data-stu-id="abaab-114">The use of `var` makes it possible to create anonymous types, but it can be used for any local variable.</span></span> <span data-ttu-id="abaab-115">也可以使用隐式类型声明数组。</span><span class="sxs-lookup"><span data-stu-id="abaab-115">Arrays can also be declared with implicit typing.</span></span>  
  
 <span data-ttu-id="abaab-116">有关详细信息，请参阅[隐式类型本地变量](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)。</span><span class="sxs-lookup"><span data-stu-id="abaab-116">For more information, see [Implicitly Typed Local Variables](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
## <a name="object-and-collection-initializers"></a><span data-ttu-id="abaab-117">对象和集合初始值设定项</span><span class="sxs-lookup"><span data-stu-id="abaab-117">Object and Collection Initializers</span></span>  
 <span data-ttu-id="abaab-118">通过对象和集合初始值设定项，初始化对象时无需为对象显式调用构造函数。</span><span class="sxs-lookup"><span data-stu-id="abaab-118">Object and collection initializers make it possible to initialize objects without explicitly calling a constructor for the object.</span></span> <span data-ttu-id="abaab-119">初始值设定项通常用在将源数据投影到新数据类型的查询表达式中。</span><span class="sxs-lookup"><span data-stu-id="abaab-119">Initializers are typically used in query expressions when they project the source data into a new data type.</span></span> <span data-ttu-id="abaab-120">假定一个类名为 `Customer`，具有公共 `Name` 和 `Phone` 属性，可以按下列代码中所示使用对象初始值设定项：</span><span class="sxs-lookup"><span data-stu-id="abaab-120">Assuming a class named `Customer` with public `Name` and `Phone` properties, the object initializer can be used as in the following code:</span></span>  
  
```  
Customer cust = new Customer { Name = "Mike", Phone = "555-1212" };  
```  
  
 <span data-ttu-id="abaab-121">有关详细信息，请参阅[对象和集合初始值设定项](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)。</span><span class="sxs-lookup"><span data-stu-id="abaab-121">For more information, see [Object and Collection Initializers](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span></span>  
  
## <a name="anonymous-types"></a><span data-ttu-id="abaab-122">匿名类型</span><span class="sxs-lookup"><span data-stu-id="abaab-122">Anonymous Types</span></span>  
 <span data-ttu-id="abaab-123">匿名类型由编译器构造，且类型名称只可用于编译器。</span><span class="sxs-lookup"><span data-stu-id="abaab-123">An anonymous type is constructed by the compiler and the type name is only available to the compiler.</span></span> <span data-ttu-id="abaab-124">匿名类型提供一种在查询结果中对一组属性临时分组的简便方法，无需定义单独的命名类型。</span><span class="sxs-lookup"><span data-stu-id="abaab-124">Anonymous types provide a convenient way to group a set of properties temporarily in a query result without having to define a separate named type.</span></span> <span data-ttu-id="abaab-125">使用新的表达式和对象初始值设定项初始化匿名类型，如下所示：</span><span class="sxs-lookup"><span data-stu-id="abaab-125">Anonymous types are initialized with a new expression and an object initializer, as shown here:</span></span>  
  
```  
select new {name = cust.Name, phone = cust.Phone};  
```  
  
 <span data-ttu-id="abaab-126">有关详细信息，请参阅[匿名类型](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="abaab-126">For more information, see [Anonymous Types](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>  
  
## <a name="extension-methods"></a><span data-ttu-id="abaab-127">扩展方法</span><span class="sxs-lookup"><span data-stu-id="abaab-127">Extension Methods</span></span>  
 <span data-ttu-id="abaab-128">扩展方法是一种可与类型关联的静态方法，因此可以像实例方法那样对类型调用它。</span><span class="sxs-lookup"><span data-stu-id="abaab-128">An extension method is a static method that can be associated with a type, so that it can be called as if it were an instance method on the type.</span></span> <span data-ttu-id="abaab-129">实际上，利用此功能，可以将新方法“添加”到现有类型，而不会实际修改它们。</span><span class="sxs-lookup"><span data-stu-id="abaab-129">This feature enables you to, in effect, "add" new methods to existing types without actually modifying them.</span></span> <span data-ttu-id="abaab-130">标准查询运算符是一组扩展方法，它们为实现 <xref:System.Collections.Generic.IEnumerable%601> 的任何类型提供 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 查询功能。</span><span class="sxs-lookup"><span data-stu-id="abaab-130">The standard query operators are a set of extension methods that provide [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query functionality for any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span>  
  
 <span data-ttu-id="abaab-131">有关详细信息，请参阅[扩展方法](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)</span><span class="sxs-lookup"><span data-stu-id="abaab-131">For more information, see [Extension Methods](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span>  
  
## <a name="lambda-expressions"></a><span data-ttu-id="abaab-132">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="abaab-132">Lambda Expressions</span></span>  
 <span data-ttu-id="abaab-133">Lambda 表达式是一种内联函数，该函数使用 => 运算符将输入参数与函数体分离，并且可以在编译时转换为委托或表达式树。</span><span class="sxs-lookup"><span data-stu-id="abaab-133">A lambda expression is an inline function that uses the => operator to separate input parameters from the function body and can be converted at compile time to a delegate or an expression tree.</span></span> <span data-ttu-id="abaab-134">在 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 编程中，在对标准查询运算符进行直接方法调用时，会遇到 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="abaab-134">In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] programming, you will encounter lambda expressions when you make direct method calls to the standard query operators.</span></span>  
  
 <span data-ttu-id="abaab-135">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="abaab-135">For more information, see:</span></span>  
  
-   [<span data-ttu-id="abaab-136">匿名函数</span><span class="sxs-lookup"><span data-stu-id="abaab-136">Anonymous Functions</span></span>](../../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)  
  
-   [<span data-ttu-id="abaab-137">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="abaab-137">Lambda Expressions</span></span>](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
  
-   [<span data-ttu-id="abaab-138">表达式树 (C#)</span><span class="sxs-lookup"><span data-stu-id="abaab-138">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)  
  
## <a name="auto-implemented-properties"></a><span data-ttu-id="abaab-139">自动实现的属性</span><span class="sxs-lookup"><span data-stu-id="abaab-139">Auto-Implemented Properties</span></span>  
 <span data-ttu-id="abaab-140">自动实现的属性使属性声明变得更简洁。</span><span class="sxs-lookup"><span data-stu-id="abaab-140">Auto-implemented properties make property-declaration more concise.</span></span> <span data-ttu-id="abaab-141">当你声明以下示例中所示的属性时，编译器会创建仅可以通过属性 getter 和 setter 访问的私有匿名支持字段。</span><span class="sxs-lookup"><span data-stu-id="abaab-141">When you declare a property as shown in the following example, the compiler will create a private, anonymous backing field that is not accessible except through the property getter and setter.</span></span>  
  
```  
public string Name {get; set;}  
```  
  
 <span data-ttu-id="abaab-142">有关详细信息，请参阅[自动实现的属性](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="abaab-142">For more information, see [Auto-Implemented Properties](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abaab-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="abaab-143">See Also</span></span>  
 [<span data-ttu-id="abaab-144">语言集成查询 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="abaab-144">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)
