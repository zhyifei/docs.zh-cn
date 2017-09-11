---
title: "C# 程序的通用结构（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, program structure
ms.assetid: 5ae964a5-0ef0-40fe-88fb-6d1793371d0d
caps.latest.revision: 21
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
ms.openlocfilehash: d55ac6a6d35e5f47ab26da681afe9fb5555331ec
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="general-structure-of-a-c-program-c-programming-guide"></a><span data-ttu-id="61f46-102">C# 程序的通用结构（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="61f46-102">General Structure of a C# Program (C# Programming Guide)</span></span>
<span data-ttu-id="61f46-103">C# 程序可由一个或多个文件组成。</span><span class="sxs-lookup"><span data-stu-id="61f46-103">C# programs can consist of one or more files.</span></span> <span data-ttu-id="61f46-104">每个文件均可包含零个或多个命名空间。</span><span class="sxs-lookup"><span data-stu-id="61f46-104">Each file can contain zero or more namespaces.</span></span> <span data-ttu-id="61f46-105">一个命名空间除了可包含其他命名空间外,还可包含类、结构、接口、枚举、委托等类型。</span><span class="sxs-lookup"><span data-stu-id="61f46-105">A namespace can contain types such as classes, structs, interfaces, enumerations, and delegates, in addition to other namespaces.</span></span> <span data-ttu-id="61f46-106">下面是包含所有这些元素的 C# 程序主干。</span><span class="sxs-lookup"><span data-stu-id="61f46-106">The following is the skeleton of a C# program that contains all of these elements.</span></span>  
  
 <span data-ttu-id="61f46-107">[!code-cs[csProgGuide#34](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/general-structure-of-a-csharp-program_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="61f46-107">[!code-cs[csProgGuide#34](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/general-structure-of-a-csharp-program_1.cs)]</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="61f46-108">相关章节</span><span class="sxs-lookup"><span data-stu-id="61f46-108">Related Sections</span></span>  
 <span data-ttu-id="61f46-109">更多相关信息：</span><span class="sxs-lookup"><span data-stu-id="61f46-109">For more information:</span></span>  
  
-   [<span data-ttu-id="61f46-110">类</span><span class="sxs-lookup"><span data-stu-id="61f46-110">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)  
  
-   [<span data-ttu-id="61f46-111">结构</span><span class="sxs-lookup"><span data-stu-id="61f46-111">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
-   [<span data-ttu-id="61f46-112">命名空间</span><span class="sxs-lookup"><span data-stu-id="61f46-112">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="61f46-113">接口</span><span class="sxs-lookup"><span data-stu-id="61f46-113">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
  
-   [<span data-ttu-id="61f46-114">委托</span><span class="sxs-lookup"><span data-stu-id="61f46-114">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="61f46-115">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="61f46-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="61f46-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="61f46-116">See Also</span></span>  
 <span data-ttu-id="61f46-117">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="61f46-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="61f46-118">[在 C# 程序内部](../../../csharp/programming-guide/inside-a-program/index.md) </span><span class="sxs-lookup"><span data-stu-id="61f46-118">[Inside a C# Program](../../../csharp/programming-guide/inside-a-program/index.md) </span></span>  
 <span data-ttu-id="61f46-119">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="61f46-119">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 [<span data-ttu-id="61f46-120">\<paveover>C# 示例应用程序</span><span class="sxs-lookup"><span data-stu-id="61f46-120">\<paveover>C# Sample Applications</span></span>](http://msdn.microsoft.com/en-us/9a9d7aaa-51d3-4224-b564-95409b0f3e15)

