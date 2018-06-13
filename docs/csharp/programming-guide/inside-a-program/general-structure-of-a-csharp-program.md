---
title: C# 程序的通用结构（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, program structure
ms.assetid: 5ae964a5-0ef0-40fe-88fb-6d1793371d0d
ms.openlocfilehash: 33d7c01b86234bb64fd2daa0863f9eb24aa85c70
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33331209"
---
# <a name="general-structure-of-a-c-program-c-programming-guide"></a><span data-ttu-id="f4259-102">C# 程序的通用结构（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="f4259-102">General Structure of a C# Program (C# Programming Guide)</span></span>
<span data-ttu-id="f4259-103">C# 程序可由一个或多个文件组成。</span><span class="sxs-lookup"><span data-stu-id="f4259-103">C# programs can consist of one or more files.</span></span> <span data-ttu-id="f4259-104">每个文件均可包含零个或多个命名空间。</span><span class="sxs-lookup"><span data-stu-id="f4259-104">Each file can contain zero or more namespaces.</span></span> <span data-ttu-id="f4259-105">一个命名空间除了可包含其他命名空间外,还可包含类、结构、接口、枚举、委托等类型。</span><span class="sxs-lookup"><span data-stu-id="f4259-105">A namespace can contain types such as classes, structs, interfaces, enumerations, and delegates, in addition to other namespaces.</span></span> <span data-ttu-id="f4259-106">下面是包含所有这些元素的 C# 程序主干。</span><span class="sxs-lookup"><span data-stu-id="f4259-106">The following is the skeleton of a C# program that contains all of these elements.</span></span>  
  
 [!code-csharp[csProgGuide#34](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/general-structure-of-a-csharp-program_1.cs)]  
  
## <a name="related-sections"></a><span data-ttu-id="f4259-107">相关章节</span><span class="sxs-lookup"><span data-stu-id="f4259-107">Related Sections</span></span>  
 <span data-ttu-id="f4259-108">更多相关信息：</span><span class="sxs-lookup"><span data-stu-id="f4259-108">For more information:</span></span>  
  
-   [<span data-ttu-id="f4259-109">类</span><span class="sxs-lookup"><span data-stu-id="f4259-109">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)  
  
-   [<span data-ttu-id="f4259-110">结构</span><span class="sxs-lookup"><span data-stu-id="f4259-110">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
-   [<span data-ttu-id="f4259-111">命名空间</span><span class="sxs-lookup"><span data-stu-id="f4259-111">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="f4259-112">接口</span><span class="sxs-lookup"><span data-stu-id="f4259-112">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
  
-   [<span data-ttu-id="f4259-113">委托</span><span class="sxs-lookup"><span data-stu-id="f4259-113">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="f4259-114">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="f4259-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f4259-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4259-115">See Also</span></span>  
 [<span data-ttu-id="f4259-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="f4259-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f4259-117">在 C# 程序内部</span><span class="sxs-lookup"><span data-stu-id="f4259-117">Inside a C# Program</span></span>](../../../csharp/programming-guide/inside-a-program/index.md)  
 [<span data-ttu-id="f4259-118">C# 参考</span><span class="sxs-lookup"><span data-stu-id="f4259-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f4259-119">\<paveover>C# 示例应用程序</span><span class="sxs-lookup"><span data-stu-id="f4259-119">\<paveover>C# Sample Applications</span></span>](http://msdn.microsoft.com/library/9a9d7aaa-51d3-4224-b564-95409b0f3e15)
