---
title: 实例构造函数 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], instance constructors
- instance constructors [C#]
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
ms.openlocfilehash: e3ba825fcbf40e08a2cb4488de2bbed9257c2508
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592830"
---
# <a name="instance-constructors-c-programming-guide"></a><span data-ttu-id="dcb02-102">实例构造函数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="dcb02-102">Instance Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="dcb02-103">使用 [new](../../../csharp/language-reference/keywords/new.md) 表达式创建[类](../../../csharp/language-reference/keywords/class.md)的对象时，实例构造函数可用于创建和初始化任意实例成员变量。</span><span class="sxs-lookup"><span data-stu-id="dcb02-103">Instance constructors are used to create and initialize any instance member variables when you use the [new](../../../csharp/language-reference/keywords/new.md) expression to create an object of a [class](../../../csharp/language-reference/keywords/class.md).</span></span> <span data-ttu-id="dcb02-104">若要初始化[静态](../../../csharp/language-reference/keywords/static.md)类或非静态类中的静态变量，必须定义静态构造函数。</span><span class="sxs-lookup"><span data-stu-id="dcb02-104">To initialize a [static](../../../csharp/language-reference/keywords/static.md) class, or static variables in a non-static class, you must define a static constructor.</span></span> <span data-ttu-id="dcb02-105">有关详细信息，请参阅[静态构造函数](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)。</span><span class="sxs-lookup"><span data-stu-id="dcb02-105">For more information, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
 <span data-ttu-id="dcb02-106">下面的示例演示了实例构造函数：</span><span class="sxs-lookup"><span data-stu-id="dcb02-106">The following example shows an instance constructor:</span></span>  
  
 [!code-csharp[csProgGuideObjects#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_1.cs)]  
  
> [!NOTE]
>  <span data-ttu-id="dcb02-107">为清楚起见，此类包含公共字段。</span><span class="sxs-lookup"><span data-stu-id="dcb02-107">For clarity, this class contains public fields.</span></span> <span data-ttu-id="dcb02-108">建议在编程时不要使用公共字段，因为这种做法会使程序中任何位置的任何方法都可以不受限制、不经验证地访问对象的内部组件。</span><span class="sxs-lookup"><span data-stu-id="dcb02-108">The use of public fields is not a recommended programming practice because it allows any method anywhere in a program unrestricted and unverified access to an object's inner workings.</span></span> <span data-ttu-id="dcb02-109">数据成员通常应当为私有的，并且只应通过类方法和属性来访问。</span><span class="sxs-lookup"><span data-stu-id="dcb02-109">Data members should generally be private, and should be accessed only through class methods and properties.</span></span>  
  
 <span data-ttu-id="dcb02-110">只要创建基于 `Coords` 类的对象，就会调用此实例构造函数。</span><span class="sxs-lookup"><span data-stu-id="dcb02-110">This instance constructor is called whenever an object based on the `Coords` class is created.</span></span> <span data-ttu-id="dcb02-111">诸如此类不带参数的构造函数称为“默认构造函数”。</span><span class="sxs-lookup"><span data-stu-id="dcb02-111">A constructor like this one, which takes no arguments, is called a *default constructor*.</span></span> <span data-ttu-id="dcb02-112">然而，提供其他构造函数通常十分有用。</span><span class="sxs-lookup"><span data-stu-id="dcb02-112">However, it is often useful to provide additional constructors.</span></span> <span data-ttu-id="dcb02-113">例如，可以将构造函数添加到 `Coords` 类，以便可以为数据成员指定初始值：</span><span class="sxs-lookup"><span data-stu-id="dcb02-113">For example, we can add a constructor to the `Coords` class that allows us to specify the initial values for the data members:</span></span>  
  
 [!code-csharp[csProgGuideObjects#76](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_2.cs)]  
  
 <span data-ttu-id="dcb02-114">这样便可以用默认或特定的初始值创建 `CoOrd` 对象，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dcb02-114">This allows `CoOrd` objects to be created with default or specific initial values, like this:</span></span>  
  
 [!code-csharp[csProgGuideObjects#77](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_3.cs)]  
  
 <span data-ttu-id="dcb02-115">如果某个类没有构造函数，则会自动生成一个默认构造函数，并使用默认值来初始化对象字段。</span><span class="sxs-lookup"><span data-stu-id="dcb02-115">If a class does not have a constructor, a default constructor is automatically generated and default values are used to initialize the object fields.</span></span> <span data-ttu-id="dcb02-116">例如，[int](../../../csharp/language-reference/keywords/int.md) 初始化为 0。</span><span class="sxs-lookup"><span data-stu-id="dcb02-116">For example, an [int](../../../csharp/language-reference/keywords/int.md) is initialized to 0.</span></span> <span data-ttu-id="dcb02-117">有关默认值的详细信息，请参阅[默认值表](../../../csharp/language-reference/keywords/default-values-table.md)。</span><span class="sxs-lookup"><span data-stu-id="dcb02-117">For more information on default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="dcb02-118">由于 `Coords` 类的默认构造函数将所有数据成员都初始化为零，因此可以将它完全移除，而不会更改类的工作方式。</span><span class="sxs-lookup"><span data-stu-id="dcb02-118">Therefore, because the `Coords` class default constructor initializes all data members to zero, it can be removed altogether without changing how the class works.</span></span> <span data-ttu-id="dcb02-119">本主题稍后部分的示例 1 中提供了使用多个构造函数的完整示例，示例 2 中提供了自动生成的构造函数的示例。</span><span class="sxs-lookup"><span data-stu-id="dcb02-119">A complete example using multiple constructors is provided in Example 1 later in this topic, and an example of an automatically generated constructor is provided in Example 2.</span></span>  
  
 <span data-ttu-id="dcb02-120">也可以用实例构造函数来调用基类的实例构造函数。</span><span class="sxs-lookup"><span data-stu-id="dcb02-120">Instance constructors can also be used to call the instance constructors of base classes.</span></span> <span data-ttu-id="dcb02-121">类构造函数可通过初始值设定项来调用基类的构造函数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dcb02-121">The class constructor can invoke the constructor of the base class through the initializer, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#78](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_4.cs)]  
  
 <span data-ttu-id="dcb02-122">在此示例中，`Circle` 类将半径和高度的值传递给 `Shape`（`Circle` 从它派生而来）提供的构造函数。</span><span class="sxs-lookup"><span data-stu-id="dcb02-122">In this example, the `Circle` class passes values representing radius and height to the constructor provided by `Shape` from which `Circle` is derived.</span></span> <span data-ttu-id="dcb02-123">使用 `Shape` 和 `Circle` 的完整示例完整示例请见本主题中的示例 3。</span><span class="sxs-lookup"><span data-stu-id="dcb02-123">A complete example using `Shape` and `Circle` appears in this topic as Example 3.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="dcb02-124">示例 1</span><span class="sxs-lookup"><span data-stu-id="dcb02-124">Example 1</span></span>  
 <span data-ttu-id="dcb02-125">下面的示例说明包含两个类构造函数的类：一个类构造函数不带参数，另一个带有两个参数。</span><span class="sxs-lookup"><span data-stu-id="dcb02-125">The following example demonstrates a class with two class constructors, one without arguments and one with two arguments.</span></span>  
  
 [!code-csharp[csProgGuideObjects#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_5.cs)]  
  
## <a name="example-2"></a><span data-ttu-id="dcb02-126">示例 2</span><span class="sxs-lookup"><span data-stu-id="dcb02-126">Example 2</span></span>  
 <span data-ttu-id="dcb02-127">在此示例中，`Person` 没有任何构造函数；在这种情况下，将自动提供默认构造函数，同时将字段初始化为它们的默认值。</span><span class="sxs-lookup"><span data-stu-id="dcb02-127">In this example, the class `Person` does not have any constructors, in which case, a default constructor is automatically provided and the fields are initialized to their default values.</span></span>  
  
 [!code-csharp[csProgGuideObjects#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_6.cs)]  
  
 <span data-ttu-id="dcb02-128">请注意，`age` 的默认值为 `0`，`name` 的默认值为`null`。</span><span class="sxs-lookup"><span data-stu-id="dcb02-128">Notice that the default value of `age` is `0` and the default value of `name` is `null`.</span></span> <span data-ttu-id="dcb02-129">有关默认值的详细信息，请参阅[默认值表](../../../csharp/language-reference/keywords/default-values-table.md)。</span><span class="sxs-lookup"><span data-stu-id="dcb02-129">For more information on default values, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
## <a name="example-3"></a><span data-ttu-id="dcb02-130">示例 3</span><span class="sxs-lookup"><span data-stu-id="dcb02-130">Example 3</span></span>  
 <span data-ttu-id="dcb02-131">下面的示例说明使用基类初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="dcb02-131">The following example demonstrates using the base class initializer.</span></span> <span data-ttu-id="dcb02-132">`Circle` 类派生自常规类 `Shape`，`Cylinder` 类派生自 `Circle` 类。</span><span class="sxs-lookup"><span data-stu-id="dcb02-132">The `Circle` class is derived from the general class `Shape`, and the `Cylinder` class is derived from the `Circle` class.</span></span> <span data-ttu-id="dcb02-133">每个派生类的构造函数都使用其基类的初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="dcb02-133">The constructor on each derived class is using its base class initializer.</span></span>  
  
 [!code-csharp[csProgGuideObjects#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_7.cs)]  
  
 <span data-ttu-id="dcb02-134">有关调用基类构造函数的更多示例，请参阅 [virtual](../../../csharp/language-reference/keywords/virtual.md)、[override](../../../csharp/language-reference/keywords/override.md) 和 [base](../../../csharp/language-reference/keywords/base.md)。</span><span class="sxs-lookup"><span data-stu-id="dcb02-134">For more examples on invoking the base class constructors, see [virtual](../../../csharp/language-reference/keywords/virtual.md), [override](../../../csharp/language-reference/keywords/override.md), and [base](../../../csharp/language-reference/keywords/base.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcb02-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="dcb02-135">See also</span></span>

- [<span data-ttu-id="dcb02-136">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="dcb02-136">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="dcb02-137">类和结构</span><span class="sxs-lookup"><span data-stu-id="dcb02-137">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="dcb02-138">构造函数</span><span class="sxs-lookup"><span data-stu-id="dcb02-138">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)
- [<span data-ttu-id="dcb02-139">终结器</span><span class="sxs-lookup"><span data-stu-id="dcb02-139">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
- [<span data-ttu-id="dcb02-140">static</span><span class="sxs-lookup"><span data-stu-id="dcb02-140">static</span></span>](../../../csharp/language-reference/keywords/static.md)
