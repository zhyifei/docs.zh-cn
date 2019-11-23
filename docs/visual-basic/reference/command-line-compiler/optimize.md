---
title: -optimize
ms.date: 07/20/2015
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
ms.openlocfilehash: e8daf4a49123623b6470bc3c6281869f1b9b3d0f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005367"
---
# <a name="-optimize"></a><span data-ttu-id="6a3b2-102">-optimize</span><span class="sxs-lookup"><span data-stu-id="6a3b2-102">-optimize</span></span>
<span data-ttu-id="6a3b2-103">启用或禁用编译器优化。</span><span class="sxs-lookup"><span data-stu-id="6a3b2-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a3b2-104">语法</span><span class="sxs-lookup"><span data-stu-id="6a3b2-104">Syntax</span></span>  
  
```console  
-optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6a3b2-105">参数</span><span class="sxs-lookup"><span data-stu-id="6a3b2-105">Arguments</span></span>  
  
|<span data-ttu-id="6a3b2-106">术语</span><span class="sxs-lookup"><span data-stu-id="6a3b2-106">Term</span></span>|<span data-ttu-id="6a3b2-107">Definition</span><span class="sxs-lookup"><span data-stu-id="6a3b2-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="6a3b2-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="6a3b2-108">`+` &#124; `-`</span></span>|<span data-ttu-id="6a3b2-109">可选。</span><span class="sxs-lookup"><span data-stu-id="6a3b2-109">Optional.</span></span> <span data-ttu-id="6a3b2-110">`-optimize-` 选项禁用编译器优化。</span><span class="sxs-lookup"><span data-stu-id="6a3b2-110">The `-optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="6a3b2-111">`-optimize+` 选项启用优化。</span><span class="sxs-lookup"><span data-stu-id="6a3b2-111">The `-optimize+` option enables optimizations.</span></span> <span data-ttu-id="6a3b2-112">默认情况下，禁用优化。</span><span class="sxs-lookup"><span data-stu-id="6a3b2-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a3b2-113">备注</span><span class="sxs-lookup"><span data-stu-id="6a3b2-113">Remarks</span></span>  
 <span data-ttu-id="6a3b2-114">编译器优化会使输出文件更智能、更快并且更有效。</span><span class="sxs-lookup"><span data-stu-id="6a3b2-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="6a3b2-115">但是，由于优化会导致输出文件中的代码重新排列，因此 `-optimize+` 会使调试变得困难。</span><span class="sxs-lookup"><span data-stu-id="6a3b2-115">However, because optimizations result in code rearrangement in the output file, `-optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="6a3b2-116">使用程序集 `-target:module` 生成的所有模块都必须使用与程序集相同的 `-optimize` 设置。</span><span class="sxs-lookup"><span data-stu-id="6a3b2-116">All modules generated with `-target:module` for an assembly must use the same `-optimize` settings as the assembly.</span></span> <span data-ttu-id="6a3b2-117">有关详细信息，请参阅[-target （Visual Basic）](../../../visual-basic/reference/command-line-compiler/target.md)。</span><span class="sxs-lookup"><span data-stu-id="6a3b2-117">For more information, see [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="6a3b2-118">可以组合 `-optimize` 和 `-debug` 选项。</span><span class="sxs-lookup"><span data-stu-id="6a3b2-118">You can combine the `-optimize` and `-debug` options.</span></span>  
  
|<span data-ttu-id="6a3b2-119">在 Visual Studio 集成开发环境中设置-优化</span><span class="sxs-lookup"><span data-stu-id="6a3b2-119">To set -optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="6a3b2-120">1. 在**解决方案资源管理器**中选择了一个项目。</span><span class="sxs-lookup"><span data-stu-id="6a3b2-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="6a3b2-121">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="6a3b2-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="6a3b2-122">2. 单击 "**编译**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="6a3b2-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="6a3b2-123">3. 单击 "**高级**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="6a3b2-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="6a3b2-124">4. 修改 "**启用优化**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="6a3b2-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6a3b2-125">示例</span><span class="sxs-lookup"><span data-stu-id="6a3b2-125">Example</span></span>  
 <span data-ttu-id="6a3b2-126">下面的代码编译 `T2.vb`，并启用编译器优化。</span><span class="sxs-lookup"><span data-stu-id="6a3b2-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```console
vbc t2.vb -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="6a3b2-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a3b2-127">See also</span></span>

- [<span data-ttu-id="6a3b2-128">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="6a3b2-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="6a3b2-129">-debug （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="6a3b2-129">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="6a3b2-130">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="6a3b2-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="6a3b2-131">-target （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="6a3b2-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
