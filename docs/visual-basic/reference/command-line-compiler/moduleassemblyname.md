---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 70cef109e4f2947fb4e38b9bfd19433257cce136
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663511"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="0fd21-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="0fd21-102">-moduleassemblyname</span></span>
<span data-ttu-id="0fd21-103">指定此模块所属程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="0fd21-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fd21-104">语法</span><span class="sxs-lookup"><span data-stu-id="0fd21-104">Syntax</span></span>  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="0fd21-105">自变量</span><span class="sxs-lookup"><span data-stu-id="0fd21-105">Arguments</span></span>  
  
|<span data-ttu-id="0fd21-106">术语</span><span class="sxs-lookup"><span data-stu-id="0fd21-106">Term</span></span>|<span data-ttu-id="0fd21-107">定义</span><span class="sxs-lookup"><span data-stu-id="0fd21-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="0fd21-108">此模块的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="0fd21-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0fd21-109">备注</span><span class="sxs-lookup"><span data-stu-id="0fd21-109">Remarks</span></span>  
 <span data-ttu-id="0fd21-110">编译器进程`-moduleassemblyname`选项仅当`-target:module`指定选项。</span><span class="sxs-lookup"><span data-stu-id="0fd21-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="0fd21-111">这将导致编译器创建一个模块。</span><span class="sxs-lookup"><span data-stu-id="0fd21-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="0fd21-112">由编译器创建的模块是仅对与指定的程序集的有效`-moduleassemblyname`选项。</span><span class="sxs-lookup"><span data-stu-id="0fd21-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="0fd21-113">如果将模块置于不同的程序集，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="0fd21-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="0fd21-114">`-moduleassemblyname`选项仅当满足以下条件时，才需要：</span><span class="sxs-lookup"><span data-stu-id="0fd21-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
- <span data-ttu-id="0fd21-115">该模块中的数据类型需要有权`Friend`中引用的程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="0fd21-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
- <span data-ttu-id="0fd21-116">将在其中生成该模块的程序集引用的程序集具有授予友元程序集访问权限。</span><span class="sxs-lookup"><span data-stu-id="0fd21-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="0fd21-117">有关创建模块的详细信息，请参阅[/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)。</span><span class="sxs-lookup"><span data-stu-id="0fd21-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="0fd21-118">有关友元程序集的详细信息，请参阅[友元程序集](../../../standard/assembly/friend-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="0fd21-118">For more information about friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fd21-119">`-moduleassemblyname`选项不是可从 Visual Studio 开发环境中; 它是可仅在编译时从命令提示符。</span><span class="sxs-lookup"><span data-stu-id="0fd21-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fd21-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="0fd21-120">See also</span></span>

- [<span data-ttu-id="0fd21-121">如何：生成单文件程序集</span><span class="sxs-lookup"><span data-stu-id="0fd21-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
- [<span data-ttu-id="0fd21-122">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="0fd21-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="0fd21-123">-目标 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0fd21-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="0fd21-124">-main</span><span class="sxs-lookup"><span data-stu-id="0fd21-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="0fd21-125">-参考 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0fd21-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="0fd21-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="0fd21-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [<span data-ttu-id="0fd21-127">.NET 中的程序集</span><span class="sxs-lookup"><span data-stu-id="0fd21-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="0fd21-128">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="0fd21-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="0fd21-129">友元程序集</span><span class="sxs-lookup"><span data-stu-id="0fd21-129">Friend Assemblies</span></span>](../../../standard/assembly/friend-assemblies.md)
