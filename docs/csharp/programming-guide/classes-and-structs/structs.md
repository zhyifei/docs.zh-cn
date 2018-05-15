---
title: 结构（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: ffb5b8da6c72056620cf890f38af4e7a8116ab3e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="1e210-102">结构（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="1e210-102">Structs (C# Programming Guide)</span></span>
<span data-ttu-id="1e210-103">通过使用[结构](../../../csharp/language-reference/keywords/struct.md)关键字来定义结构，例如：</span><span class="sxs-lookup"><span data-stu-id="1e210-103">Structs are defined by using the [struct](../../../csharp/language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]  
  
 <span data-ttu-id="1e210-104">结构与类具有许多相同的语法，但结构比类受到的限制更多：</span><span class="sxs-lookup"><span data-stu-id="1e210-104">Structs share most of the same syntax as classes, although structs are more limited than classes:</span></span>  
  
-   <span data-ttu-id="1e210-105">在结构声明中，除非将字段声明为 const 或 static，否则无法初始化。</span><span class="sxs-lookup"><span data-stu-id="1e210-105">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
  
-   <span data-ttu-id="1e210-106">结构不能声明默认构造函数（没有参数的构造函数）或终结器。</span><span class="sxs-lookup"><span data-stu-id="1e210-106">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
  
-   <span data-ttu-id="1e210-107">结构在分配时进行复制。</span><span class="sxs-lookup"><span data-stu-id="1e210-107">Structs are copied on assignment.</span></span> <span data-ttu-id="1e210-108">将结构分配给新变量时，将复制所有数据，并且对新副本所做的任何修改不会更改原始副本的数据。</span><span class="sxs-lookup"><span data-stu-id="1e210-108">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="1e210-109">使用值类型的集合（如 Dictionary\<string, myStruct>）时，请务必记住这一点。</span><span class="sxs-lookup"><span data-stu-id="1e210-109">This is important to remember when working with collections of value types such as Dictionary\<string, myStruct>.</span></span>  
  
-   <span data-ttu-id="1e210-110">结构是值类型，而类是引用类型。</span><span class="sxs-lookup"><span data-stu-id="1e210-110">Structs are value types and classes are reference types.</span></span>  
  
-   <span data-ttu-id="1e210-111">与类不同，无需使用 `new` 运算符即可对结构进行实例化。</span><span class="sxs-lookup"><span data-stu-id="1e210-111">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
  
-   <span data-ttu-id="1e210-112">结构可以声明具有参数的构造函数。</span><span class="sxs-lookup"><span data-stu-id="1e210-112">Structs can declare constructors that have parameters.</span></span>  
  
-   <span data-ttu-id="1e210-113">一个结构无法继承自另一个结构或类，并且它不能为类的基类。</span><span class="sxs-lookup"><span data-stu-id="1e210-113">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="1e210-114">所有结构都直接继承自 `System.ValueType`，后者继承自 `System.Object`。</span><span class="sxs-lookup"><span data-stu-id="1e210-114">All structs inherit directly from `System.ValueType`, which inherits from `System.Object`.</span></span>  
  
-   <span data-ttu-id="1e210-115">结构可以实现接口。</span><span class="sxs-lookup"><span data-stu-id="1e210-115">A struct can implement interfaces.</span></span>  
  
-   <span data-ttu-id="1e210-116">结构可用作可以为 null 的类型，并且可以向其分配一个 null 值。</span><span class="sxs-lookup"><span data-stu-id="1e210-116">A struct can be used as a nullable type and can be assigned a null value.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1e210-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="1e210-117">Related Sections</span></span>  
 <span data-ttu-id="1e210-118">更多相关信息：</span><span class="sxs-lookup"><span data-stu-id="1e210-118">For more information:</span></span>  
  
-   [<span data-ttu-id="1e210-119">使用结构</span><span class="sxs-lookup"><span data-stu-id="1e210-119">Using Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [<span data-ttu-id="1e210-120">构造函数</span><span class="sxs-lookup"><span data-stu-id="1e210-120">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [<span data-ttu-id="1e210-121">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="1e210-121">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [<span data-ttu-id="1e210-122">如何：了解向方法传递结构和向方法传递类引用之间的区别</span><span class="sxs-lookup"><span data-stu-id="1e210-122">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [<span data-ttu-id="1e210-123">如何：在结构之间实现用户定义的转换</span><span class="sxs-lookup"><span data-stu-id="1e210-123">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
## <a name="see-also"></a><span data-ttu-id="1e210-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e210-124">See Also</span></span>  
 [<span data-ttu-id="1e210-125">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="1e210-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1e210-126">类和结构</span><span class="sxs-lookup"><span data-stu-id="1e210-126">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="1e210-127">类</span><span class="sxs-lookup"><span data-stu-id="1e210-127">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)
