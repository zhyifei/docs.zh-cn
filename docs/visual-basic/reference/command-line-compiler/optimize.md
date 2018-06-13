---
title: -优化
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: 2f066835c5f864538f281d4c58772e0e60c132f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649940"
---
# <a name="-optimize"></a><span data-ttu-id="d0a42-102">-优化</span><span class="sxs-lookup"><span data-stu-id="d0a42-102">-optimize</span></span>
<span data-ttu-id="d0a42-103">启用或禁用编译器优化。</span><span class="sxs-lookup"><span data-stu-id="d0a42-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0a42-104">语法</span><span class="sxs-lookup"><span data-stu-id="d0a42-104">Syntax</span></span>  
  
```  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d0a42-105">自变量</span><span class="sxs-lookup"><span data-stu-id="d0a42-105">Arguments</span></span>  
  
|<span data-ttu-id="d0a42-106">术语</span><span class="sxs-lookup"><span data-stu-id="d0a42-106">Term</span></span>|<span data-ttu-id="d0a42-107">定义</span><span class="sxs-lookup"><span data-stu-id="d0a42-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="d0a42-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="d0a42-108">`+` &#124; `-`</span></span>|<span data-ttu-id="d0a42-109">可选。</span><span class="sxs-lookup"><span data-stu-id="d0a42-109">Optional.</span></span> <span data-ttu-id="d0a42-110">`-optimize-`选项禁用编译器优化。</span><span class="sxs-lookup"><span data-stu-id="d0a42-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="d0a42-111">`-optimize+`选项将启用优化。</span><span class="sxs-lookup"><span data-stu-id="d0a42-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="d0a42-112">默认情况下，禁用优化。</span><span class="sxs-lookup"><span data-stu-id="d0a42-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0a42-113">备注</span><span class="sxs-lookup"><span data-stu-id="d0a42-113">Remarks</span></span>  
 <span data-ttu-id="d0a42-114">编译器优化会使输出文件更智能、更快并且更有效。</span><span class="sxs-lookup"><span data-stu-id="d0a42-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="d0a42-115">但是，因为优化会导致中的输出文件中的代码重排`-optimize+`可能使调试困难。</span><span class="sxs-lookup"><span data-stu-id="d0a42-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="d0a42-116">使用生成的所有模块`-target:module`对于程序集必须使用相同`-optimize`与程序集的设置。</span><span class="sxs-lookup"><span data-stu-id="d0a42-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="d0a42-117">有关详细信息，请参阅[-目标 (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/target.md)。</span><span class="sxs-lookup"><span data-stu-id="d0a42-117">For more information, see [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="d0a42-118">你可以组合`-optimize`和`-debug`选项。</span><span class="sxs-lookup"><span data-stu-id="d0a42-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="d0a42-119">若要设置的优化在 Visual Studio 集成的开发环境</span><span class="sxs-lookup"><span data-stu-id="d0a42-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="d0a42-120">1.在 **“解决方案资源管理器”** 中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="d0a42-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d0a42-121">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="d0a42-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="d0a42-122">2.单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="d0a42-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="d0a42-123">3.单击“高级”按钮。</span><span class="sxs-lookup"><span data-stu-id="d0a42-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="d0a42-124">4.修改**启用优化**复选框。</span><span class="sxs-lookup"><span data-stu-id="d0a42-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d0a42-125">示例</span><span class="sxs-lookup"><span data-stu-id="d0a42-125">Example</span></span>  
 <span data-ttu-id="d0a42-126">下面的代码编译`T2.vb`并启用编译器优化。</span><span class="sxs-lookup"><span data-stu-id="d0a42-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="d0a42-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0a42-127">See Also</span></span>  
 [<span data-ttu-id="d0a42-128">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="d0a42-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="d0a42-129">-调试 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0a42-129">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [<span data-ttu-id="d0a42-130">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="d0a42-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="d0a42-131">-目标 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0a42-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
