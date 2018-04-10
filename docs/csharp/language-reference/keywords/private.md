---
title: private（C# 参考）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- private_CSharpKeyword
- private
helpviewer_keywords:
- private keyword [C#]
ms.assetid: 654c0bb8-e6ac-4086-bf96-7474fa6aa1c8
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d9cc8f86166888b47a758e200182d319c68ca6d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="private-c-reference"></a><span data-ttu-id="8945f-102">private（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="8945f-102">private (C# Reference)</span></span>
<span data-ttu-id="8945f-103">`private` 关键字是一个成员访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="8945f-103">The `private` keyword is a member access modifier.</span></span> 
   
 > <span data-ttu-id="8945f-104">本页介绍如何`private`访问。</span><span class="sxs-lookup"><span data-stu-id="8945f-104">This page covers `private` access.</span></span> <span data-ttu-id="8945f-105">`private`关键字也是属于[ `private protected` ](./private-protected.md)访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="8945f-105">The `private` keyword is also part of the [`private protected`](./private-protected.md) access modifier.</span></span>
  
<span data-ttu-id="8945f-106">私有访问是允许的最低访问级别。</span><span class="sxs-lookup"><span data-stu-id="8945f-106">Private access is the least permissive access level.</span></span> <span data-ttu-id="8945f-107">私有成员只有在声明它们的类和结构体中才是可访问的，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="8945f-107">Private members are accessible only within the body of the class or the struct in which they are declared, as in this example:</span></span>  
  
```  
class Employee  
{  
    private int i;  
    double d;   // private access by default  
}  
```  

 <span data-ttu-id="8945f-108">同一体中的嵌套类型也可以访问那些私有成员。</span><span class="sxs-lookup"><span data-stu-id="8945f-108">Nested types in the same body can also access those private members.</span></span>  
  
 <span data-ttu-id="8945f-109">在声明私有成员的类或结构外引用它会导致编译时错误。</span><span class="sxs-lookup"><span data-stu-id="8945f-109">It is a compile-time error to reference a private member outside the class or the struct in which it is declared.</span></span>  
  
 <span data-ttu-id="8945f-110">有关 `private` 和其他访问修饰符的比较，请参阅[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)和[访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="8945f-110">For a comparison of `private` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) and [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8945f-111">示例</span><span class="sxs-lookup"><span data-stu-id="8945f-111">Example</span></span>  
 <span data-ttu-id="8945f-112">在此示例中，`Employee` 类包含两个私有数据成员 `name` 和 `salary`。</span><span class="sxs-lookup"><span data-stu-id="8945f-112">In this example, the `Employee` class contains two private data members, `name` and `salary`.</span></span> <span data-ttu-id="8945f-113">作为私有成员，它们只能通过成员方法来访问。</span><span class="sxs-lookup"><span data-stu-id="8945f-113">As private members, they cannot be accessed except by member methods.</span></span> <span data-ttu-id="8945f-114">添加名为 `GetName` 和 `Salary` 的公共方法，以便可以对私有成员进行受控的访问。</span><span class="sxs-lookup"><span data-stu-id="8945f-114">Public methods named `GetName` and `Salary` are added to allow controlled access to the private members.</span></span> <span data-ttu-id="8945f-115">通过公共方法访问 `name` 成员，而通过公共只读属性访问 `salary` 成员。</span><span class="sxs-lookup"><span data-stu-id="8945f-115">The `name` member is accessed by way of a public method, and the `salary` member is accessed by way of a public read-only property.</span></span> <span data-ttu-id="8945f-116">（有关详细信息，请参阅[属性](../../../csharp/programming-guide/classes-and-structs/properties.md)。）</span><span class="sxs-lookup"><span data-stu-id="8945f-116">(See [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) for more information.)</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/private_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="8945f-117">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="8945f-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8945f-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8945f-118">See Also</span></span>  
 [<span data-ttu-id="8945f-119">C# 参考</span><span class="sxs-lookup"><span data-stu-id="8945f-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8945f-120">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8945f-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8945f-121">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="8945f-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="8945f-122">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="8945f-122">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="8945f-123">可访问性级别</span><span class="sxs-lookup"><span data-stu-id="8945f-123">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="8945f-124">修饰符</span><span class="sxs-lookup"><span data-stu-id="8945f-124">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="8945f-125">公用</span><span class="sxs-lookup"><span data-stu-id="8945f-125">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="8945f-126">受保护</span><span class="sxs-lookup"><span data-stu-id="8945f-126">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="8945f-127">内部</span><span class="sxs-lookup"><span data-stu-id="8945f-127">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
