---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: dc4c0336c8a67a1b4e70f71ba5f5406da1fbb2ff
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972379"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="8ec7f-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="8ec7f-102">-moduleassemblyname</span></span>
<span data-ttu-id="8ec7f-103">指定此模块所属程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="8ec7f-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ec7f-104">语法</span><span class="sxs-lookup"><span data-stu-id="8ec7f-104">Syntax</span></span>  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="8ec7f-105">自变量</span><span class="sxs-lookup"><span data-stu-id="8ec7f-105">Arguments</span></span>  
  
|<span data-ttu-id="8ec7f-106">术语</span><span class="sxs-lookup"><span data-stu-id="8ec7f-106">Term</span></span>|<span data-ttu-id="8ec7f-107">定义</span><span class="sxs-lookup"><span data-stu-id="8ec7f-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="8ec7f-108">此模块所属的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="8ec7f-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ec7f-109">备注</span><span class="sxs-lookup"><span data-stu-id="8ec7f-109">Remarks</span></span>  
 <span data-ttu-id="8ec7f-110">`-moduleassemblyname` 仅`-target:module`当指定了选项时，编译器才会处理该选项。</span><span class="sxs-lookup"><span data-stu-id="8ec7f-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="8ec7f-111">这将导致编译器创建模块。</span><span class="sxs-lookup"><span data-stu-id="8ec7f-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="8ec7f-112">编译器创建的模块仅对使用`-moduleassemblyname`选项指定的程序集有效。</span><span class="sxs-lookup"><span data-stu-id="8ec7f-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="8ec7f-113">如果将模块放在不同的程序集中，则会发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="8ec7f-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="8ec7f-114">仅当满足以下条件时才需要选项：`-moduleassemblyname`</span><span class="sxs-lookup"><span data-stu-id="8ec7f-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
- <span data-ttu-id="8ec7f-115">模块中的数据类型需要访问引用程序集中`Friend`的类型。</span><span class="sxs-lookup"><span data-stu-id="8ec7f-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
- <span data-ttu-id="8ec7f-116">引用的程序集已向要在其中生成模块的程序集授予友元程序集访问权限。</span><span class="sxs-lookup"><span data-stu-id="8ec7f-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="8ec7f-117">有关创建模块的详细信息，请参阅[/target （Visual Basic）](../../../visual-basic/reference/command-line-compiler/target.md)。</span><span class="sxs-lookup"><span data-stu-id="8ec7f-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="8ec7f-118">有关友元程序集的详细信息，请参阅[友元程序集](../../../standard/assembly/friend.md)。</span><span class="sxs-lookup"><span data-stu-id="8ec7f-118">For more information about friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8ec7f-119">此`-moduleassemblyname`选项在 Visual Studio 开发环境中不可用; 它仅在从命令提示符编译时可用。</span><span class="sxs-lookup"><span data-stu-id="8ec7f-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ec7f-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ec7f-120">See also</span></span>

- [<span data-ttu-id="8ec7f-121">如何：生成单文件程序集</span><span class="sxs-lookup"><span data-stu-id="8ec7f-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/build-multifile-assembly.md)
- [<span data-ttu-id="8ec7f-122">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="8ec7f-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="8ec7f-123">-target （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="8ec7f-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="8ec7f-124">-main</span><span class="sxs-lookup"><span data-stu-id="8ec7f-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="8ec7f-125">-reference （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="8ec7f-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="8ec7f-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="8ec7f-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [<span data-ttu-id="8ec7f-127">.NET 中的程序集</span><span class="sxs-lookup"><span data-stu-id="8ec7f-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="8ec7f-128">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="8ec7f-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="8ec7f-129">友元程序集</span><span class="sxs-lookup"><span data-stu-id="8ec7f-129">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
