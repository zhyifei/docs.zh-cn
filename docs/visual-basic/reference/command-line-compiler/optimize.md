---
title: /optimize
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dead17435cd147bdcdf91bdc5b8e0aa651e9e9fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="optimize"></a><span data-ttu-id="a12af-102">/optimize</span><span class="sxs-lookup"><span data-stu-id="a12af-102">/optimize</span></span>
<span data-ttu-id="a12af-103">启用或禁用编译器优化。</span><span class="sxs-lookup"><span data-stu-id="a12af-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a12af-104">语法</span><span class="sxs-lookup"><span data-stu-id="a12af-104">Syntax</span></span>  
  
```  
/optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="a12af-105">参数</span><span class="sxs-lookup"><span data-stu-id="a12af-105">Arguments</span></span>  
  
|<span data-ttu-id="a12af-106">术语</span><span class="sxs-lookup"><span data-stu-id="a12af-106">Term</span></span>|<span data-ttu-id="a12af-107">定义</span><span class="sxs-lookup"><span data-stu-id="a12af-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="a12af-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="a12af-108">`+` &#124; `-`</span></span>|<span data-ttu-id="a12af-109">可选。</span><span class="sxs-lookup"><span data-stu-id="a12af-109">Optional.</span></span> <span data-ttu-id="a12af-110">`/optimize-`选项禁用编译器优化。</span><span class="sxs-lookup"><span data-stu-id="a12af-110">The `/optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="a12af-111">`/optimize+`选项将启用优化。</span><span class="sxs-lookup"><span data-stu-id="a12af-111">The `/optimize+` option enables optimizations.</span></span> <span data-ttu-id="a12af-112">默认情况下，禁用优化。</span><span class="sxs-lookup"><span data-stu-id="a12af-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a12af-113">备注</span><span class="sxs-lookup"><span data-stu-id="a12af-113">Remarks</span></span>  
 <span data-ttu-id="a12af-114">编译器优化使你的输出文件更小、 更快、 更高效。</span><span class="sxs-lookup"><span data-stu-id="a12af-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="a12af-115">但是，因为优化会导致中的输出文件中的代码重排`/optimize+`可能使调试困难。</span><span class="sxs-lookup"><span data-stu-id="a12af-115">However, because optimizations result in code rearrangement in the output file, `/optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="a12af-116">使用生成的所有模块`/target:module`对于程序集必须使用相同`/optimize`与程序集的设置。</span><span class="sxs-lookup"><span data-stu-id="a12af-116">All modules generated with `/target:module` for an assembly must use the same `/optimize` settings as the assembly.</span></span> <span data-ttu-id="a12af-117">有关详细信息，请参阅[/target (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/target.md)。</span><span class="sxs-lookup"><span data-stu-id="a12af-117">For more information, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="a12af-118">你可以组合`/optimize`和`/debug`选项。</span><span class="sxs-lookup"><span data-stu-id="a12af-118">You can combine the `/optimize` and `/debug` options.</span></span>  
  
|<span data-ttu-id="a12af-119">若要设置 / 优化在 Visual Studio 集成的开发环境</span><span class="sxs-lookup"><span data-stu-id="a12af-119">To set /optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="a12af-120">1.在 “解决方案资源管理器”中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="a12af-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a12af-121">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="a12af-121">On the **Project** menu, click **Properties**.</span></span><br />     <span data-ttu-id="a12af-122">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="a12af-122">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="a12af-123">2.单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="a12af-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="a12af-124">3.单击 **“高级”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="a12af-124">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="a12af-125">4.修改**启用优化**复选框。</span><span class="sxs-lookup"><span data-stu-id="a12af-125">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a12af-126">示例</span><span class="sxs-lookup"><span data-stu-id="a12af-126">Example</span></span>  
 <span data-ttu-id="a12af-127">下面的代码编译`T2.vb`并启用编译器优化。</span><span class="sxs-lookup"><span data-stu-id="a12af-127">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```  
vbc t2.vb /optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="a12af-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a12af-128">See Also</span></span>  
 [<span data-ttu-id="a12af-129">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="a12af-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="a12af-130">/debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a12af-130">/debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [<span data-ttu-id="a12af-131">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="a12af-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="a12af-132">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a12af-132">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
