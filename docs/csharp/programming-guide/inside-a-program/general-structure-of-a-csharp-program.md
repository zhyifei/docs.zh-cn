---
title: C# 程序的通用结构 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, program structure
ms.assetid: 5ae964a5-0ef0-40fe-88fb-6d1793371d0d
ms.openlocfilehash: a9e20d0020b82973fb95e422c30f87421adedd5c
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236890"
---
# <a name="general-structure-of-a-c-program-c-programming-guide"></a><span data-ttu-id="b7edf-102">C# 程序的通用结构（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="b7edf-102">General Structure of a C# Program (C# Programming Guide)</span></span>
<span data-ttu-id="b7edf-103">C# 程序可由一个或多个文件组成。</span><span class="sxs-lookup"><span data-stu-id="b7edf-103">C# programs can consist of one or more files.</span></span> <span data-ttu-id="b7edf-104">每个文件均可包含零个或多个命名空间。</span><span class="sxs-lookup"><span data-stu-id="b7edf-104">Each file can contain zero or more namespaces.</span></span> <span data-ttu-id="b7edf-105">一个命名空间除了可包含其他命名空间外,还可包含类、结构、接口、枚举、委托等类型。</span><span class="sxs-lookup"><span data-stu-id="b7edf-105">A namespace can contain types such as classes, structs, interfaces, enumerations, and delegates, in addition to other namespaces.</span></span> <span data-ttu-id="b7edf-106">下面是包含所有这些元素的 C# 程序主干。</span><span class="sxs-lookup"><span data-stu-id="b7edf-106">The following is the skeleton of a C# program that contains all of these elements.</span></span>  
  
 [!code-csharp[csProgGuide#34](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/general-structure-of-a-csharp-program_1.cs)]  
  
## <a name="related-sections"></a><span data-ttu-id="b7edf-107">相关章节</span><span class="sxs-lookup"><span data-stu-id="b7edf-107">Related Sections</span></span>  
 <span data-ttu-id="b7edf-108">更多相关信息：</span><span class="sxs-lookup"><span data-stu-id="b7edf-108">For more information:</span></span>  
  
-   [<span data-ttu-id="b7edf-109">类</span><span class="sxs-lookup"><span data-stu-id="b7edf-109">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)  
  
-   [<span data-ttu-id="b7edf-110">结构</span><span class="sxs-lookup"><span data-stu-id="b7edf-110">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
-   [<span data-ttu-id="b7edf-111">命名空间</span><span class="sxs-lookup"><span data-stu-id="b7edf-111">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="b7edf-112">接口</span><span class="sxs-lookup"><span data-stu-id="b7edf-112">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
  
-   [<span data-ttu-id="b7edf-113">委托</span><span class="sxs-lookup"><span data-stu-id="b7edf-113">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="b7edf-114">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="b7edf-114">C# Language Specification</span></span>  

<span data-ttu-id="b7edf-115">有关详细信息，请参阅 [C# 语言规范](../../language-reference/language-specification/index.md)中的[基本概念](~/_csharplang/spec/basic-concepts.md)。</span><span class="sxs-lookup"><span data-stu-id="b7edf-115">For more information, see [Basic concepts](~/_csharplang/spec/basic-concepts.md) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="b7edf-116">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="b7edf-116">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b7edf-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7edf-117">See Also</span></span>

- [<span data-ttu-id="b7edf-118">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="b7edf-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="b7edf-119">在 C# 程序内部</span><span class="sxs-lookup"><span data-stu-id="b7edf-119">Inside a C# Program</span></span>](../../../csharp/programming-guide/inside-a-program/index.md)  
- [<span data-ttu-id="b7edf-120">C# 参考</span><span class="sxs-lookup"><span data-stu-id="b7edf-120">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="b7edf-121">C# 示例应用程序</span><span class="sxs-lookup"><span data-stu-id="b7edf-121">C# Sample Applications</span></span>](https://msdn.microsoft.com/library/9a9d7aaa-51d3-4224-b564-95409b0f3e15)
