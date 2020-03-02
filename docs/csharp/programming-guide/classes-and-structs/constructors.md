---
title: 构造函数 - C# 编程指南
ms.date: 05/05/2017
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
ms.openlocfilehash: 8eedfaed111f01cc2ec55a2f42df66d4588bd42f
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626732"
---
# <a name="constructors-c-programming-guide"></a><span data-ttu-id="27662-102">构造函数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="27662-102">Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="27662-103">每当创建[类](../../language-reference/keywords/class.md)或[结构](../../language-reference/builtin-types/struct.md)时，将会调用其构造函数。</span><span class="sxs-lookup"><span data-stu-id="27662-103">Whenever a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/builtin-types/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="27662-104">类或结构可能具有采用不同参数的多个构造函数。</span><span class="sxs-lookup"><span data-stu-id="27662-104">A class or struct may have multiple constructors that take different arguments.</span></span> <span data-ttu-id="27662-105">使用构造函数，程序员能够设置默认值、限制实例化，并编写灵活易读的代码。</span><span class="sxs-lookup"><span data-stu-id="27662-105">Constructors enable the programmer to set default values, limit instantiation, and write code that is flexible and easy to read.</span></span> <span data-ttu-id="27662-106">有关详细信息和示例，请参阅[使用构造函数](./using-constructors.md)和[实例构造函数](./instance-constructors.md)。</span><span class="sxs-lookup"><span data-stu-id="27662-106">For more information and examples, see [Using Constructors](./using-constructors.md) and [Instance Constructors](./instance-constructors.md).</span></span>  

## <a name="parameterless-constructors"></a><span data-ttu-id="27662-107">无参数构造函数</span><span class="sxs-lookup"><span data-stu-id="27662-107">Parameterless constructors</span></span>
  
<span data-ttu-id="27662-108">如果没有为类提供构造函数，则 C# 将默认创建一个构造函数，该函数会实例化对象并将成员变量设置为默认值，如 [C# 类型的默认值](../../language-reference/builtin-types/default-values.md)中所列。</span><span class="sxs-lookup"><span data-stu-id="27662-108">If you don't provide a constructor for your class, C# creates one by default that instantiates the object and sets member variables to the default values as listed in the [Default values of C# types](../../language-reference/builtin-types/default-values.md) article.</span></span> <span data-ttu-id="27662-109">如果没有为结构提供构造函数，C# 将依赖于隐式无参数构造函数，自动将每个字段初始化为其默认值  。</span><span class="sxs-lookup"><span data-stu-id="27662-109">If you don't provide a constructor for your struct, C# relies on an *implicit parameterless constructor* to automatically initialize each field to its default value.</span></span> <span data-ttu-id="27662-110">有关详细信息和示例，请参阅[实例构造函数](instance-constructors.md)。</span><span class="sxs-lookup"><span data-stu-id="27662-110">For more information and examples, see [Instance constructors](instance-constructors.md).</span></span>  

## <a name="constructor-syntax"></a><span data-ttu-id="27662-111">构造函数语法</span><span class="sxs-lookup"><span data-stu-id="27662-111">Constructor syntax</span></span>

<span data-ttu-id="27662-112">构造函数是一种方法，其名称与其类型的名称相同。</span><span class="sxs-lookup"><span data-stu-id="27662-112">A constructor is a method whose name is the same as the name of its type.</span></span> <span data-ttu-id="27662-113">其方法签名仅包含方法名称和其参数列表；它不包含返回类型。</span><span class="sxs-lookup"><span data-stu-id="27662-113">Its method signature includes only the method name and its parameter list; it does not include a return type.</span></span> <span data-ttu-id="27662-114">以下示例演示一个名为 `Person` 的类的构造函数。</span><span class="sxs-lookup"><span data-stu-id="27662-114">The following example shows the constructor for a class named `Person`.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

