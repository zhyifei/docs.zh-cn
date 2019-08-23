---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 052d6937846df39bd94d532e1b63ebe522dbf6c7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964677"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="3d282-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="3d282-102">-moduleassemblyname</span></span>
<span data-ttu-id="3d282-103">指定此模块所属程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="3d282-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d282-104">语法</span><span class="sxs-lookup"><span data-stu-id="3d282-104">Syntax</span></span>  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="3d282-105">自变量</span><span class="sxs-lookup"><span data-stu-id="3d282-105">Arguments</span></span>  
  
|<span data-ttu-id="3d282-106">术语</span><span class="sxs-lookup"><span data-stu-id="3d282-106">Term</span></span>|<span data-ttu-id="3d282-107">定义</span><span class="sxs-lookup"><span data-stu-id="3d282-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="3d282-108">此模块所属的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="3d282-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d282-109">备注</span><span class="sxs-lookup"><span data-stu-id="3d282-109">Remarks</span></span>  
 <span data-ttu-id="3d282-110">`-moduleassemblyname` 仅`-target:module`当指定了选项时, 编译器才会处理该选项。</span><span class="sxs-lookup"><span data-stu-id="3d282-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="3d282-111">这将导致编译器创建模块。</span><span class="sxs-lookup"><span data-stu-id="3d282-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="3d282-112">编译器创建的模块仅对使用`-moduleassemblyname`选项指定的程序集有效。</span><span class="sxs-lookup"><span data-stu-id="3d282-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="3d282-113">如果将模块放在不同的程序集中, 则会发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="3d282-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="3d282-114">仅当满足以下条件时才需要选项:`-moduleassemblyname`</span><span class="sxs-lookup"><span data-stu-id="3d282-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
- <span data-ttu-id="3d282-115">模块中的数据类型需要访问引用程序集中`Friend`的类型。</span><span class="sxs-lookup"><span data-stu-id="3d282-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
- <span data-ttu-id="3d282-116">引用的程序集已向要在其中生成模块的程序集授予友元程序集访问权限。</span><span class="sxs-lookup"><span data-stu-id="3d282-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="3d282-117">有关创建模块的详细信息, 请参阅[/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)。</span><span class="sxs-lookup"><span data-stu-id="3d282-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="3d282-118">有关友元程序集的详细信息, 请参阅[友元程序集](../../../standard/assembly/friend-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="3d282-118">For more information about friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend-assemblies.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d282-119">此`-moduleassemblyname`选项在 Visual Studio 开发环境中不可用; 它仅在从命令提示符编译时可用。</span><span class="sxs-lookup"><span data-stu-id="3d282-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d282-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d282-120">See also</span></span>

- [<span data-ttu-id="3d282-121">如何：生成单文件程序集</span><span class="sxs-lookup"><span data-stu-id="3d282-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
- [<span data-ttu-id="3d282-122">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="3d282-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="3d282-123">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d282-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="3d282-124">-main</span><span class="sxs-lookup"><span data-stu-id="3d282-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="3d282-125">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d282-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="3d282-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="3d282-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [<span data-ttu-id="3d282-127">.NET 中的程序集</span><span class="sxs-lookup"><span data-stu-id="3d282-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="3d282-128">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="3d282-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="3d282-129">友元程序集</span><span class="sxs-lookup"><span data-stu-id="3d282-129">Friend Assemblies</span></span>](../../../standard/assembly/friend-assemblies.md)
