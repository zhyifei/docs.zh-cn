---
title: 命名空间（C# 编程指南）
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: c4011092a6c605137053b544d4b9f14cce2fdb4c
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46002809"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="a176d-102">命名空间（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="a176d-102">Namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="a176d-103">在 C# 编程中，命名空间在两个方面被大量使用。</span><span class="sxs-lookup"><span data-stu-id="a176d-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="a176d-104">首先，.NET Framework 使用命名空间来组织许多类，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a176d-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
[!code-csharp[csProgGuide#22](../inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
<span data-ttu-id="a176d-105">`System` 是一个命名空间，`Console` 是该命名空间中的一个类。</span><span class="sxs-lookup"><span data-stu-id="a176d-105">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="a176d-106">可以使用 `using` 关键字，如此则不必使用完整的名称，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="a176d-106">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
[!code-csharp[csProgGuide#1](../inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
[!code-csharp[csProgGuide#25](../inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
<span data-ttu-id="a176d-107">有关详细信息，请参阅 [using 指令](../../language-reference/keywords/using-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="a176d-107">For more information, see the [using Directive](../../language-reference/keywords/using-directive.md).</span></span>  
  
<span data-ttu-id="a176d-108">其次，在较大的编程项目中，声明自己的命名空间可以帮助控制类和方法名称的范围。</span><span class="sxs-lookup"><span data-stu-id="a176d-108">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="a176d-109">使用 [namespace](../../language-reference/keywords/namespace.md) 关键字可声明命名空间，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="a176d-109">Use the [namespace](../../language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
[!code-csharp[csProgGuideNamespaces#6](codesnippet/CSharp/index_4.cs)]

<span data-ttu-id="a176d-110">命名空间的名称必须是有效的 C# [标识符名称](../inside-a-program/identifier-names.md)。</span><span class="sxs-lookup"><span data-stu-id="a176d-110">The name of the namespace must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span>

## <a name="namespaces-overview"></a><span data-ttu-id="a176d-111">命名空间概述</span><span class="sxs-lookup"><span data-stu-id="a176d-111">Namespaces Overview</span></span>  

<span data-ttu-id="a176d-112">命名空间具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="a176d-112">Namespaces have the following properties:</span></span>  
  
- <span data-ttu-id="a176d-113">它们组织大型代码项目。</span><span class="sxs-lookup"><span data-stu-id="a176d-113">They organize large code projects.</span></span>  
- <span data-ttu-id="a176d-114">通过使用 `.` 运算符分隔它们。</span><span class="sxs-lookup"><span data-stu-id="a176d-114">They are delimited by using the `.` operator.</span></span>  
- <span data-ttu-id="a176d-115">使用 `using directive` 可免去为每个类指定名称空间的名称。</span><span class="sxs-lookup"><span data-stu-id="a176d-115">The `using directive` obviates the requirement to specify the name of the namespace for every class.</span></span>  
- <span data-ttu-id="a176d-116">`global` 命名空间是“根”命名空间：`global::System` 始终引用 .NET Framework 命名空间 `System`。</span><span class="sxs-lookup"><span data-stu-id="a176d-116">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET Framework namespace `System`.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="a176d-117">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="a176d-117">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a176d-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a176d-118">See Also</span></span>

- [<span data-ttu-id="a176d-119">使用命名空间</span><span class="sxs-lookup"><span data-stu-id="a176d-119">Using Namespaces</span></span>](using-namespaces.md)
- [<span data-ttu-id="a176d-120">如何：使用全局命名空间别名</span><span class="sxs-lookup"><span data-stu-id="a176d-120">How to: Use the Global Namespace Alias</span></span>](how-to-use-the-global-namespace-alias.md)
- [<span data-ttu-id="a176d-121">如何：使用 My 命名空间</span><span class="sxs-lookup"><span data-stu-id="a176d-121">How to: Use the My Namespace</span></span>](how-to-use-the-my-namespace.md)
- [<span data-ttu-id="a176d-122">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a176d-122">C# Programming Guide</span></span>](../index.md)  
- [<span data-ttu-id="a176d-123">标识符名称</span><span class="sxs-lookup"><span data-stu-id="a176d-123">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="a176d-124">命名空间关键字</span><span class="sxs-lookup"><span data-stu-id="a176d-124">Namespace Keywords</span></span>](../../language-reference/keywords/namespace-keywords.md)  
- [<span data-ttu-id="a176d-125">using 指令</span><span class="sxs-lookup"><span data-stu-id="a176d-125">using Directive</span></span>](../../language-reference/keywords/using-directive.md)  
- [<span data-ttu-id="a176d-126">:: 运算符</span><span class="sxs-lookup"><span data-stu-id="a176d-126">:: Operator</span></span>](../../language-reference/operators/namespace-alias-qualifer.md)  
- [<span data-ttu-id="a176d-127">。运算符</span><span class="sxs-lookup"><span data-stu-id="a176d-127">. Operator</span></span>](../../language-reference/operators/member-access-operator.md)
>>>>>>> <span data-ttu-id="a176d-128">添加标识符命名规则</span><span class="sxs-lookup"><span data-stu-id="a176d-128">add identifier naming rules</span></span>
