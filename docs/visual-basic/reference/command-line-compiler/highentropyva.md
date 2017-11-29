---
title: /highentropyva (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 55568808bb94f98ce7a20016fc5a2a0a2ef23a38
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="highentropyva-visual-basic"></a><span data-ttu-id="bf886-102">/highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf886-102">/highentropyva (Visual Basic)</span></span>
<span data-ttu-id="bf886-103">指示是否 64 位可执行文件或可执行文件标记的[/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md)编译器选项支持高熵地址空间布局随机化 (ASLR)。</span><span class="sxs-lookup"><span data-stu-id="bf886-103">Indicates whether a 64-bit executable or an executable that's marked by the [/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf886-104">语法</span><span class="sxs-lookup"><span data-stu-id="bf886-104">Syntax</span></span>  
  
```  
/highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="bf886-105">参数</span><span class="sxs-lookup"><span data-stu-id="bf886-105">Arguments</span></span>  
 <span data-ttu-id="bf886-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="bf886-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="bf886-107">可选。</span><span class="sxs-lookup"><span data-stu-id="bf886-107">Optional.</span></span> <span data-ttu-id="bf886-108">选项默认处于关闭状态，或如果你指定`/highentropyva-`。</span><span class="sxs-lookup"><span data-stu-id="bf886-108">The option is off by default or if you specify `/highentropyva-`.</span></span> <span data-ttu-id="bf886-109">如果你指定的选项位于`/highentropyva`或`/highentropyva+`。</span><span class="sxs-lookup"><span data-stu-id="bf886-109">The option is on if you specify `/highentropyva` or `/highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf886-110">备注</span><span class="sxs-lookup"><span data-stu-id="bf886-110">Remarks</span></span>  
 <span data-ttu-id="bf886-111">如果指定此选项时，Windows 内核的兼容版本可以使用更高程度的熵时内核的 ASLR 一部分随机进程的地址空间布局。</span><span class="sxs-lookup"><span data-stu-id="bf886-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="bf886-112">如果内核使用更高程度的平均信息量，可以将更多的地址分配到例如堆栈或堆的内存区域。</span><span class="sxs-lookup"><span data-stu-id="bf886-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="bf886-113">因此，猜测特定内存区域的位置会更加困难。</span><span class="sxs-lookup"><span data-stu-id="bf886-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="bf886-114">选项上时，目标可执行文件和任何模块上它依赖于它必须是能够处理这些模块作为 64 位进程运行时会大于 4 千兆字节 (GB) 的指针值。</span><span class="sxs-lookup"><span data-stu-id="bf886-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf886-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf886-115">See Also</span></span>  
 [<span data-ttu-id="bf886-116">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="bf886-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="bf886-117">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="bf886-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
