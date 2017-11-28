---
title: "如何：显示命令行自变量（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f6ae495eef227c6e4d9fb9ca0d4d0c031163fd52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="98e8b-102">如何：显示命令行自变量（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="98e8b-102">How to: Display Command Line Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="98e8b-103">可通过 `Main` 的可选参数来访问在命令行处提供给可执行文件的参数。</span><span class="sxs-lookup"><span data-stu-id="98e8b-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="98e8b-104">参数以字符串数组的形式提供。</span><span class="sxs-lookup"><span data-stu-id="98e8b-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="98e8b-105">数组的每个元素都包含 1 个参数。</span><span class="sxs-lookup"><span data-stu-id="98e8b-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="98e8b-106">删除参数之间的空格。</span><span class="sxs-lookup"><span data-stu-id="98e8b-106">White-space between arguments is removed.</span></span> <span data-ttu-id="98e8b-107">例如，下面是对虚构可执行文件的命令行调用：</span><span class="sxs-lookup"><span data-stu-id="98e8b-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="98e8b-108">命令行输入</span><span class="sxs-lookup"><span data-stu-id="98e8b-108">Input on Command-line</span></span>|<span data-ttu-id="98e8b-109">传递给 Main 的字符串数组</span><span class="sxs-lookup"><span data-stu-id="98e8b-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="98e8b-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="98e8b-110">**executable.exe a b c**</span></span>|<span data-ttu-id="98e8b-111">"a"</span><span class="sxs-lookup"><span data-stu-id="98e8b-111">"a"</span></span><br /><br /> <span data-ttu-id="98e8b-112">"b"</span><span class="sxs-lookup"><span data-stu-id="98e8b-112">"b"</span></span><br /><br /> <span data-ttu-id="98e8b-113">“c”</span><span class="sxs-lookup"><span data-stu-id="98e8b-113">"c"</span></span>|  
|<span data-ttu-id="98e8b-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="98e8b-114">**executable.exe one two**</span></span>|<span data-ttu-id="98e8b-115">"one"</span><span class="sxs-lookup"><span data-stu-id="98e8b-115">"one"</span></span><br /><br /> <span data-ttu-id="98e8b-116">"two"</span><span class="sxs-lookup"><span data-stu-id="98e8b-116">"two"</span></span>|  
|<span data-ttu-id="98e8b-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="98e8b-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="98e8b-118">"one two"</span><span class="sxs-lookup"><span data-stu-id="98e8b-118">"one two"</span></span><br /><br /> <span data-ttu-id="98e8b-119">"three"</span><span class="sxs-lookup"><span data-stu-id="98e8b-119">"three"</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="98e8b-120">在 Visual Studio 中运行应用程序时，可在[“项目设计器”->“调试”页](/visualstudio/ide/reference/debug-page-project-designer)中指定命令行参数。</span><span class="sxs-lookup"><span data-stu-id="98e8b-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="98e8b-121">示例</span><span class="sxs-lookup"><span data-stu-id="98e8b-121">Example</span></span>  
 <span data-ttu-id="98e8b-122">本示例显示了传递给命令行应用程序的命令行参数。</span><span class="sxs-lookup"><span data-stu-id="98e8b-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="98e8b-123">显示的输出对应于上表中的第一项。</span><span class="sxs-lookup"><span data-stu-id="98e8b-123">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="98e8b-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98e8b-124">See Also</span></span>  
 [<span data-ttu-id="98e8b-125">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="98e8b-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="98e8b-126">在命令行上使用 csc.exe 生成</span><span class="sxs-lookup"><span data-stu-id="98e8b-126">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
 [<span data-ttu-id="98e8b-127">Main() 和命令行参数</span><span class="sxs-lookup"><span data-stu-id="98e8b-127">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)  
 [<span data-ttu-id="98e8b-128">如何：使用 foreach 访问命令行参数</span><span class="sxs-lookup"><span data-stu-id="98e8b-128">How to: Access Command-Line Arguments Using foreach</span></span>](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)  
 [<span data-ttu-id="98e8b-129">Main() 返回值</span><span class="sxs-lookup"><span data-stu-id="98e8b-129">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
