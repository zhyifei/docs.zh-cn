---
title: "C# 程序的通用结构（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: C# language, program structure
ms.assetid: 5ae964a5-0ef0-40fe-88fb-6d1793371d0d
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ac9b0ad47dc9608c3082167493caa7c4bc966497
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="general-structure-of-a-c-program-c-programming-guide"></a><span data-ttu-id="95518-102">C# 程序的通用结构（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="95518-102">General Structure of a C# Program (C# Programming Guide)</span></span>
<span data-ttu-id="95518-103">C# 程序可由一个或多个文件组成。</span><span class="sxs-lookup"><span data-stu-id="95518-103">C# programs can consist of one or more files.</span></span> <span data-ttu-id="95518-104">每个文件均可包含零个或多个命名空间。</span><span class="sxs-lookup"><span data-stu-id="95518-104">Each file can contain zero or more namespaces.</span></span> <span data-ttu-id="95518-105">一个命名空间除了可包含其他命名空间外,还可包含类、结构、接口、枚举、委托等类型。</span><span class="sxs-lookup"><span data-stu-id="95518-105">A namespace can contain types such as classes, structs, interfaces, enumerations, and delegates, in addition to other namespaces.</span></span> <span data-ttu-id="95518-106">下面是包含所有这些元素的 C# 程序主干。</span><span class="sxs-lookup"><span data-stu-id="95518-106">The following is the skeleton of a C# program that contains all of these elements.</span></span>  
  
 [!code-csharp[csProgGuide#34](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/general-structure-of-a-csharp-program_1.cs)]  
  
## <a name="related-sections"></a><span data-ttu-id="95518-107">相关章节</span><span class="sxs-lookup"><span data-stu-id="95518-107">Related Sections</span></span>  
 <span data-ttu-id="95518-108">更多相关信息：</span><span class="sxs-lookup"><span data-stu-id="95518-108">For more information:</span></span>  
  
-   [<span data-ttu-id="95518-109">类</span><span class="sxs-lookup"><span data-stu-id="95518-109">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)  
  
-   [<span data-ttu-id="95518-110">结构</span><span class="sxs-lookup"><span data-stu-id="95518-110">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
-   [<span data-ttu-id="95518-111">命名空间</span><span class="sxs-lookup"><span data-stu-id="95518-111">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="95518-112">接口</span><span class="sxs-lookup"><span data-stu-id="95518-112">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
  
-   [<span data-ttu-id="95518-113">委托</span><span class="sxs-lookup"><span data-stu-id="95518-113">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="95518-114">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="95518-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="95518-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="95518-115">See Also</span></span>  
 [<span data-ttu-id="95518-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="95518-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="95518-117">在 C# 程序内部</span><span class="sxs-lookup"><span data-stu-id="95518-117">Inside a C# Program</span></span>](../../../csharp/programming-guide/inside-a-program/index.md)  
 [<span data-ttu-id="95518-118">C# 参考</span><span class="sxs-lookup"><span data-stu-id="95518-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="95518-119">\<paveover>C# 示例应用程序</span><span class="sxs-lookup"><span data-stu-id="95518-119">\<paveover>C# Sample Applications</span></span>](http://msdn.microsoft.com/library/9a9d7aaa-51d3-4224-b564-95409b0f3e15)
