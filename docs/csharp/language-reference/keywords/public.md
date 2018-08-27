---
title: public（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: 853f9c9ebe36345a897337d4e793d3c88059e068
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "42998722"
---
# <a name="public-c-reference"></a><span data-ttu-id="e4126-102">public（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="e4126-102">public (C# Reference)</span></span>
<span data-ttu-id="e4126-103">`public` 关键字是类型和类型成员的访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="e4126-103">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="e4126-104">公共访问是允许的最高访问级别。</span><span class="sxs-lookup"><span data-stu-id="e4126-104">Public access is the most permissive access level.</span></span> <span data-ttu-id="e4126-105">对访问公共成员没有限制，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e4126-105">There are no restrictions on accessing public members, as in this example:</span></span>  
  
```csharp  
class SampleClass  
{  
    public int x; // No access restrictions.  
}  
```  
  
 <span data-ttu-id="e4126-106">有关详细信息，请参阅[访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)和[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="e4126-106">See [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4126-107">示例</span><span class="sxs-lookup"><span data-stu-id="e4126-107">Example</span></span>  
 <span data-ttu-id="e4126-108">在下面的示例中，声明了两个类：`PointTest` 和 `MainClass`。</span><span class="sxs-lookup"><span data-stu-id="e4126-108">In the following example, two classes are declared, `PointTest` and `MainClass`.</span></span> <span data-ttu-id="e4126-109">直接从 `MainClass` 访问 `PointTest` 的公共成员 `x` 和 `y`。</span><span class="sxs-lookup"><span data-stu-id="e4126-109">The public members `x` and `y` of `PointTest` are accessed directly from `MainClass`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/public_1.cs)]  
  
 <span data-ttu-id="e4126-110">如果将 `public` 访问级别更改为 [private](../../../csharp/language-reference/keywords/private.md) 或 [protected](../../../csharp/language-reference/keywords/protected.md)，则会收到错误消息：</span><span class="sxs-lookup"><span data-stu-id="e4126-110">If you change the `public` access level to [private](../../../csharp/language-reference/keywords/private.md) or [protected](../../../csharp/language-reference/keywords/protected.md), you will get the error message:</span></span>  
  
 <span data-ttu-id="e4126-111">“PointTest.y”不可访问，因为它受保护级别限制。</span><span class="sxs-lookup"><span data-stu-id="e4126-111">'PointTest.y' is inaccessible due to its protection level.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e4126-112">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="e4126-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e4126-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4126-113">See Also</span></span>

- [<span data-ttu-id="e4126-114">C# 参考</span><span class="sxs-lookup"><span data-stu-id="e4126-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="e4126-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="e4126-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="e4126-116">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="e4126-116">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
- [<span data-ttu-id="e4126-117">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="e4126-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="e4126-118">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="e4126-118">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
- [<span data-ttu-id="e4126-119">可访问性级别</span><span class="sxs-lookup"><span data-stu-id="e4126-119">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
- [<span data-ttu-id="e4126-120">修饰符</span><span class="sxs-lookup"><span data-stu-id="e4126-120">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
- [<span data-ttu-id="e4126-121">private</span><span class="sxs-lookup"><span data-stu-id="e4126-121">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
- [<span data-ttu-id="e4126-122">protected</span><span class="sxs-lookup"><span data-stu-id="e4126-122">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
- [<span data-ttu-id="e4126-123">internal</span><span class="sxs-lookup"><span data-stu-id="e4126-123">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
