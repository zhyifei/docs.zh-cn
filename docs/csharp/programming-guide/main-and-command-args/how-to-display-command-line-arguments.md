---
title: 如何：显示命令行参数 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: c88219d03d40c814338a1b09ccd37cfc03c2d577
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881016"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="3d49f-102">如何：显示命令行参数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="3d49f-102">How to: Display Command Line Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="3d49f-103">可通过 `Main` 的可选参数来访问在命令行处提供给可执行文件的参数。</span><span class="sxs-lookup"><span data-stu-id="3d49f-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="3d49f-104">参数以字符串数组的形式提供。</span><span class="sxs-lookup"><span data-stu-id="3d49f-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="3d49f-105">数组的每个元素都包含 1 个参数。</span><span class="sxs-lookup"><span data-stu-id="3d49f-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="3d49f-106">删除参数之间的空格。</span><span class="sxs-lookup"><span data-stu-id="3d49f-106">White-space between arguments is removed.</span></span> <span data-ttu-id="3d49f-107">例如，下面是对虚构可执行文件的命令行调用：</span><span class="sxs-lookup"><span data-stu-id="3d49f-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="3d49f-108">命令行输入</span><span class="sxs-lookup"><span data-stu-id="3d49f-108">Input on Command-line</span></span>|<span data-ttu-id="3d49f-109">传递给 Main 的字符串数组</span><span class="sxs-lookup"><span data-stu-id="3d49f-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="3d49f-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="3d49f-110">**executable.exe a b c**</span></span>|<span data-ttu-id="3d49f-111">"a"</span><span class="sxs-lookup"><span data-stu-id="3d49f-111">"a"</span></span><br /><br /> <span data-ttu-id="3d49f-112">"b"</span><span class="sxs-lookup"><span data-stu-id="3d49f-112">"b"</span></span><br /><br /> <span data-ttu-id="3d49f-113">“c”</span><span class="sxs-lookup"><span data-stu-id="3d49f-113">"c"</span></span>|  
|<span data-ttu-id="3d49f-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="3d49f-114">**executable.exe one two**</span></span>|<span data-ttu-id="3d49f-115">"one"</span><span class="sxs-lookup"><span data-stu-id="3d49f-115">"one"</span></span><br /><br /> <span data-ttu-id="3d49f-116">"two"</span><span class="sxs-lookup"><span data-stu-id="3d49f-116">"two"</span></span>|  
|<span data-ttu-id="3d49f-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="3d49f-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="3d49f-118">"one two"</span><span class="sxs-lookup"><span data-stu-id="3d49f-118">"one two"</span></span><br /><br /> <span data-ttu-id="3d49f-119">"three"</span><span class="sxs-lookup"><span data-stu-id="3d49f-119">"three"</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="3d49f-120">在 Visual Studio 中运行应用程序时，可在[“项目设计器”->“调试”页](/visualstudio/ide/reference/debug-page-project-designer)中指定命令行参数。</span><span class="sxs-lookup"><span data-stu-id="3d49f-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d49f-121">示例</span><span class="sxs-lookup"><span data-stu-id="3d49f-121">Example</span></span>  
 <span data-ttu-id="3d49f-122">本示例显示了传递给命令行应用程序的命令行参数。</span><span class="sxs-lookup"><span data-stu-id="3d49f-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="3d49f-123">显示的输出对应于上表中的第一项。</span><span class="sxs-lookup"><span data-stu-id="3d49f-123">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="3d49f-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d49f-124">See also</span></span>

- [<span data-ttu-id="3d49f-125">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="3d49f-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="3d49f-126">在命令行上使用 csc.exe 生成</span><span class="sxs-lookup"><span data-stu-id="3d49f-126">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="3d49f-127">Main() 和命令行参数</span><span class="sxs-lookup"><span data-stu-id="3d49f-127">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)
- [<span data-ttu-id="3d49f-128">Main() 返回值</span><span class="sxs-lookup"><span data-stu-id="3d49f-128">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
