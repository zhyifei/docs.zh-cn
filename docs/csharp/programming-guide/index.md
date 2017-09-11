---
title: "C# 编程指南"
ms.date: 2017-05-02
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.langref
dev_langs:
- CSharp
helpviewer_keywords:
- reference tables [C#]
- C# language, programming guide
- Visual C#, programming concepts
- C# language, concepts
ms.assetid: ac0f23a2-6bf3-4077-be99-538ae5fd3bc5
caps.latest.revision: 45
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
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: 0c95459f21aebf1d5efe1482e74ca2724d283821
ms.contentlocale: zh-cn
ms.lasthandoff: 09/02/2017

---
# <a name="c-programming-guide"></a><span data-ttu-id="7361a-102">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="7361a-102">C# programming guide</span></span>
<span data-ttu-id="7361a-103">此部分详细介绍了 C# 语言主要功能，以及通过 .NET Framework 可以在 C# 中使用的功能。</span><span class="sxs-lookup"><span data-stu-id="7361a-103">This section provides detailed information on key C# language features and features accessible to C# through the .NET Framework.</span></span>  
  
 <span data-ttu-id="7361a-104">阅读此部分的大部分内容的前提是，你已对 C# 和一般编程概念有一定的了解。</span><span class="sxs-lookup"><span data-stu-id="7361a-104">Most of this section assumes that you already know something about C# and general programming concepts.</span></span> <span data-ttu-id="7361a-105">如果你完全是编程或 C# 的初学者，请先参阅 [C# 入门](https://www.microsoft.com/net/tutorials/csharp/getting-started)互动教程，此教程不需要具备任何编程知识。</span><span class="sxs-lookup"><span data-stu-id="7361a-105">If you are a complete beginner with programming or with C#, you might want to visit the [Getting Started with C#](https://www.microsoft.com/net/tutorials/csharp/getting-started) interactive tutorial, where no prior programming knowledge is required.</span></span>  
  
 <span data-ttu-id="7361a-106">若要了解特定的关键字、运算符和预处理器指令，请参阅 [C# 参考](../../csharp/language-reference/index.md)。</span><span class="sxs-lookup"><span data-stu-id="7361a-106">For information about specific keywords, operators and preprocessor directives, see [C# Reference](../../csharp/language-reference/index.md).</span></span> <span data-ttu-id="7361a-107">若要了解 C# 语言规范，请参阅 [C# 语言规范](../../csharp/language-reference/language-specification/index.md)。</span><span class="sxs-lookup"><span data-stu-id="7361a-107">For information about the C# Language Specification, see [C# Language Specification](../../csharp/language-reference/language-specification/index.md).</span></span>  
  
## <a name="program-sections"></a><span data-ttu-id="7361a-108">程序部分</span><span class="sxs-lookup"><span data-stu-id="7361a-108">Program sections</span></span>

[<span data-ttu-id="7361a-109">在 C# 程序内部</span><span class="sxs-lookup"><span data-stu-id="7361a-109">Inside a C# Program</span></span>](../../csharp/programming-guide/inside-a-program/index.md)  
  
[<span data-ttu-id="7361a-110">Main() 和命令行参数</span><span class="sxs-lookup"><span data-stu-id="7361a-110">Main() and Command-Line Arguments</span></span>](../../csharp/programming-guide/main-and-command-args/index.md)  
 
## <a name="language-sections"></a><span data-ttu-id="7361a-111">语言部分</span><span class="sxs-lookup"><span data-stu-id="7361a-111">Language Sections</span></span>  
[<span data-ttu-id="7361a-112">语句、表达式和运算符</span><span class="sxs-lookup"><span data-stu-id="7361a-112">Statements, Expressions, and Operators</span></span>](../../csharp/programming-guide/statements-expressions-operators/index.md)  

 [<span data-ttu-id="7361a-113">类型</span><span class="sxs-lookup"><span data-stu-id="7361a-113">Types</span></span>](../../csharp/programming-guide/types/index.md)  

 [<span data-ttu-id="7361a-114">类和结构</span><span class="sxs-lookup"><span data-stu-id="7361a-114">Classes and Structs</span></span>](../../csharp/programming-guide/classes-and-structs/index.md)  
  
 [<span data-ttu-id="7361a-115">接口</span><span class="sxs-lookup"><span data-stu-id="7361a-115">Interfaces</span></span>](../../csharp/programming-guide/interfaces/index.md)  

 [<span data-ttu-id="7361a-116">枚举类型</span><span class="sxs-lookup"><span data-stu-id="7361a-116">Enumeration Types</span></span>](../../csharp/programming-guide/enumeration-types.md)  
  
 [<span data-ttu-id="7361a-117">委托</span><span class="sxs-lookup"><span data-stu-id="7361a-117">Delegates</span></span>](../../csharp/programming-guide/delegates/index.md)  
 
 [<span data-ttu-id="7361a-118">阵列</span><span class="sxs-lookup"><span data-stu-id="7361a-118">Arrays</span></span>](../../csharp/programming-guide/arrays/index.md)  
  
 [<span data-ttu-id="7361a-119">字符串</span><span class="sxs-lookup"><span data-stu-id="7361a-119">Strings</span></span>](../../csharp/programming-guide/strings/index.md)  
  
 [<span data-ttu-id="7361a-120">属性</span><span class="sxs-lookup"><span data-stu-id="7361a-120">Properties</span></span>](../../csharp/programming-guide/classes-and-structs/properties.md)  
  
 [<span data-ttu-id="7361a-121">索引器</span><span class="sxs-lookup"><span data-stu-id="7361a-121">Indexers</span></span>](../../csharp/programming-guide/indexers/index.md)  
  
 [<span data-ttu-id="7361a-122">事件</span><span class="sxs-lookup"><span data-stu-id="7361a-122">Events</span></span>](../../csharp/programming-guide/events/index.md)  
  
 [<span data-ttu-id="7361a-123">泛型</span><span class="sxs-lookup"><span data-stu-id="7361a-123">Generics</span></span>](../../csharp/programming-guide/generics/index.md)  
  
 [<span data-ttu-id="7361a-124">迭代器</span><span class="sxs-lookup"><span data-stu-id="7361a-124">Iterators</span></span>](../../csharp/programming-guide/concepts/iterators.md)
  
 [<span data-ttu-id="7361a-125">LINQ 查询表达式</span><span class="sxs-lookup"><span data-stu-id="7361a-125">LINQ Query Expressions</span></span>](../../csharp/programming-guide/linq-query-expressions/index.md)  
  
 [<span data-ttu-id="7361a-126">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="7361a-126">Lambda Expressions</span></span>](../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
  
 [<span data-ttu-id="7361a-127">命名空间</span><span class="sxs-lookup"><span data-stu-id="7361a-127">Namespaces</span></span>](../../csharp/programming-guide/namespaces/index.md)  
  
 [<span data-ttu-id="7361a-128">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="7361a-128">Nullable Types</span></span>](../../csharp/programming-guide/nullable-types/index.md)  
  
 [<span data-ttu-id="7361a-129">不安全代码和指针</span><span class="sxs-lookup"><span data-stu-id="7361a-129">Unsafe Code and Pointers</span></span>](../../csharp/programming-guide/unsafe-code-pointers/index.md)  
  
 [<span data-ttu-id="7361a-130">XML 文档注释</span><span class="sxs-lookup"><span data-stu-id="7361a-130">XML Documentation Comments</span></span>](../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)  
  
## <a name="platform-sections"></a><span data-ttu-id="7361a-131">平台部分</span><span class="sxs-lookup"><span data-stu-id="7361a-131">Platform Sections</span></span>  
 [<span data-ttu-id="7361a-132">应用程序域（C# 和 Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="7361a-132">Application Domains (C# and Visual Basic)</span></span>](http://msdn.microsoft.com/en-us/1bc2939a-79db-4a4a-a677-4a2ce6de2b1e)  
  
 [<span data-ttu-id="7361a-133">程序集和全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="7361a-133">Assemblies and the Global Assembly Cache</span></span>](../../csharp/programming-guide/concepts/assemblies-gac/index.md)  
  
 [<span data-ttu-id="7361a-134">特性</span><span class="sxs-lookup"><span data-stu-id="7361a-134">Attributes</span></span>](../../csharp/programming-guide/concepts/attributes/index.md)  
  
 [<span data-ttu-id="7361a-135">集合</span><span class="sxs-lookup"><span data-stu-id="7361a-135">Collections</span></span>](../../csharp/programming-guide/concepts/collections.md)  
  
 [<span data-ttu-id="7361a-136">异常和异常处理</span><span class="sxs-lookup"><span data-stu-id="7361a-136">Exceptions and Exception Handling</span></span>](../../csharp/programming-guide/exceptions/index.md)  
  
 [<span data-ttu-id="7361a-137">文件系统和注册表（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="7361a-137">File System and the Registry (C# Programming Guide)</span></span>](../../csharp/programming-guide/file-system/index.md)  
  
 [<span data-ttu-id="7361a-138">互操作性</span><span class="sxs-lookup"><span data-stu-id="7361a-138">Interoperability</span></span>](../../csharp/programming-guide/interop/index.md)  
  
 [<span data-ttu-id="7361a-139">反射</span><span class="sxs-lookup"><span data-stu-id="7361a-139">Reflection</span></span>](../../csharp/programming-guide/concepts/reflection.md)  
  
## <a name="see-also"></a><span data-ttu-id="7361a-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7361a-140">See Also</span></span>  
 <span data-ttu-id="7361a-141">[C# 参考](../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="7361a-141">[C# Reference](../../csharp/language-reference/index.md) </span></span>  
 [<span data-ttu-id="7361a-142">C#</span><span class="sxs-lookup"><span data-stu-id="7361a-142">C#</span></span>](../../csharp/index.md)

