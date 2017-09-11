---
title: "结构（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ce12f402c0748ea6729c82e3f188c0a58f63d628
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="1542f-102">结构（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="1542f-102">Structs (C# Programming Guide)</span></span>
<span data-ttu-id="1542f-103">通过使用[结构](../../../csharp/language-reference/keywords/struct.md)关键字来定义结构，例如：</span><span class="sxs-lookup"><span data-stu-id="1542f-103">Structs are defined by using the [struct](../../../csharp/language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 <span data-ttu-id="1542f-104">[!code-cs[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1542f-104">[!code-cs[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]</span></span>  
  
 <span data-ttu-id="1542f-105">结构与类具有许多相同的语法，但结构比类受到的限制更多：</span><span class="sxs-lookup"><span data-stu-id="1542f-105">Structs share most of the same syntax as classes, although structs are more limited than classes:</span></span>  
  
-   <span data-ttu-id="1542f-106">在结构声明中，除非将字段声明为 const 或 static，否则无法初始化。</span><span class="sxs-lookup"><span data-stu-id="1542f-106">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
  
-   <span data-ttu-id="1542f-107">结构不能声明默认构造函数（没有参数的构造函数）或终结器。</span><span class="sxs-lookup"><span data-stu-id="1542f-107">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
  
-   <span data-ttu-id="1542f-108">结构在分配时进行复制。</span><span class="sxs-lookup"><span data-stu-id="1542f-108">Structs are copied on assignment.</span></span> <span data-ttu-id="1542f-109">将结构分配给新变量时，将复制所有数据，并且对新副本所做的任何修改不会更改原始副本的数据。</span><span class="sxs-lookup"><span data-stu-id="1542f-109">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="1542f-110">使用值类型的集合（如 Dictionary\<string, myStruct>）时，请务必记住这一点。</span><span class="sxs-lookup"><span data-stu-id="1542f-110">This is important to remember when working with collections of value types such as Dictionary\<string, myStruct>.</span></span>  
  
-   <span data-ttu-id="1542f-111">结构是值类型，而类是引用类型。</span><span class="sxs-lookup"><span data-stu-id="1542f-111">Structs are value types and classes are reference types.</span></span>  
  
-   <span data-ttu-id="1542f-112">与类不同，无需使用 `new` 运算符即可对结构进行实例化。</span><span class="sxs-lookup"><span data-stu-id="1542f-112">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
  
-   <span data-ttu-id="1542f-113">结构可以声明具有参数的构造函数。</span><span class="sxs-lookup"><span data-stu-id="1542f-113">Structs can declare constructors that have parameters.</span></span>  
  
-   <span data-ttu-id="1542f-114">一个结构无法继承自另一个结构或类，并且它不能为类的基类。</span><span class="sxs-lookup"><span data-stu-id="1542f-114">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="1542f-115">所有结构都直接继承自 `System.ValueType`，后者继承自 `System.Object`。</span><span class="sxs-lookup"><span data-stu-id="1542f-115">All structs inherit directly from `System.ValueType`, which inherits from `System.Object`.</span></span>  
  
-   <span data-ttu-id="1542f-116">结构可以实现接口。</span><span class="sxs-lookup"><span data-stu-id="1542f-116">A struct can implement interfaces.</span></span>  
  
-   <span data-ttu-id="1542f-117">结构可用作可以为 null 的类型，并且可以向其分配一个 null 值。</span><span class="sxs-lookup"><span data-stu-id="1542f-117">A struct can be used as a nullable type and can be assigned a null value.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1542f-118">相关章节</span><span class="sxs-lookup"><span data-stu-id="1542f-118">Related Sections</span></span>  
 <span data-ttu-id="1542f-119">更多相关信息：</span><span class="sxs-lookup"><span data-stu-id="1542f-119">For more information:</span></span>  
  
-   [<span data-ttu-id="1542f-120">使用结构</span><span class="sxs-lookup"><span data-stu-id="1542f-120">Using Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [<span data-ttu-id="1542f-121">构造函数</span><span class="sxs-lookup"><span data-stu-id="1542f-121">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [<span data-ttu-id="1542f-122">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="1542f-122">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [<span data-ttu-id="1542f-123">如何：了解向方法传递结构和向方法传递类引用之间的区别</span><span class="sxs-lookup"><span data-stu-id="1542f-123">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [<span data-ttu-id="1542f-124">如何：在结构之间实现用户定义的转换</span><span class="sxs-lookup"><span data-stu-id="1542f-124">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
## <a name="see-also"></a><span data-ttu-id="1542f-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1542f-125">See Also</span></span>  
 <span data-ttu-id="1542f-126">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1542f-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1542f-127">[类和结构](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="1542f-127">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 [<span data-ttu-id="1542f-128">类</span><span class="sxs-lookup"><span data-stu-id="1542f-128">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)

