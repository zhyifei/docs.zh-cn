---
title: 命名空间 - C# 编程指南
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 6d3b77a506186166c9ad76490ef47f8759c704eb
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452721"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="61540-102">命名空间（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="61540-102">Namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="61540-103">在 C# 编程中，命名空间在两个方面被大量使用。</span><span class="sxs-lookup"><span data-stu-id="61540-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="61540-104">首先，.NET Framework 使用命名空间来组织许多类，如下所示：</span><span class="sxs-lookup"><span data-stu-id="61540-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
 [!code-csharp[csProgGuide#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#22)]  
  
<span data-ttu-id="61540-105">`System` 是一个命名空间，`Console` 是该命名空间中的一个类。</span><span class="sxs-lookup"><span data-stu-id="61540-105">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="61540-106">可以使用 `using` 关键字，如此则不必使用完整的名称，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="61540-106">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuide#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#25)]  
  
<span data-ttu-id="61540-107">有关详细信息，请参阅 [using 指令](../../language-reference/keywords/using-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="61540-107">For more information, see the [using Directive](../../language-reference/keywords/using-directive.md).</span></span>  
  
<span data-ttu-id="61540-108">其次，在较大的编程项目中，声明自己的命名空间可以帮助控制类和方法名称的范围。</span><span class="sxs-lookup"><span data-stu-id="61540-108">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="61540-109">使用 [namespace](../../language-reference/keywords/namespace.md) 关键字可声明命名空间，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="61540-109">Use the [namespace](../../language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#6)]

<span data-ttu-id="61540-110">命名空间的名称必须是有效的 C# [标识符名称](../inside-a-program/identifier-names.md)。</span><span class="sxs-lookup"><span data-stu-id="61540-110">The name of the namespace must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span>

## <a name="namespaces-overview"></a><span data-ttu-id="61540-111">命名空间概述</span><span class="sxs-lookup"><span data-stu-id="61540-111">Namespaces Overview</span></span>  

<span data-ttu-id="61540-112">命名空间具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="61540-112">Namespaces have the following properties:</span></span>  
  
- <span data-ttu-id="61540-113">它们组织大型代码项目。</span><span class="sxs-lookup"><span data-stu-id="61540-113">They organize large code projects.</span></span>  
- <span data-ttu-id="61540-114">通过使用 `.` 运算符分隔它们。</span><span class="sxs-lookup"><span data-stu-id="61540-114">They are delimited by using the `.` operator.</span></span>  
- <span data-ttu-id="61540-115">`using` 指令可免去为每个类指定命名空间的名称。</span><span class="sxs-lookup"><span data-stu-id="61540-115">The `using` directive obviates the requirement to specify the name of the namespace for every class.</span></span>  
- <span data-ttu-id="61540-116">`global` 命名空间是“根”命名空间：`global::System` 始终引用 .NET <xref:System> 命名空间。</span><span class="sxs-lookup"><span data-stu-id="61540-116">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET <xref:System> namespace.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="61540-117">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="61540-117">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="61540-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="61540-118">See also</span></span>

- [<span data-ttu-id="61540-119">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="61540-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="61540-120">使用命名空间</span><span class="sxs-lookup"><span data-stu-id="61540-120">Using Namespaces</span></span>](using-namespaces.md)
- [<span data-ttu-id="61540-121">如何：使用全局命名空间别名</span><span class="sxs-lookup"><span data-stu-id="61540-121">How to: Use the Global Namespace Alias</span></span>](how-to-use-the-global-namespace-alias.md)
- [<span data-ttu-id="61540-122">如何：使用 My 命名空间</span><span class="sxs-lookup"><span data-stu-id="61540-122">How to: Use the My Namespace</span></span>](how-to-use-the-my-namespace.md)
- [<span data-ttu-id="61540-123">标识符名称</span><span class="sxs-lookup"><span data-stu-id="61540-123">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="61540-124">命名空间关键字</span><span class="sxs-lookup"><span data-stu-id="61540-124">Namespace Keywords</span></span>](../../language-reference/keywords/namespace-keywords.md)
- [<span data-ttu-id="61540-125">using 指令</span><span class="sxs-lookup"><span data-stu-id="61540-125">using Directive</span></span>](../../language-reference/keywords/using-directive.md)
- [<span data-ttu-id="61540-126">::运算符</span><span class="sxs-lookup"><span data-stu-id="61540-126">:: Operator</span></span>](../../language-reference/operators/namespace-alias-qualifer.md)
