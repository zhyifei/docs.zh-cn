---
title: -highentropyva（C# 编译器选项）
ms.date: 07/20/2015
f1_keywords:
- /highentropyva
helpviewer_keywords:
- /highentropyva compiler option [C#]
- -highentropyva compiler option [C#]
- highentropyva compiler option [C#]
ms.assetid: eaf409b3-384e-49dd-9417-62453658f421
ms.openlocfilehash: b710bb829f6a7591159d2f2e6bacc670d21c42d1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "69606849"
---
# <a name="-highentropyva-c-compiler-options"></a><span data-ttu-id="5cc8f-102">-highentropyva（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="5cc8f-102">-highentropyva (C# Compiler Options)</span></span>
<span data-ttu-id="5cc8f-103">-highentropyva 编译器选项可向 Windows 内核提供下列信息：特定的可执行文件是否支持高熵地址空间布局随机化 (ASLR)  。</span><span class="sxs-lookup"><span data-stu-id="5cc8f-103">The **-highentropyva** compiler option tells the Windows kernel whether a particular executable supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cc8f-104">语法</span><span class="sxs-lookup"><span data-stu-id="5cc8f-104">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="5cc8f-105">参数</span><span class="sxs-lookup"><span data-stu-id="5cc8f-105">Arguments</span></span>  
 <span data-ttu-id="5cc8f-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="5cc8f-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="5cc8f-107">此选项指定 64 位可执行文件或由 [-platform:anycpu](./platform-compiler-option.md) 编译器选项标记的可执行文件支持高熵虚拟地址空间。</span><span class="sxs-lookup"><span data-stu-id="5cc8f-107">This option specifies that a 64-bit executable or an executable that is marked by the [-platform:anycpu](./platform-compiler-option.md) compiler option supports a high entropy virtual address space.</span></span> <span data-ttu-id="5cc8f-108">默认情况下，此选项处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="5cc8f-108">The option is disabled by default.</span></span> <span data-ttu-id="5cc8f-109">通过 -highentropyva+ 或 -highentropyva 启用它   。</span><span class="sxs-lookup"><span data-stu-id="5cc8f-109">Use **-highentropyva+** or **-highentropyva** to enable it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5cc8f-110">备注</span><span class="sxs-lookup"><span data-stu-id="5cc8f-110">Remarks</span></span>  
 <span data-ttu-id="5cc8f-111">当随机化进程的地址空间布局包含在 ASLR 中时，-highentropyva 选项允许 Windows 内核的兼容版本使用更高程度的熵  。</span><span class="sxs-lookup"><span data-stu-id="5cc8f-111">The **-highentropyva** option enables compatible versions of the Windows kernel to use higher degrees of entropy when randomizing the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="5cc8f-112">使用更高程度的熵意味着，可向内存区域（例如堆栈或堆）分配更多的地址。</span><span class="sxs-lookup"><span data-stu-id="5cc8f-112">Using higher degrees of entropy means that a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="5cc8f-113">因此，猜测特定内存区域的位置会更加困难。</span><span class="sxs-lookup"><span data-stu-id="5cc8f-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="5cc8f-114">指定 -highentropyva 编译器选项时，目标可执行文件及其依赖的任何模块在作为 64 位进程运行时，必须能够处理大于 4 GB 的指针值  。</span><span class="sxs-lookup"><span data-stu-id="5cc8f-114">When the **-highentropyva** compiler option is specified, the target executable and any modules that it depends on must be able to handle pointer values that are larger than 4 gigabytes (GB) when they are running as a 64-bit process.</span></span>
