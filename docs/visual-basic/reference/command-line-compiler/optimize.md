---
title: "/optimize |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization, enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f01ab17d4a2f5d123538294a7a13d7a6d7a40267
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="optimize"></a><span data-ttu-id="4e7ce-102">/optimize</span><span class="sxs-lookup"><span data-stu-id="4e7ce-102">/optimize</span></span>
<span data-ttu-id="4e7ce-103">启用或禁用编译器优化。</span><span class="sxs-lookup"><span data-stu-id="4e7ce-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e7ce-104">语法</span><span class="sxs-lookup"><span data-stu-id="4e7ce-104">Syntax</span></span>  
  
```  
/optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="4e7ce-105">参数</span><span class="sxs-lookup"><span data-stu-id="4e7ce-105">Arguments</span></span>  
  
|<span data-ttu-id="4e7ce-106">术语</span><span class="sxs-lookup"><span data-stu-id="4e7ce-106">Term</span></span>|<span data-ttu-id="4e7ce-107">定义</span><span class="sxs-lookup"><span data-stu-id="4e7ce-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="4e7ce-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="4e7ce-108">`+` &#124; `-`</span></span>|<span data-ttu-id="4e7ce-109">可选。</span><span class="sxs-lookup"><span data-stu-id="4e7ce-109">Optional.</span></span> <span data-ttu-id="4e7ce-110">`/optimize-`选项禁用编译器优化。</span><span class="sxs-lookup"><span data-stu-id="4e7ce-110">The `/optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="4e7ce-111">`/optimize+`选项将启用优化。</span><span class="sxs-lookup"><span data-stu-id="4e7ce-111">The `/optimize+` option enables optimizations.</span></span> <span data-ttu-id="4e7ce-112">默认情况下，禁用优化。</span><span class="sxs-lookup"><span data-stu-id="4e7ce-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e7ce-113">备注</span><span class="sxs-lookup"><span data-stu-id="4e7ce-113">Remarks</span></span>  
 <span data-ttu-id="4e7ce-114">编译器优化使输出文件更小、 更快、 更高效。</span><span class="sxs-lookup"><span data-stu-id="4e7ce-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="4e7ce-115">但是，这是因为优化会导致代码中重新排列输出文件中，在`/optimize+`可能使调试困难。</span><span class="sxs-lookup"><span data-stu-id="4e7ce-115">However, because optimizations result in code rearrangement in the output file, `/optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="4e7ce-116">使用生成的所有模块`/target:module`为程序集必须都使用相同`/optimize`与程序集的设置。</span><span class="sxs-lookup"><span data-stu-id="4e7ce-116">All modules generated with `/target:module` for an assembly must use the same `/optimize` settings as the assembly.</span></span> <span data-ttu-id="4e7ce-117">有关详细信息，请参阅[/target (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/target.md)。</span><span class="sxs-lookup"><span data-stu-id="4e7ce-117">For more information, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="4e7ce-118">您可以组合使用`/optimize`和`/debug`选项。</span><span class="sxs-lookup"><span data-stu-id="4e7ce-118">You can combine the `/optimize` and `/debug` options.</span></span>  
  
|<span data-ttu-id="4e7ce-119">设置 / 优化在 Visual Studio 集成的开发环境</span><span class="sxs-lookup"><span data-stu-id="4e7ce-119">To set /optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="4e7ce-120">1.在 **“解决方案资源管理器”**中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="4e7ce-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="4e7ce-121">在**项目**菜单上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="4e7ce-121">On the **Project** menu, click **Properties**.</span></span><br />     <span data-ttu-id="4e7ce-122">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="4e7ce-122">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="4e7ce-123">2.单击“编译”****选项卡。</span><span class="sxs-lookup"><span data-stu-id="4e7ce-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="4e7ce-124">3.单击 **“高级”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="4e7ce-124">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="4e7ce-125">4.修改**启用优化**复选框。</span><span class="sxs-lookup"><span data-stu-id="4e7ce-125">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4e7ce-126">示例</span><span class="sxs-lookup"><span data-stu-id="4e7ce-126">Example</span></span>  
 <span data-ttu-id="4e7ce-127">下面的代码编译`T2.vb`和允许进行编译器优化。</span><span class="sxs-lookup"><span data-stu-id="4e7ce-127">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```  
vbc t2.vb /optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="4e7ce-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e7ce-128">See Also</span></span>  
 <span data-ttu-id="4e7ce-129">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="4e7ce-129">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="4e7ce-130"> [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md) </span><span class="sxs-lookup"><span data-stu-id="4e7ce-130"> [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md) </span></span>  
<span data-ttu-id="4e7ce-131"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="4e7ce-131"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="4e7ce-132"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)</span><span class="sxs-lookup"><span data-stu-id="4e7ce-132"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)</span></span>
