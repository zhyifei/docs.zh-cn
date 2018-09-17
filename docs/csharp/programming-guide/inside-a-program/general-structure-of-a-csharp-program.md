---
title: C# 程序的通用结构（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, program structure
ms.assetid: 5ae964a5-0ef0-40fe-88fb-6d1793371d0d
ms.openlocfilehash: d3920fff26eccdd509c72143ff8553fb0c501bbc
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45597636"
---
# <a name="general-structure-of-a-c-program-c-programming-guide"></a><span data-ttu-id="1d540-102">C# 程序的通用结构（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="1d540-102">General Structure of a C# Program (C# Programming Guide)</span></span>
<span data-ttu-id="1d540-103">C# 程序可由一个或多个文件组成。</span><span class="sxs-lookup"><span data-stu-id="1d540-103">C# programs can consist of one or more files.</span></span> <span data-ttu-id="1d540-104">每个文件均可包含零个或多个命名空间。</span><span class="sxs-lookup"><span data-stu-id="1d540-104">Each file can contain zero or more namespaces.</span></span> <span data-ttu-id="1d540-105">一个命名空间除了可包含其他命名空间外,还可包含类、结构、接口、枚举、委托等类型。</span><span class="sxs-lookup"><span data-stu-id="1d540-105">A namespace can contain types such as classes, structs, interfaces, enumerations, and delegates, in addition to other namespaces.</span></span> <span data-ttu-id="1d540-106">下面是包含所有这些元素的 C# 程序主干。</span><span class="sxs-lookup"><span data-stu-id="1d540-106">The following is the skeleton of a C# program that contains all of these elements.</span></span>  
  
 [!code-csharp[csProgGuide#34](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/general-structure-of-a-csharp-program_1.cs)]  
  
## <a name="related-sections"></a><span data-ttu-id="1d540-107">相关章节</span><span class="sxs-lookup"><span data-stu-id="1d540-107">Related Sections</span></span>  
 <span data-ttu-id="1d540-108">更多相关信息：</span><span class="sxs-lookup"><span data-stu-id="1d540-108">For more information:</span></span>  
  
-   [<span data-ttu-id="1d540-109">类</span><span class="sxs-lookup"><span data-stu-id="1d540-109">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)  
  
-   [<span data-ttu-id="1d540-110">结构</span><span class="sxs-lookup"><span data-stu-id="1d540-110">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
-   [<span data-ttu-id="1d540-111">命名空间</span><span class="sxs-lookup"><span data-stu-id="1d540-111">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="1d540-112">接口</span><span class="sxs-lookup"><span data-stu-id="1d540-112">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
  
-   [<span data-ttu-id="1d540-113">委托</span><span class="sxs-lookup"><span data-stu-id="1d540-113">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="1d540-114">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="1d540-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1d540-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="1d540-115">See Also</span></span>

- [<span data-ttu-id="1d540-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="1d540-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="1d540-117">在 C# 程序内部</span><span class="sxs-lookup"><span data-stu-id="1d540-117">Inside a C# Program</span></span>](../../../csharp/programming-guide/inside-a-program/index.md)  
- [<span data-ttu-id="1d540-118">C# 参考</span><span class="sxs-lookup"><span data-stu-id="1d540-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="1d540-119">\<paveover>C# 示例应用程序</span><span class="sxs-lookup"><span data-stu-id="1d540-119">\<paveover>C# Sample Applications</span></span>](https://msdn.microsoft.com/library/9a9d7aaa-51d3-4224-b564-95409b0f3e15)
