---
title: 构造函数 - C# 编程指南
ms.custom: seodec18
ms.date: 05/05/2017
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
ms.openlocfilehash: e88cc9b36f64a559105620359f4c163978cf9d8c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692254"
---
# <a name="constructors-c-programming-guide"></a><span data-ttu-id="4ea36-102">构造函数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="4ea36-102">Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="4ea36-103">每当创建[类](../../../csharp/language-reference/keywords/class.md)或[结构](../../../csharp/language-reference/keywords/struct.md)时，将会调用其构造函数。</span><span class="sxs-lookup"><span data-stu-id="4ea36-103">Whenever a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="4ea36-104">类或结构可能具有采用不同参数的多个构造函数。</span><span class="sxs-lookup"><span data-stu-id="4ea36-104">A class or struct may have multiple constructors that take different arguments.</span></span> <span data-ttu-id="4ea36-105">使用构造函数，程序员能够设置默认值、限制实例化，并编写灵活易读的代码。</span><span class="sxs-lookup"><span data-stu-id="4ea36-105">Constructors enable the programmer to set default values, limit instantiation, and write code that is flexible and easy to read.</span></span> <span data-ttu-id="4ea36-106">有关详细信息和示例，请参阅[使用构造函数](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)和[实例构造函数](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)。</span><span class="sxs-lookup"><span data-stu-id="4ea36-106">For more information and examples, see [Using Constructors](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) and [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  

## <a name="default-constructors"></a><span data-ttu-id="4ea36-107">默认构造函数</span><span class="sxs-lookup"><span data-stu-id="4ea36-107">Default constructors</span></span>
  
<span data-ttu-id="4ea36-108">如果没有为类提供构造函数，默认情况下，C# 将创建一个会实例化对象并将成员变量设置为默认值的构造函数，如[默认值表](../../../csharp/language-reference/keywords/default-values-table.md)中所列。</span><span class="sxs-lookup"><span data-stu-id="4ea36-108">If you don't provide a constructor for your class, C# creates one by default that instantiates the object and sets member variables to the default values as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="4ea36-109">如果没有为结构提供构造函数，C# 将依赖于隐式默认构造函数，自动将值类型的每个字段初始化为其默认值，如[默认值表](../../../csharp/language-reference/keywords/default-values-table.md)中所列。</span><span class="sxs-lookup"><span data-stu-id="4ea36-109">If you don't provide a constructor for your struct, C# relies on an *implicit default constructor* to automatically initialize each field of a value type to its default value as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="4ea36-110">有关详细信息和示例，请参阅[实例构造函数](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)。</span><span class="sxs-lookup"><span data-stu-id="4ea36-110">For more information and examples, see [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  

## <a name="constructor-syntax"></a><span data-ttu-id="4ea36-111">构造函数语法</span><span class="sxs-lookup"><span data-stu-id="4ea36-111">Constructor syntax</span></span>

<span data-ttu-id="4ea36-112">构造函数是一种方法，其名称与其类型的名称相同。</span><span class="sxs-lookup"><span data-stu-id="4ea36-112">A constructor is a method whose name is the same as the name of its type.</span></span> <span data-ttu-id="4ea36-113">其方法签名仅包含方法名称和其参数列表；它不包含返回类型。</span><span class="sxs-lookup"><span data-stu-id="4ea36-113">Its method signature includes only the method name and its parameter list; it does not include a return type.</span></span> <span data-ttu-id="4ea36-114">以下示例演示一个名为 `Person` 的类的构造函数。</span><span class="sxs-lookup"><span data-stu-id="4ea36-114">The following example shows the constructor for a class named `Person`.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

<span data-ttu-id="4ea36-115">如果某个构造函数可以作为单个语句实现，则可以使用[表达式主体定义](../statements-expressions-operators/expression-bodied-members.md)。</span><span class="sxs-lookup"><span data-stu-id="4ea36-115">If a constructor can be implemented as a single statement, you can use an [expression body definition](../statements-expressions-operators/expression-bodied-members.md).</span></span> <span data-ttu-id="4ea36-116">以下示例定义 `Location` 类，其构造函数具有一个名为“name”的字符串参数。</span><span class="sxs-lookup"><span data-stu-id="4ea36-116">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="4ea36-117">表达式主体定义给 `locationName` 字段分配参数。</span><span class="sxs-lookup"><span data-stu-id="4ea36-117">The expression body definition assigns the argument to the `locationName` field.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a><span data-ttu-id="4ea36-118">静态构造函数</span><span class="sxs-lookup"><span data-stu-id="4ea36-118">Static constructors</span></span>

