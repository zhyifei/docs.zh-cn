---
title: 对象和集合初始值设定项 - C# 编程指南
ms.custom: seodec18
ms.date: 12/19/2018
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
ms.openlocfilehash: bd49834c45f6e07a99be5a1f4293e938eed2cc77
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2019
ms.locfileid: "67267720"
---
# <a name="object-and-collection-initializers-c-programming-guide"></a><span data-ttu-id="43a69-102">对象和集合初始值设定项（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="43a69-102">Object and Collection Initializers (C# Programming Guide)</span></span>

<span data-ttu-id="43a69-103">使用 C# 可以在单条语句中实例化对象或集合并执行成员分配。</span><span class="sxs-lookup"><span data-stu-id="43a69-103">C# lets you instantiate an object or collection and perform member assignments in a single statement.</span></span>

## <a name="object-initializers"></a><span data-ttu-id="43a69-104">对象初始值设定项</span><span class="sxs-lookup"><span data-stu-id="43a69-104">Object initializers</span></span>

<span data-ttu-id="43a69-105">使用对象初始值设定项，你可以在创建对象时向对象的任何可访问字段或属性分配值，而无需调用后跟赋值语句行的构造函数。</span><span class="sxs-lookup"><span data-stu-id="43a69-105">Object initializers let you assign values to any accessible fields or properties of an object at creation time without having to invoke a constructor followed by lines of assignment statements.</span></span> <span data-ttu-id="43a69-106">利用对象初始值设定项语法，你可为构造函数指定参数或忽略参数（以及括号语法）。</span><span class="sxs-lookup"><span data-stu-id="43a69-106">The object initializer syntax enables you to specify arguments for a constructor or omit the arguments (and parentheses syntax).</span></span>  <span data-ttu-id="43a69-107">以下示例演示如何使用具有命名类型 `Cat` 的对象初始值设定项以及如何调用无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="43a69-107">The following example shows how to use an object initializer with a named type, `Cat` and how to invoke the parameterless constructor.</span></span> <span data-ttu-id="43a69-108">请注意，自动实现的属性在 `Cat` 类中的用法。</span><span class="sxs-lookup"><span data-stu-id="43a69-108">Note the use of auto-implemented properties in the `Cat` class.</span></span> <span data-ttu-id="43a69-109">有关详细信息，请参阅[自动实现的属性](auto-implemented-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="43a69-109">For more information, see [Auto-Implemented Properties](auto-implemented-properties.md).</span></span>  
  
[!code-csharp[ObjectInitializer1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#CatDeclaration)]  
[!code-csharp[ObjectInitializer1a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ObjectPropertyInitialization)]  
 
<span data-ttu-id="43a69-110">对象初始值设定项语法允许你创建一个实例，然后将具有其分配属性的新建对象指定给赋值中的变量。</span><span class="sxs-lookup"><span data-stu-id="43a69-110">The object initializers syntax allows you to create an instance, and after that it assigns the newly created object, with its assigned properties, to the variable in the assignment.</span></span>

<span data-ttu-id="43a69-111">从 C# 6 开始，除了分配字段和属性外，对象初始值设定项还可以设置索引器。</span><span class="sxs-lookup"><span data-stu-id="43a69-111">Starting with C# 6, object initializers can set indexers, in addition to assigning fields and properties.</span></span> <span data-ttu-id="43a69-112">请思考这个基本的 `Matrix` 类：</span><span class="sxs-lookup"><span data-stu-id="43a69-112">Consider this basic `Matrix` class:</span></span>

[!code-csharp[ObjectInitializer2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixDeclaration)]  

<span data-ttu-id="43a69-113">可以使用以下代码初始化标识矩阵：</span><span class="sxs-lookup"><span data-stu-id="43a69-113">You could initialize the identity matrix with the following code:</span></span>

[!code-csharp[ObjectInitializer2a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixInitialization)]  

<span data-ttu-id="43a69-114">包含可访问资源库的任何可访问索引器都可以用作对象初始值设定项中的表达式之一，这与参数的数量或类型无关。</span><span class="sxs-lookup"><span data-stu-id="43a69-114">Any accessible indexer that contains an accessible setter can be used as one of the expressions in an object initializer, regardless of the number or types of arguments.</span></span> <span data-ttu-id="43a69-115">索引参数构成左侧赋值，而表达式右侧是值。</span><span class="sxs-lookup"><span data-stu-id="43a69-115">The index arguments form the left side of the assignment, and the value is the right side of the expression.</span></span>  <span data-ttu-id="43a69-116">例如，如果 `IndexersExample` 具有适当的索引器，则这些都是有效的：</span><span class="sxs-lookup"><span data-stu-id="43a69-116">For example, these are all valid if `IndexersExample` has the appropriate indexers:</span></span>

```csharp
var thing = new IndexersExample {
    name = "object one",
    [1] = '1',
    [2] = '4',
    [3] = '9',
    Size = Math.PI,
    ['C',4] = "Middle C"
}
```

<span data-ttu-id="43a69-117">对于要进行编译的前面的代码，`IndexersExample` 类型必须具有以下成员：</span><span class="sxs-lookup"><span data-stu-id="43a69-117">For the preceding code to compile, the `IndexersExample` type must have the following members:</span></span>

```csharp
public string name;
public double Size { set { ... }; }
public char this[int i] { set { ... }; }
public string this[char c, int i] {  set { ... }; }
```

## <a name="object-initializers-with-anonymous-types"></a><span data-ttu-id="43a69-118">具有匿名类型的对象初始值设定项</span><span class="sxs-lookup"><span data-stu-id="43a69-118">Object Initializers with anonymous types</span></span>

<span data-ttu-id="43a69-119">尽管对象初始值设定项可用于任何上下文中，但它们在 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 查询表达式中特别有用。</span><span class="sxs-lookup"><span data-stu-id="43a69-119">Although object initializers can be used in any context, they are especially useful in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="43a69-120">查询表达式常使用只能通过使用对象初始值设定项进行初始化的[匿名类型](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)，如下面的声明所示。</span><span class="sxs-lookup"><span data-stu-id="43a69-120">Query expressions make frequent use of [anonymous types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md), which can only be initialized by using an object initializer, as shown in the following declaration.</span></span>  

```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```

<span data-ttu-id="43a69-121">利用匿名类型，[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 查询表达式中的 `select` 子句可以将原始序列的对象转换为其值和形状可能不同于原始序列的对象。</span><span class="sxs-lookup"><span data-stu-id="43a69-121">Anonymous types enable the `select` clause in a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expression to transform objects of the original sequence into objects whose value and shape may differ from the original.</span></span> <span data-ttu-id="43a69-122">如果你只想存储某个序列中每个对象的部分信息，则这很有用。</span><span class="sxs-lookup"><span data-stu-id="43a69-122">This is useful if you want to store only a part of the information from each object in a sequence.</span></span> <span data-ttu-id="43a69-123">在下面的示例中，假定产品对象 (`p`) 包含很多字段和方法，而你只想创建包含产品名和单价的对象序列。</span><span class="sxs-lookup"><span data-stu-id="43a69-123">In the following example, assume that a product object (`p`) contains many fields and methods, and that you are only interested in creating a sequence of objects that contain the product name and the unit price.</span></span>  
  
[!code-csharp[ObjectInitializer3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#AnonymousUse)]  

<span data-ttu-id="43a69-124">执行此查询时，`productInfos` 变量将包含一系列对象，这些对象可以在 `foreach` 语句中进行访问，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="43a69-124">When this query is executed, the `productInfos` variable will contain a sequence of objects that can be accessed in a `foreach` statement as shown in this example:</span></span>  

```csharp
foreach(var p in productInfos){...}  
```

<span data-ttu-id="43a69-125">新的匿名类型中的每个对象都具有两个公共属性，这两个属性接收与原始对象中的属性或字段相同的名称。</span><span class="sxs-lookup"><span data-stu-id="43a69-125">Each object in the new anonymous type has two public properties that receive the same names as the properties or fields in the original object.</span></span> <span data-ttu-id="43a69-126">你还可在创建匿名类型时重命名字段；下面的示例将 `UnitPrice` 字段重命名为 `Price`。</span><span class="sxs-lookup"><span data-stu-id="43a69-126">You can also rename a field when you are creating an anonymous type; the following example renames the `UnitPrice` field to `Price`.</span></span>  

```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```

## <a name="collection-initializers"></a><span data-ttu-id="43a69-127">集合初始值设定项</span><span class="sxs-lookup"><span data-stu-id="43a69-127">Collection initializers</span></span>

<span data-ttu-id="43a69-128">在初始化实现 <xref:System.Collections.IEnumerable> 的集合类型和初始化使用适当的签名作为实例方法或扩展方法的 `Add` 时，集合初始值设定项允许指定一个或多个元素初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="43a69-128">Collection initializers let you specify one or more element initializers when you initialize a collection type that implements <xref:System.Collections.IEnumerable> and has `Add` with the appropriate signature as an instance method or an extension method.</span></span> <span data-ttu-id="43a69-129">元素初始值设定项可以是简单的值、表达式或对象初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="43a69-129">The element initializers can be a simple value, an expression, or an object initializer.</span></span> <span data-ttu-id="43a69-130">通过使用集合初始值设定项，无需指定多个调用；编译器将自动添加这些调用。</span><span class="sxs-lookup"><span data-stu-id="43a69-130">By using a collection initializer, you do not have to specify multiple calls; the compiler adds the calls automatically.</span></span>  
  
<span data-ttu-id="43a69-131">下面的示例演示了两个简单的集合初始值设定项：</span><span class="sxs-lookup"><span data-stu-id="43a69-131">The following example shows two simple collection initializers:</span></span>  

```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```

<span data-ttu-id="43a69-132">下面的集合初始值设定项使用对象初始值设定项来初始化上一个示例中定义的 `Cat` 类的对象。</span><span class="sxs-lookup"><span data-stu-id="43a69-132">The following collection initializer uses object initializers to initialize objects of the `Cat` class defined in a previous example.</span></span> <span data-ttu-id="43a69-133">请注意，各个对象初始值设定项分别括在大括号中且用逗号隔开。</span><span class="sxs-lookup"><span data-stu-id="43a69-133">Note that the individual object initializers are enclosed in braces and separated by commas.</span></span>  
  
[!code-csharp[ListInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitializer)]  
  
<span data-ttu-id="43a69-134">如果集合的 `Add` 方法允许，则可以将 [null](../../language-reference/keywords/null.md) 指定为集合初始值设定项中的一个元素。</span><span class="sxs-lookup"><span data-stu-id="43a69-134">You can specify [null](../../language-reference/keywords/null.md) as an element in a collection initializer if the collection's `Add` method allows it.</span></span>  
  
[!code-csharp[ListInitializerNull](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitialerWithNull)]  
  
 <span data-ttu-id="43a69-135">如果集合支持读取/写入索引，可以指定索引元素。</span><span class="sxs-lookup"><span data-stu-id="43a69-135">You can specify indexed elements if the collection supports read / write indexing.</span></span>
  
[!code-csharp[DictionaryInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryIndexerInitializer)]  

<span data-ttu-id="43a69-136">前面的示例生成调用 <xref:System.Collections.Generic.Dictionary%602.Item(%600)> 以设置值的代码。</span><span class="sxs-lookup"><span data-stu-id="43a69-136">The preceding sample generates code that calls the <xref:System.Collections.Generic.Dictionary%602.Item(%600)> to set the values.</span></span> <span data-ttu-id="43a69-137">从 C# 6 开始，可以使用以下语法初始化字典和其他关联容器。</span><span class="sxs-lookup"><span data-stu-id="43a69-137">Beginning with C# 6, you can initialize dictionaries and other associative containers using the following syntax.</span></span> <span data-ttu-id="43a69-138">请注意，它使用具有多个值的对象，而不是带括号和赋值的索引器语法：</span><span class="sxs-lookup"><span data-stu-id="43a69-138">Notice that instead of indexer syntax, with parentheses and an assignment, it uses an object with multiple values:</span></span>

[!code-csharp[DictionaryAddInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryAddInitializer)]  

<span data-ttu-id="43a69-139">此初始值设定项示例调用 <xref:System.Collections.Generic.Dictionary%602.Add(%600,%601)>，将这三个项添加到字典中。</span><span class="sxs-lookup"><span data-stu-id="43a69-139">This initializer example calls <xref:System.Collections.Generic.Dictionary%602.Add(%600,%601)> to add the three items into the dictionary.</span></span> <span data-ttu-id="43a69-140">由于编译器生成的方法调用不同，这两种初始化关联集合的不同方法的行为略有不同。</span><span class="sxs-lookup"><span data-stu-id="43a69-140">These two different ways to initialize associative collections have slightly different behavior because of the method calls the compiler generates.</span></span> <span data-ttu-id="43a69-141">这两种变量都适用于 `Dictionary` 类。</span><span class="sxs-lookup"><span data-stu-id="43a69-141">Both variants work with the `Dictionary` class.</span></span> <span data-ttu-id="43a69-142">其他类型根据它们的公共 API 可能只支持两者中的一种。</span><span class="sxs-lookup"><span data-stu-id="43a69-142">Other types may only support one or the other based on their public API.</span></span>

## <a name="examples"></a><span data-ttu-id="43a69-143">示例</span><span class="sxs-lookup"><span data-stu-id="43a69-143">Examples</span></span>

<span data-ttu-id="43a69-144">下例结合了对象和集合初始值设定项的概念。</span><span class="sxs-lookup"><span data-stu-id="43a69-144">The following example combines the concepts of object and collection initializers.</span></span>

[!code-csharp[InitializerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullExample)]  

<span data-ttu-id="43a69-145">下面的示例展示了实现 <xref:System.Collections.IEnumerable> 且包含具有多个参数的 `Add` 方法的一个对象，它使用在列表中每项具有多个元素的集合初始值设定项，这些元素对应于 `Add` 方法的签名。</span><span class="sxs-lookup"><span data-stu-id="43a69-145">The following example shows an object that implements <xref:System.Collections.IEnumerable> and contains an `Add` method with multiple parameters, It uses a collection initializer with multiple elements per item in the list that correspond to the signature of the `Add` method.</span></span>

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullListExample)]  

<span data-ttu-id="43a69-146">`Add` 方法可使用 `params` 关键字来获取可变数量的自变量，如下例中所示。</span><span class="sxs-lookup"><span data-stu-id="43a69-146">`Add` methods can use the `params` keyword to take a variable number of arguments, as shown in the following example.</span></span> <span data-ttu-id="43a69-147">此示例还演示了索引器的自定义实现，以使用索引初始化集合。</span><span class="sxs-lookup"><span data-stu-id="43a69-147">This example also demonstrates the custom implementation of an indexer to initialize a collection using indexes.</span></span>

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullDictionaryInitializer)]  

## <a name="see-also"></a><span data-ttu-id="43a69-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="43a69-148">See also</span></span>

- [<span data-ttu-id="43a69-149">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="43a69-149">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="43a69-150">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="43a69-150">LINQ Query Expressions</span></span>](../linq-query-expressions/index.md)
- [<span data-ttu-id="43a69-151">匿名类型</span><span class="sxs-lookup"><span data-stu-id="43a69-151">Anonymous Types</span></span>](anonymous-types.md)
