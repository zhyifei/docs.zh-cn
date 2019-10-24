---
title: -highentropyva （Visual Basic）
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 203380bbe2b2828e159ee36d795b6cd4a24e2917
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775661"
---
# <a name="-highentropyva-visual-basic"></a><span data-ttu-id="5135c-102">-highentropyva （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="5135c-102">-highentropyva (Visual Basic)</span></span>
<span data-ttu-id="5135c-103">指示64位可执行文件或由[-platform： anycpu](../../../visual-basic/reference/command-line-compiler/platform.md)编译器选项标记的可执行文件是否支持高熵地址空间布局随机化（ASLR）。</span><span class="sxs-lookup"><span data-stu-id="5135c-103">Indicates whether a 64-bit executable or an executable that's marked by the [-platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5135c-104">语法</span><span class="sxs-lookup"><span data-stu-id="5135c-104">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="5135c-105">自变量</span><span class="sxs-lookup"><span data-stu-id="5135c-105">Arguments</span></span>  
 <span data-ttu-id="5135c-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="5135c-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="5135c-107">可选。</span><span class="sxs-lookup"><span data-stu-id="5135c-107">Optional.</span></span> <span data-ttu-id="5135c-108">默认情况下，或指定 `-highentropyva-` 时，此选项处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="5135c-108">The option is off by default or if you specify `-highentropyva-`.</span></span> <span data-ttu-id="5135c-109">如果指定 `-highentropyva` 或 `-highentropyva+`，则选项为 on。</span><span class="sxs-lookup"><span data-stu-id="5135c-109">The option is on if you specify `-highentropyva` or `-highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5135c-110">备注</span><span class="sxs-lookup"><span data-stu-id="5135c-110">Remarks</span></span>  
 <span data-ttu-id="5135c-111">如果指定此选项，则当内核将进程的地址空间布局作为 ASLR 的一部分随机化时，Windows 内核的兼容版本可以使用更高的平均信息量。</span><span class="sxs-lookup"><span data-stu-id="5135c-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="5135c-112">如果内核使用的平均信息量较高，则可以向内存区域（例如堆栈和堆）分配更多的地址。</span><span class="sxs-lookup"><span data-stu-id="5135c-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="5135c-113">因此，猜测特定内存区域的位置会更加困难。</span><span class="sxs-lookup"><span data-stu-id="5135c-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="5135c-114">当选项为 on 时，目标可执行文件及其依赖的任何模块在这些模块作为64位进程运行时，必须能够处理大于 4 gb 的指针值。</span><span class="sxs-lookup"><span data-stu-id="5135c-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5135c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="5135c-115">See also</span></span>

- [<span data-ttu-id="5135c-116">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="5135c-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="5135c-117">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="5135c-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
