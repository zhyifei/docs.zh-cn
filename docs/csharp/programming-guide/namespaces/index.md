---
title: "命名空间（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
caps.latest.revision: 27
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
ms.openlocfilehash: a45339a4c3320a92c0339b1cad6345a2555ed920
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="ad8b5-102">命名空间（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="ad8b5-102">Namespaces (C# Programming Guide)</span></span>
<span data-ttu-id="ad8b5-103">在 C# 编程中，命名空间在两个方面被大量使用。</span><span class="sxs-lookup"><span data-stu-id="ad8b5-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="ad8b5-104">首先，.NET Framework 使用命名空间来组织它的许多类，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ad8b5-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
 <span data-ttu-id="ad8b5-105">[!code-cs[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ad8b5-105">[!code-cs[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]</span></span>  
  
 <span data-ttu-id="ad8b5-106">`System` 是一个命名空间，`Console` 是该命名空间中的一个类。</span><span class="sxs-lookup"><span data-stu-id="ad8b5-106">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="ad8b5-107">可以使用 `using` 关键字，如此则不必使用完整的名称，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="ad8b5-107">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
 <span data-ttu-id="ad8b5-108">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="ad8b5-108">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]</span></span>  
  
 <span data-ttu-id="ad8b5-109">[!code-cs[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="ad8b5-109">[!code-cs[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]</span></span>  
  
 <span data-ttu-id="ad8b5-110">有关详细信息，请参阅 [using 指令](../../../csharp/language-reference/keywords/using-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="ad8b5-110">For more information, see [using Directive](../../../csharp/language-reference/keywords/using-directive.md).</span></span>  
  
 <span data-ttu-id="ad8b5-111">其次，在较大的编程项目中，声明自己的命名空间可以帮助控制类和方法名称的范围。</span><span class="sxs-lookup"><span data-stu-id="ad8b5-111">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="ad8b5-112">使用 [namespace](../../../csharp/language-reference/keywords/namespace.md) 关键字可声明命名空间，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="ad8b5-112">Use the [namespace](../../../csharp/language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
 <span data-ttu-id="ad8b5-113">[!code-cs[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="ad8b5-113">[!code-cs[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]</span></span>  
  
## <a name="namespaces-overview"></a><span data-ttu-id="ad8b5-114">命名空间概述</span><span class="sxs-lookup"><span data-stu-id="ad8b5-114">Namespaces Overview</span></span>  
 <span data-ttu-id="ad8b5-115">命名空间具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="ad8b5-115">Namespaces have the following properties:</span></span>  
  
-   <span data-ttu-id="ad8b5-116">它们组织大型代码项目。</span><span class="sxs-lookup"><span data-stu-id="ad8b5-116">They organize large code projects.</span></span>  
  
-   <span data-ttu-id="ad8b5-117">通过使用 `.` 运算符分隔它们。</span><span class="sxs-lookup"><span data-stu-id="ad8b5-117">They are delimited by using the `.` operator.</span></span>  
  
-   <span data-ttu-id="ad8b5-118">使用 `using directive` 可免去为每个类指定名称空间的名称。</span><span class="sxs-lookup"><span data-stu-id="ad8b5-118">The `using directive` obviates the requirement to specify the name of the namespace for every class.</span></span>  
  
-   <span data-ttu-id="ad8b5-119">`global` 命名空间是“根”命名空间：`global::System` 始终引用 .NET Framework 命名空间 `System`。</span><span class="sxs-lookup"><span data-stu-id="ad8b5-119">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET Framework namespace `System`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ad8b5-120">相关章节</span><span class="sxs-lookup"><span data-stu-id="ad8b5-120">Related Sections</span></span>  
 <span data-ttu-id="ad8b5-121">有关命名空间的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="ad8b5-121">See the following topics for more information about namespaces:</span></span>  
  
-   [<span data-ttu-id="ad8b5-122">使用命名空间</span><span class="sxs-lookup"><span data-stu-id="ad8b5-122">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="ad8b5-123">如何：使用全局命名空间别名</span><span class="sxs-lookup"><span data-stu-id="ad8b5-123">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
-   [<span data-ttu-id="ad8b5-124">如何：使用 My 命名空间</span><span class="sxs-lookup"><span data-stu-id="ad8b5-124">How to: Use the My Namespace</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-my-namespace.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="ad8b5-125">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="ad8b5-125">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ad8b5-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad8b5-126">See Also</span></span>  
 <span data-ttu-id="ad8b5-127">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ad8b5-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ad8b5-128">[命名空间关键字](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="ad8b5-128">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
 <span data-ttu-id="ad8b5-129">[using 指令](../../../csharp/language-reference/keywords/using-directive.md) </span><span class="sxs-lookup"><span data-stu-id="ad8b5-129">[using Directive](../../../csharp/language-reference/keywords/using-directive.md) </span></span>  
 <span data-ttu-id="ad8b5-130">[:: Operator](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span><span class="sxs-lookup"><span data-stu-id="ad8b5-130">[:: Operator](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span></span>  
 [<span data-ttu-id="ad8b5-131">。运算符</span><span class="sxs-lookup"><span data-stu-id="ad8b5-131">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)

