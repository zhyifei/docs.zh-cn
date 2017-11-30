---
title: /target
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0d9a5307970ac745b4f102d0008e64b985c00e52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="moduleassemblyname"></a><span data-ttu-id="ff48c-102">/target</span><span class="sxs-lookup"><span data-stu-id="ff48c-102">/moduleassemblyname</span></span>
<span data-ttu-id="ff48c-103">指定此模块所属程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="ff48c-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff48c-104">语法</span><span class="sxs-lookup"><span data-stu-id="ff48c-104">Syntax</span></span>  
  
```  
/moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="ff48c-105">参数</span><span class="sxs-lookup"><span data-stu-id="ff48c-105">Arguments</span></span>  
  
|<span data-ttu-id="ff48c-106">术语</span><span class="sxs-lookup"><span data-stu-id="ff48c-106">Term</span></span>|<span data-ttu-id="ff48c-107">定义</span><span class="sxs-lookup"><span data-stu-id="ff48c-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="ff48c-108">此模块的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="ff48c-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff48c-109">备注</span><span class="sxs-lookup"><span data-stu-id="ff48c-109">Remarks</span></span>  
 <span data-ttu-id="ff48c-110">编译器进程`/moduleassemblyname`选项仅当`/target:module`指定选项。</span><span class="sxs-lookup"><span data-stu-id="ff48c-110">The compiler processes the `/moduleassemblyname` option only if the `/target:module` option has been specified.</span></span> <span data-ttu-id="ff48c-111">这将导致编译器创建的模块。</span><span class="sxs-lookup"><span data-stu-id="ff48c-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="ff48c-112">由编译器创建的模块是仅对与指定的程序集有效`/moduleassemblyname`选项。</span><span class="sxs-lookup"><span data-stu-id="ff48c-112">The module created by the compiler is valid only for the assembly specified with the `/moduleassemblyname` option.</span></span> <span data-ttu-id="ff48c-113">如果将模块放在不同的程序集时，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="ff48c-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="ff48c-114">`/moduleassemblyname`仅当满足以下条件时，才需要选项：</span><span class="sxs-lookup"><span data-stu-id="ff48c-114">The `/moduleassemblyname` option is needed only when the following are true:</span></span>  
  
-   <span data-ttu-id="ff48c-115">模块中的数据类型需要访问`Friend`引用的程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="ff48c-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
-   <span data-ttu-id="ff48c-116">引用的程序集具有友元程序集访问权限授予将在其中生成该模块的程序集。</span><span class="sxs-lookup"><span data-stu-id="ff48c-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="ff48c-117">有关创建模块的详细信息，请参阅[/target (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/target.md)。</span><span class="sxs-lookup"><span data-stu-id="ff48c-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="ff48c-118">友元程序集有关的详细信息，请参阅[友元程序集](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)。</span><span class="sxs-lookup"><span data-stu-id="ff48c-118">For more information about friend assemblies, see [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff48c-119">`/moduleassemblyname`选项不是可从 Visual Studio 开发环境中; 它是可用仅编译时从命令提示符。</span><span class="sxs-lookup"><span data-stu-id="ff48c-119">The `/moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff48c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff48c-120">See Also</span></span>  
 [<span data-ttu-id="ff48c-121">如何：生成多文件程序集</span><span class="sxs-lookup"><span data-stu-id="ff48c-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [<span data-ttu-id="ff48c-122">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="ff48c-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="ff48c-123">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff48c-123">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="ff48c-124">/main</span><span class="sxs-lookup"><span data-stu-id="ff48c-124">/main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)  
 [<span data-ttu-id="ff48c-125">/reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff48c-125">/reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [<span data-ttu-id="ff48c-126">/addmodule</span><span class="sxs-lookup"><span data-stu-id="ff48c-126">/addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
 [<span data-ttu-id="ff48c-127">程序集和全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="ff48c-127">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="ff48c-128">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="ff48c-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="ff48c-129">友元程序集</span><span class="sxs-lookup"><span data-stu-id="ff48c-129">Friend Assemblies</span></span>](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)
