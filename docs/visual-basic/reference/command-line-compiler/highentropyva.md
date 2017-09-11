---
title: "/highentropyva (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
caps.latest.revision: 12
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
ms.openlocfilehash: ef482f142e07e96eabf93bd2223b0d24f351553b
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="highentropyva-visual-basic"></a><span data-ttu-id="8b098-102">/highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8b098-102">/highentropyva (Visual Basic)</span></span>
<span data-ttu-id="8b098-103">指示是否是 64 位可执行文件或可执行文件标记的[/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md)编译器选项支持高熵地址空间布局随机化 (ASLR)。</span><span class="sxs-lookup"><span data-stu-id="8b098-103">Indicates whether a 64-bit executable or an executable that's marked by the [/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b098-104">语法</span><span class="sxs-lookup"><span data-stu-id="8b098-104">Syntax</span></span>  
  
```  
/highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="8b098-105">参数</span><span class="sxs-lookup"><span data-stu-id="8b098-105">Arguments</span></span>  
 <span data-ttu-id="8b098-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="8b098-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="8b098-107">可选。</span><span class="sxs-lookup"><span data-stu-id="8b098-107">Optional.</span></span> <span data-ttu-id="8b098-108">选项默认情况下处于关闭状态，或者您指定`/highentropyva-`。</span><span class="sxs-lookup"><span data-stu-id="8b098-108">The option is off by default or if you specify `/highentropyva-`.</span></span> <span data-ttu-id="8b098-109">如果您指定该选项位于`/highentropyva`或`/highentropyva+`。</span><span class="sxs-lookup"><span data-stu-id="8b098-109">The option is on if you specify `/highentropyva` or `/highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b098-110">备注</span><span class="sxs-lookup"><span data-stu-id="8b098-110">Remarks</span></span>  
 <span data-ttu-id="8b098-111">如果指定此选项，Windows 内核的兼容版本可以使用更高程度的熵 aslr 内核随机排列的进程的地址空间布局时。</span><span class="sxs-lookup"><span data-stu-id="8b098-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="8b098-112">如果内核使用更高程度的熵，则可以向内存区域，例如堆栈或堆分配更多的地址。</span><span class="sxs-lookup"><span data-stu-id="8b098-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="8b098-113">因此，猜测特定内存区域的位置会更加困难。</span><span class="sxs-lookup"><span data-stu-id="8b098-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="8b098-114">在选项上处于打开状态，目标可执行文件和任何模块时它所依赖的必须能够处理这些模块作为 64 位进程运行时大于 4 千兆字节 (GB) 的指针值。</span><span class="sxs-lookup"><span data-stu-id="8b098-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b098-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b098-115">See Also</span></span>  
 <span data-ttu-id="8b098-116">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="8b098-116">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="8b098-117"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="8b098-117"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
