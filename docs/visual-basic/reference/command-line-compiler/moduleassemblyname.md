---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: a612a68cffd927f3e360406cca6d9daae4f66c86
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775623"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="bf305-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="bf305-102">-moduleassemblyname</span></span>
<span data-ttu-id="bf305-103">指定此模块所属程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="bf305-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf305-104">语法</span><span class="sxs-lookup"><span data-stu-id="bf305-104">Syntax</span></span>  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="bf305-105">自变量</span><span class="sxs-lookup"><span data-stu-id="bf305-105">Arguments</span></span>  
  
|<span data-ttu-id="bf305-106">术语</span><span class="sxs-lookup"><span data-stu-id="bf305-106">Term</span></span>|<span data-ttu-id="bf305-107">定义</span><span class="sxs-lookup"><span data-stu-id="bf305-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="bf305-108">此模块所属程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="bf305-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf305-109">备注</span><span class="sxs-lookup"><span data-stu-id="bf305-109">Remarks</span></span>  
 <span data-ttu-id="bf305-110">仅当指定了 `-target:module` 选项时，编译器才处理 `-moduleassemblyname` 选项。</span><span class="sxs-lookup"><span data-stu-id="bf305-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="bf305-111">这将导致编译器创建模块。</span><span class="sxs-lookup"><span data-stu-id="bf305-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="bf305-112">编译器创建的模块仅对使用 `-moduleassemblyname` 选项指定的程序集有效。</span><span class="sxs-lookup"><span data-stu-id="bf305-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="bf305-113">如果将模块放在不同的程序集中，则会发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="bf305-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="bf305-114">仅当满足以下条件时，才需要 `-moduleassemblyname` 选项：</span><span class="sxs-lookup"><span data-stu-id="bf305-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
- <span data-ttu-id="bf305-115">模块中的数据类型需要访问所引用程序集中的 `Friend` 类型。</span><span class="sxs-lookup"><span data-stu-id="bf305-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
- <span data-ttu-id="bf305-116">引用的程序集已获得友元程序集访问权限，可访问将在其中生成模块的程序集。</span><span class="sxs-lookup"><span data-stu-id="bf305-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="bf305-117">有关创建模块的详细信息，请参阅 [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)。</span><span class="sxs-lookup"><span data-stu-id="bf305-117">For more information about creating a module, see [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="bf305-118">有关友元程序集的详细信息，请参阅[友元程序集](../../../standard/assembly/friend.md)。</span><span class="sxs-lookup"><span data-stu-id="bf305-118">For more information about friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bf305-119">`-moduleassemblyname` 选项在 Visual Studio 开发环境内无法使用；仅当从命令提示符编译时才可用。</span><span class="sxs-lookup"><span data-stu-id="bf305-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf305-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf305-120">See also</span></span>

- [<span data-ttu-id="bf305-121">如何：生成单文件程序集</span><span class="sxs-lookup"><span data-stu-id="bf305-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/build-multifile-assembly.md)
- [<span data-ttu-id="bf305-122">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="bf305-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="bf305-123">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf305-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="bf305-124">-main</span><span class="sxs-lookup"><span data-stu-id="bf305-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="bf305-125">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf305-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="bf305-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="bf305-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [<span data-ttu-id="bf305-127">.NET 中的程序集</span><span class="sxs-lookup"><span data-stu-id="bf305-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="bf305-128">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="bf305-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="bf305-129">友元程序集</span><span class="sxs-lookup"><span data-stu-id="bf305-129">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
