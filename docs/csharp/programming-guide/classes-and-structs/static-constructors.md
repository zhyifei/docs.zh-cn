---
title: "静态构造函数（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ee5448095cf06c2473c94bae542c02557918271a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="static-constructors-c-programming-guide"></a><span data-ttu-id="55639-102">静态构造函数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="55639-102">Static Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="55639-103">静态构造函数用于初始化任何[静态](../../../csharp/language-reference/keywords/static.md)数据，或执行仅需执行一次的特定操作。</span><span class="sxs-lookup"><span data-stu-id="55639-103">A static constructor is used to initialize any [static](../../../csharp/language-reference/keywords/static.md) data, or to perform a particular action that needs to be performed once only.</span></span> <span data-ttu-id="55639-104">将在创建第一个实例或引用任何静态成员之前自动调用静态构造函数。</span><span class="sxs-lookup"><span data-stu-id="55639-104">It is called automatically before the first instance is created or any static members are referenced.</span></span>  
  
 [!code-csharp[csProgGuideObjects#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_1.cs)]  
  
 <span data-ttu-id="55639-105">静态构造函数具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="55639-105">Static constructors have the following properties:</span></span>  
  
-   <span data-ttu-id="55639-106">静态构造函数不使用访问修饰符或不具有参数。</span><span class="sxs-lookup"><span data-stu-id="55639-106">A static constructor does not take access modifiers or have parameters.</span></span>  
  
-   <span data-ttu-id="55639-107">在创建第一个实例或引用任何静态成员之前，将自动调用静态构造函数以初始化[类](../../../csharp/language-reference/keywords/class.md)。</span><span class="sxs-lookup"><span data-stu-id="55639-107">A static constructor is called automatically to initialize the [class](../../../csharp/language-reference/keywords/class.md) before the first instance is created or any static members are referenced.</span></span>  
  
-   <span data-ttu-id="55639-108">不能直接调用静态构造函数。</span><span class="sxs-lookup"><span data-stu-id="55639-108">A static constructor cannot be called directly.</span></span>  
  
-   <span data-ttu-id="55639-109">用户无法控制在程序中执行静态构造函数的时间。</span><span class="sxs-lookup"><span data-stu-id="55639-109">The user has no control on when the static constructor is executed in the program.</span></span>  
  
-   <span data-ttu-id="55639-110">静态构造函数的一种典型用法是在类使用日志文件且将构造函数用于将条目写入到此文件中时使用。</span><span class="sxs-lookup"><span data-stu-id="55639-110">A typical use of static constructors is when the class is using a log file and the constructor is used to write entries to this file.</span></span>  
  
-   <span data-ttu-id="55639-111">静态构造函数对于创建非托管代码的包装类也非常有用，这种情况下构造函数可调用 `LoadLibrary` 方法。</span><span class="sxs-lookup"><span data-stu-id="55639-111">Static constructors are also useful when creating wrapper classes for unmanaged code, when the constructor can call the `LoadLibrary` method.</span></span>  
  
-   <span data-ttu-id="55639-112">如果静态构造函数引发异常，运行时将不会再次调用该函数，并且类型在程序运行所在的应用程序域的生存期内将保持未初始化。</span><span class="sxs-lookup"><span data-stu-id="55639-112">If a static constructor throws an exception, the runtime will not invoke it a second time, and the type will remain uninitialized for the lifetime of the application domain in which your program is running.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55639-113">示例</span><span class="sxs-lookup"><span data-stu-id="55639-113">Example</span></span>  
 <span data-ttu-id="55639-114">在此示例中，类 `Bus` 具有静态构造函数。</span><span class="sxs-lookup"><span data-stu-id="55639-114">In this example, class `Bus` has a static constructor.</span></span> <span data-ttu-id="55639-115">创建 `Bus` 的第一个实例 (`bus1`) 时，将调用该静态构造函数，以便初始化类。</span><span class="sxs-lookup"><span data-stu-id="55639-115">When the first instance of `Bus` is created (`bus1`), the static constructor is invoked to initialize the class.</span></span> <span data-ttu-id="55639-116">示例输出验证即使创建了两个 `Bus` 的实例，静态构造函数也仅运行一次，并且在实例构造函数运行前运行。</span><span class="sxs-lookup"><span data-stu-id="55639-116">The sample output verifies that the static constructor runs only one time, even though two instances of `Bus` are created, and that it runs before the instance constructor runs.</span></span>  
  
 [!code-csharp[csProgGuideObjects#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-constructors_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="55639-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55639-117">See Also</span></span>  
 [<span data-ttu-id="55639-118">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="55639-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="55639-119">类和结构</span><span class="sxs-lookup"><span data-stu-id="55639-119">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="55639-120">构造函数</span><span class="sxs-lookup"><span data-stu-id="55639-120">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [<span data-ttu-id="55639-121">静态类和静态类成员</span><span class="sxs-lookup"><span data-stu-id="55639-121">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)  
 [<span data-ttu-id="55639-122">终结器</span><span class="sxs-lookup"><span data-stu-id="55639-122">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
