---
title: "如何：显示命令行自变量（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
caps.latest.revision: 19
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
ms.openlocfilehash: cf8a57cce252b3596f0a19c9df643427615467c6
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="a38ee-102">如何：显示命令行自变量（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="a38ee-102">How to: Display Command Line Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="a38ee-103">可通过 `Main` 的可选参数来访问在命令行处提供给可执行文件的参数。</span><span class="sxs-lookup"><span data-stu-id="a38ee-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="a38ee-104">参数以字符串数组的形式提供。</span><span class="sxs-lookup"><span data-stu-id="a38ee-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="a38ee-105">数组的每个元素都包含 1 个参数。</span><span class="sxs-lookup"><span data-stu-id="a38ee-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="a38ee-106">删除参数之间的空格。</span><span class="sxs-lookup"><span data-stu-id="a38ee-106">White-space between arguments is removed.</span></span> <span data-ttu-id="a38ee-107">例如，下面是对虚构可执行文件的命令行调用：</span><span class="sxs-lookup"><span data-stu-id="a38ee-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="a38ee-108">命令行输入</span><span class="sxs-lookup"><span data-stu-id="a38ee-108">Input on Command-line</span></span>|<span data-ttu-id="a38ee-109">传递给 Main 的字符串数组</span><span class="sxs-lookup"><span data-stu-id="a38ee-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="a38ee-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="a38ee-110">**executable.exe a b c**</span></span>|<span data-ttu-id="a38ee-111">"a"</span><span class="sxs-lookup"><span data-stu-id="a38ee-111">"a"</span></span><br /><br /> <span data-ttu-id="a38ee-112">"b"</span><span class="sxs-lookup"><span data-stu-id="a38ee-112">"b"</span></span><br /><br /> <span data-ttu-id="a38ee-113">“c”</span><span class="sxs-lookup"><span data-stu-id="a38ee-113">"c"</span></span>|  
|<span data-ttu-id="a38ee-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="a38ee-114">**executable.exe one two**</span></span>|<span data-ttu-id="a38ee-115">"one"</span><span class="sxs-lookup"><span data-stu-id="a38ee-115">"one"</span></span><br /><br /> <span data-ttu-id="a38ee-116">"two"</span><span class="sxs-lookup"><span data-stu-id="a38ee-116">"two"</span></span>|  
|<span data-ttu-id="a38ee-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="a38ee-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="a38ee-118">"one two"</span><span class="sxs-lookup"><span data-stu-id="a38ee-118">"one two"</span></span><br /><br /> <span data-ttu-id="a38ee-119">"three"</span><span class="sxs-lookup"><span data-stu-id="a38ee-119">"three"</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="a38ee-120">在 Visual Studio 中运行应用程序时，可在[“项目设计器”->“调试”页](/visualstudio/ide/reference/debug-page-project-designer)中指定命令行参数。</span><span class="sxs-lookup"><span data-stu-id="a38ee-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a38ee-121">示例</span><span class="sxs-lookup"><span data-stu-id="a38ee-121">Example</span></span>  
 <span data-ttu-id="a38ee-122">本示例显示了传递给命令行应用程序的命令行参数。</span><span class="sxs-lookup"><span data-stu-id="a38ee-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="a38ee-123">显示的输出对应于上表中的第一项。</span><span class="sxs-lookup"><span data-stu-id="a38ee-123">The output shown is for the first entry in the table above.</span></span>  
  
 <span data-ttu-id="a38ee-124">[!code-cs[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a38ee-124">[!code-cs[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a38ee-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="a38ee-125">See Also</span></span>  
 <span data-ttu-id="a38ee-126">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a38ee-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a38ee-127">[在命令行上使用 csc.exe 生成](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) </span><span class="sxs-lookup"><span data-stu-id="a38ee-127">[Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) </span></span>  
 <span data-ttu-id="a38ee-128">[Main() 和命令行自变量](../../../csharp/programming-guide/main-and-command-args/index.md) </span><span class="sxs-lookup"><span data-stu-id="a38ee-128">[Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) </span></span>  
 <span data-ttu-id="a38ee-129">[如何：使用 foreach 访问命令行参数](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md) </span><span class="sxs-lookup"><span data-stu-id="a38ee-129">[How to: Access Command-Line Arguments Using foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md) </span></span>  
 [<span data-ttu-id="a38ee-130">Main() 返回值</span><span class="sxs-lookup"><span data-stu-id="a38ee-130">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)