<span data-ttu-id="4ea36-119">前面的示例具有所有已展示的实例构造函数，这些构造函数创建一个新对象。</span><span class="sxs-lookup"><span data-stu-id="4ea36-119">The previous examples have all shown instance constructors, which create a new object.</span></span> <span data-ttu-id="4ea36-120">类或结构也可以具有静态构造函数，该静态构造函数初始化类型的静态成员。</span><span class="sxs-lookup"><span data-stu-id="4ea36-120">A class or struct can also have a static constructor, which initializes static members of the type.</span></span>  <span data-ttu-id="4ea36-121">静态构造函数是无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="4ea36-121">Static constructors are parameterless.</span></span> <span data-ttu-id="4ea36-122">如果未提供静态构造函数来初始化静态字段，C# 编译器将提供默认静态构造函数，该静态构造函数会将静态字段初始化为其默认值，如[默认值表](../../../csharp/language-reference/keywords/default-values-table.md)中所列。</span><span class="sxs-lookup"><span data-stu-id="4ea36-122">If you don't provide a static constructor to initialize static fields, the C# compiler will supply a default static constructor that initializes static fields to their default value as listed in the [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> 

<span data-ttu-id="4ea36-123">以下示例使用静态构造函数来初始化静态字段。</span><span class="sxs-lookup"><span data-stu-id="4ea36-123">The following example uses a static constructor to initialize a static field.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

<span data-ttu-id="4ea36-124">也可以通过表达式主体定义来定义静态构造函数，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="4ea36-124">You can also define a static constructor with an expression body definition, as the following example shows.</span></span> 

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

<span data-ttu-id="4ea36-125">有关详细信息和示例，请参阅[静态构造函数](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)。</span><span class="sxs-lookup"><span data-stu-id="4ea36-125">For more information and examples, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4ea36-126">本节内容</span><span class="sxs-lookup"><span data-stu-id="4ea36-126">In This Section</span></span>  
 [<span data-ttu-id="4ea36-127">使用构造函数</span><span class="sxs-lookup"><span data-stu-id="4ea36-127">Using Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
  
 [<span data-ttu-id="4ea36-128">实例构造函数</span><span class="sxs-lookup"><span data-stu-id="4ea36-128">Instance Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)  
  
 [<span data-ttu-id="4ea36-129">私有构造函数</span><span class="sxs-lookup"><span data-stu-id="4ea36-129">Private Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/private-constructors.md)  
  
 [<span data-ttu-id="4ea36-130">静态构造函数</span><span class="sxs-lookup"><span data-stu-id="4ea36-130">Static Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)  
  
 [<span data-ttu-id="4ea36-131">如何：编写复制构造函数</span><span class="sxs-lookup"><span data-stu-id="4ea36-131">How to: Write a Copy Constructor</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a><span data-ttu-id="4ea36-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ea36-132">See also</span></span>

- [<span data-ttu-id="4ea36-133">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="4ea36-133">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="4ea36-134">类和结构</span><span class="sxs-lookup"><span data-stu-id="4ea36-134">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="4ea36-135">终结器</span><span class="sxs-lookup"><span data-stu-id="4ea36-135">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
- [<span data-ttu-id="4ea36-136">static</span><span class="sxs-lookup"><span data-stu-id="4ea36-136">static</span></span>](../../../csharp/language-reference/keywords/static.md)
- <span data-ttu-id="4ea36-137">[Why Do Initializers Run In The Opposite Order As Constructors?Part One](https://blogs.msdn.microsoft.com/ericlippert/2008/02/15/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)（为何初始值设定项作为构造函数以相反顺序运行？第一部分）</span><span class="sxs-lookup"><span data-stu-id="4ea36-137">[Why Do Initializers Run In The Opposite Order As Constructors? Part One](https://blogs.msdn.microsoft.com/ericlippert/2008/02/15/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)</span></span>
