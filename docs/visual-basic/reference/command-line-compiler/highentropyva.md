---
title: -highentropyva (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 16bfea37a5742ac5aaaabfacdcf03a2b5bedb6db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663266"
---
# <a name="-highentropyva-visual-basic"></a><span data-ttu-id="3e8db-102">-highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e8db-102">-highentropyva (Visual Basic)</span></span>
<span data-ttu-id="3e8db-103">指示是否是 64 位可执行文件或可执行文件标记[/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md)编译器选项支持高熵地址空间布局随机化 (ASLR)。</span><span class="sxs-lookup"><span data-stu-id="3e8db-103">Indicates whether a 64-bit executable or an executable that's marked by the [/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e8db-104">语法</span><span class="sxs-lookup"><span data-stu-id="3e8db-104">Syntax</span></span>  
  
```  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="3e8db-105">自变量</span><span class="sxs-lookup"><span data-stu-id="3e8db-105">Arguments</span></span>  
 <span data-ttu-id="3e8db-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="3e8db-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="3e8db-107">可选。</span><span class="sxs-lookup"><span data-stu-id="3e8db-107">Optional.</span></span> <span data-ttu-id="3e8db-108">该选项默认处于关闭状态或者您指定`-highentropyva-`。</span><span class="sxs-lookup"><span data-stu-id="3e8db-108">The option is off by default or if you specify `-highentropyva-`.</span></span> <span data-ttu-id="3e8db-109">如果您指定的选项位于`-highentropyva`或`-highentropyva+`。</span><span class="sxs-lookup"><span data-stu-id="3e8db-109">The option is on if you specify `-highentropyva` or `-highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e8db-110">备注</span><span class="sxs-lookup"><span data-stu-id="3e8db-110">Remarks</span></span>  
 <span data-ttu-id="3e8db-111">如果指定此选项，Windows 内核的兼容版本可以使用更高程度的熵，内核在 ASLR 随机进程的地址空间布局时。</span><span class="sxs-lookup"><span data-stu-id="3e8db-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="3e8db-112">如果内核使用更高程度的熵，可以向内存区域，例如堆栈或堆分配更多的地址。</span><span class="sxs-lookup"><span data-stu-id="3e8db-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="3e8db-113">因此，猜测特定内存区域的位置会更加困难。</span><span class="sxs-lookup"><span data-stu-id="3e8db-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="3e8db-114">当选项打开时，目标可执行文件和任何模块上它依赖于它必须是能够处理这些模块作为 64 位进程运行时大于 4 千兆字节 (GB) 的指针值。</span><span class="sxs-lookup"><span data-stu-id="3e8db-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e8db-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e8db-115">See also</span></span>

- [<span data-ttu-id="3e8db-116">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="3e8db-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="3e8db-117">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="3e8db-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
