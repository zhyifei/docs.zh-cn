---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 479f9f639548eb81351d1df3f8f08b29b393cba1
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085022"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="6f654-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="6f654-102">-moduleassemblyname</span></span>
<span data-ttu-id="6f654-103">指定此模块所属程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="6f654-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f654-104">语法</span><span class="sxs-lookup"><span data-stu-id="6f654-104">Syntax</span></span>  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="6f654-105">自变量</span><span class="sxs-lookup"><span data-stu-id="6f654-105">Arguments</span></span>  
  
|<span data-ttu-id="6f654-106">术语</span><span class="sxs-lookup"><span data-stu-id="6f654-106">Term</span></span>|<span data-ttu-id="6f654-107">定义</span><span class="sxs-lookup"><span data-stu-id="6f654-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="6f654-108">此模块的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="6f654-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f654-109">备注</span><span class="sxs-lookup"><span data-stu-id="6f654-109">Remarks</span></span>  
 <span data-ttu-id="6f654-110">编译器进程`-moduleassemblyname`选项仅当`-target:module`指定选项。</span><span class="sxs-lookup"><span data-stu-id="6f654-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="6f654-111">这将导致编译器创建一个模块。</span><span class="sxs-lookup"><span data-stu-id="6f654-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="6f654-112">由编译器创建的模块是仅对与指定的程序集的有效`-moduleassemblyname`选项。</span><span class="sxs-lookup"><span data-stu-id="6f654-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="6f654-113">如果将模块置于不同的程序集，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="6f654-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="6f654-114">`-moduleassemblyname`选项仅当满足以下条件时，才需要：</span><span class="sxs-lookup"><span data-stu-id="6f654-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
-   <span data-ttu-id="6f654-115">该模块中的数据类型需要有权`Friend`中引用的程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="6f654-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
-   <span data-ttu-id="6f654-116">将在其中生成该模块的程序集引用的程序集具有授予友元程序集访问权限。</span><span class="sxs-lookup"><span data-stu-id="6f654-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="6f654-117">有关创建模块的详细信息，请参阅[/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)。</span><span class="sxs-lookup"><span data-stu-id="6f654-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="6f654-118">有关友元程序集的详细信息，请参阅[友元程序集](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="6f654-118">For more information about friend assemblies, see [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f654-119">`-moduleassemblyname`选项不是可从 Visual Studio 开发环境中; 它是可仅在编译时从命令提示符。</span><span class="sxs-lookup"><span data-stu-id="6f654-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f654-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f654-120">See Also</span></span>  
 [<span data-ttu-id="6f654-121">如何：生成多文件程序集</span><span class="sxs-lookup"><span data-stu-id="6f654-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [<span data-ttu-id="6f654-122">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="6f654-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="6f654-123">-目标 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f654-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="6f654-124">-main</span><span class="sxs-lookup"><span data-stu-id="6f654-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)  
 [<span data-ttu-id="6f654-125">-参考 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f654-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [<span data-ttu-id="6f654-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="6f654-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
 [<span data-ttu-id="6f654-127">程序集和全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="6f654-127">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="6f654-128">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="6f654-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="6f654-129">友元程序集</span><span class="sxs-lookup"><span data-stu-id="6f654-129">Friend Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)