<span data-ttu-id="27662-115">如果某个构造函数可以作为单个语句实现，则可以使用[表达式主体定义](../statements-expressions-operators/expression-bodied-members.md)。</span><span class="sxs-lookup"><span data-stu-id="27662-115">If a constructor can be implemented as a single statement, you can use an [expression body definition](../statements-expressions-operators/expression-bodied-members.md).</span></span> <span data-ttu-id="27662-116">以下示例定义 `Location` 类，其构造函数具有一个名为“name”  的字符串参数。</span><span class="sxs-lookup"><span data-stu-id="27662-116">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="27662-117">表达式主体定义给 `locationName` 字段分配参数。</span><span class="sxs-lookup"><span data-stu-id="27662-117">The expression body definition assigns the argument to the `locationName` field.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a><span data-ttu-id="27662-118">静态构造函数</span><span class="sxs-lookup"><span data-stu-id="27662-118">Static constructors</span></span>

<span data-ttu-id="27662-119">前面的示例具有所有已展示的实例构造函数，这些构造函数创建一个新对象。</span><span class="sxs-lookup"><span data-stu-id="27662-119">The previous examples have all shown instance constructors, which create a new object.</span></span> <span data-ttu-id="27662-120">类或结构也可以具有静态构造函数，该静态构造函数初始化类型的静态成员。</span><span class="sxs-lookup"><span data-stu-id="27662-120">A class or struct can also have a static constructor, which initializes static members of the type.</span></span>  <span data-ttu-id="27662-121">静态构造函数是无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="27662-121">Static constructors are parameterless.</span></span> <span data-ttu-id="27662-122">如果未提供静态构造函数来初始化静态字段，C# 编译器会将静态字段初始化为其默认值，如 [C# 类型的默认值](../../language-reference/builtin-types/default-values.md)中所列。</span><span class="sxs-lookup"><span data-stu-id="27662-122">If you don't provide a static constructor to initialize static fields, the C# compiler initializes static fields to their default value as listed in the [Default values of C# types](../../language-reference/builtin-types/default-values.md) article.</span></span>

<span data-ttu-id="27662-123">以下示例使用静态构造函数来初始化静态字段。</span><span class="sxs-lookup"><span data-stu-id="27662-123">The following example uses a static constructor to initialize a static field.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

<span data-ttu-id="27662-124">也可以通过表达式主体定义来定义静态构造函数，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="27662-124">You can also define a static constructor with an expression body definition, as the following example shows.</span></span>

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

<span data-ttu-id="27662-125">有关详细信息和示例，请参阅[静态构造函数](./static-constructors.md)。</span><span class="sxs-lookup"><span data-stu-id="27662-125">For more information and examples, see [Static Constructors](./static-constructors.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="27662-126">本节内容</span><span class="sxs-lookup"><span data-stu-id="27662-126">In This Section</span></span>  
 [<span data-ttu-id="27662-127">使用构造函数</span><span class="sxs-lookup"><span data-stu-id="27662-127">Using Constructors</span></span>](./using-constructors.md)  
  
 [<span data-ttu-id="27662-128">实例构造函数</span><span class="sxs-lookup"><span data-stu-id="27662-128">Instance Constructors</span></span>](./instance-constructors.md)  
  
 [<span data-ttu-id="27662-129">私有构造函数</span><span class="sxs-lookup"><span data-stu-id="27662-129">Private Constructors</span></span>](./private-constructors.md)  
  
 [<span data-ttu-id="27662-130">静态构造函数</span><span class="sxs-lookup"><span data-stu-id="27662-130">Static Constructors</span></span>](./static-constructors.md)  
  
 [<span data-ttu-id="27662-131">如何编写复制构造函数</span><span class="sxs-lookup"><span data-stu-id="27662-131">How to write a copy constructor</span></span>](./how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a><span data-ttu-id="27662-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="27662-132">See also</span></span>

- [<span data-ttu-id="27662-133">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="27662-133">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="27662-134">类和结构</span><span class="sxs-lookup"><span data-stu-id="27662-134">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="27662-135">终结器</span><span class="sxs-lookup"><span data-stu-id="27662-135">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="27662-136">static</span><span class="sxs-lookup"><span data-stu-id="27662-136">static</span></span>](../../language-reference/keywords/static.md)
- <span data-ttu-id="27662-137">[Why Do Initializers Run In The Opposite Order As Constructors?Part One](https://docs.microsoft.com/archive/blogs/ericlippert/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)（为何初始值设定项作为构造函数以相反顺序运行？第一部分）</span><span class="sxs-lookup"><span data-stu-id="27662-137">[Why Do Initializers Run In The Opposite Order As Constructors? Part One](https://docs.microsoft.com/archive/blogs/ericlippert/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)</span></span>
