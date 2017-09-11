---
title: "可访问域（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
caps.latest.revision: 17
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
ms.openlocfilehash: 90faf22d8a7d515ae8bd062f0b95f4be5e051f79
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="accessibility-domain-c-reference"></a><span data-ttu-id="3131f-102">可访问域（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="3131f-102">Accessibility Domain (C# Reference)</span></span>
<span data-ttu-id="3131f-103">成员的可访问域可指定成员可以引用哪些程序分区。</span><span class="sxs-lookup"><span data-stu-id="3131f-103">The accessibility domain of a member specifies in which program sections a member can be referenced.</span></span> <span data-ttu-id="3131f-104">如果成员嵌套于其他类型中，则该成员的可访问域是由该成员的[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)和直接包含类型的可访问域这二者共同确定的。</span><span class="sxs-lookup"><span data-stu-id="3131f-104">If the member is nested within another type, its accessibility domain is determined by both the [accessibility level](../../../csharp/language-reference/keywords/accessibility-levels.md) of the member and the accessibility domain of the immediately containing type.</span></span>  
  
 <span data-ttu-id="3131f-105">顶级类型的可访问域至少是在其中进行声明的项目的程序文本。</span><span class="sxs-lookup"><span data-stu-id="3131f-105">The accessibility domain of a top-level type is at least the program text of the project that it is declared in.</span></span> <span data-ttu-id="3131f-106">也就是说，该域包含此项目的所有源文件。</span><span class="sxs-lookup"><span data-stu-id="3131f-106">That is, the domain includes all of the source files of this project.</span></span> <span data-ttu-id="3131f-107">嵌套类型的可访问域至少是在其中进行声明的类型的程序文本。</span><span class="sxs-lookup"><span data-stu-id="3131f-107">The accessibility domain of a nested type is at least the program text of the type in which it is declared.</span></span> <span data-ttu-id="3131f-108">也就是说，域是类型的主题，其中包括所有嵌套类型。</span><span class="sxs-lookup"><span data-stu-id="3131f-108">That is, the domain is the type body, which includes all nested types.</span></span> <span data-ttu-id="3131f-109">嵌套类型的可访问域决不能超出包含类型的可访问域。</span><span class="sxs-lookup"><span data-stu-id="3131f-109">The accessibility domain of a nested type never exceeds that of the containing type.</span></span> <span data-ttu-id="3131f-110">下例说明了这些概念。</span><span class="sxs-lookup"><span data-stu-id="3131f-110">These concepts are demonstrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3131f-111">示例</span><span class="sxs-lookup"><span data-stu-id="3131f-111">Example</span></span>  
 <span data-ttu-id="3131f-112">此示例包含一个顶级类型 `T1` 和两个嵌套类 `M1` 和 `M2`。</span><span class="sxs-lookup"><span data-stu-id="3131f-112">This example contains a top-level type, `T1`, and two nested classes, `M1` and `M2`.</span></span> <span data-ttu-id="3131f-113">这两个类包含的字段具有不同的已声明可访问性。</span><span class="sxs-lookup"><span data-stu-id="3131f-113">The classes contain fields that have different declared accessibilities.</span></span> <span data-ttu-id="3131f-114">在 `Main` 方法中，每条语句后跟注释以指示每个成员的可访问域。</span><span class="sxs-lookup"><span data-stu-id="3131f-114">In the `Main` method, a comment follows each statement to indicate the accessibility domain of each member.</span></span> <span data-ttu-id="3131f-115">请注意，试图引用不可访问成员的语句将被注释掉。</span><span class="sxs-lookup"><span data-stu-id="3131f-115">Notice that the statements that try to reference the inaccessible members are commented out.</span></span> <span data-ttu-id="3131f-116">如果想要查看通过引用不可访问成员引起的编译器错误，请一次删除一条注释。</span><span class="sxs-lookup"><span data-stu-id="3131f-116">If you want to see the compiler errors caused by referencing an inaccessible member, remove the comments one at a time.</span></span>  
  
 <span data-ttu-id="3131f-117">[!code-cs[csrefKeywordsModifiers#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/accessibility-domain_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3131f-117">[!code-cs[csrefKeywordsModifiers#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/accessibility-domain_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="3131f-118">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="3131f-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3131f-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="3131f-119">See Also</span></span>  
 <span data-ttu-id="3131f-120">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3131f-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3131f-121">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3131f-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3131f-122">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="3131f-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="3131f-123">[访问修饰符](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="3131f-123">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="3131f-124">[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="3131f-124">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="3131f-125">[可访问性级别的使用限制](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="3131f-125">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md) </span></span>  
 <span data-ttu-id="3131f-126">[访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="3131f-126">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 <span data-ttu-id="3131f-127">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="3131f-127">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="3131f-128">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="3131f-128">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="3131f-129">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="3131f-129">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 [<span data-ttu-id="3131f-130">内部</span><span class="sxs-lookup"><span data-stu-id="3131f-130">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)

