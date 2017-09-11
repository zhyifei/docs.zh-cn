---
title: "/moduleassemblyname |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
caps.latest.revision: 16
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
ms.openlocfilehash: 6852b8a0d9874fd65e93cdd9507fe9b7119ce5b3
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="moduleassemblyname"></a><span data-ttu-id="2f48b-102">/target</span><span class="sxs-lookup"><span data-stu-id="2f48b-102">/moduleassemblyname</span></span>
<span data-ttu-id="2f48b-103">指定此模块所属程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="2f48b-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f48b-104">语法</span><span class="sxs-lookup"><span data-stu-id="2f48b-104">Syntax</span></span>  
  
```  
/moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="2f48b-105">参数</span><span class="sxs-lookup"><span data-stu-id="2f48b-105">Arguments</span></span>  
  
|<span data-ttu-id="2f48b-106">术语</span><span class="sxs-lookup"><span data-stu-id="2f48b-106">Term</span></span>|<span data-ttu-id="2f48b-107">定义</span><span class="sxs-lookup"><span data-stu-id="2f48b-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="2f48b-108">此模块的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="2f48b-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f48b-109">备注</span><span class="sxs-lookup"><span data-stu-id="2f48b-109">Remarks</span></span>  
 <span data-ttu-id="2f48b-110">编译器进程`/moduleassemblyname`选项仅当`/target:module`指定选项。</span><span class="sxs-lookup"><span data-stu-id="2f48b-110">The compiler processes the `/moduleassemblyname` option only if the `/target:module` option has been specified.</span></span> <span data-ttu-id="2f48b-111">这将导致编译器需要创建一个模块。</span><span class="sxs-lookup"><span data-stu-id="2f48b-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="2f48b-112">由编译器创建的模块是仅对与指定的程序集的有效`/moduleassemblyname`选项。</span><span class="sxs-lookup"><span data-stu-id="2f48b-112">The module created by the compiler is valid only for the assembly specified with the `/moduleassemblyname` option.</span></span> <span data-ttu-id="2f48b-113">如果将模块放在另一个程序集时，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="2f48b-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="2f48b-114">`/moduleassemblyname`选项仅当满足以下条件时，才需要︰</span><span class="sxs-lookup"><span data-stu-id="2f48b-114">The `/moduleassemblyname` option is needed only when the following are true:</span></span>  
  
-   <span data-ttu-id="2f48b-115">该模块中的数据类型需要访问`Friend`引用的程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="2f48b-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
-   <span data-ttu-id="2f48b-116">引用的程序集具有友元程序集访问权限授予该模块将生成到其中的程序集。</span><span class="sxs-lookup"><span data-stu-id="2f48b-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="2f48b-117">有关创建模块的详细信息，请参阅[/target (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/target.md)。</span><span class="sxs-lookup"><span data-stu-id="2f48b-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="2f48b-118">有关友元程序集的详细信息，请参阅[友元程序集](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)。</span><span class="sxs-lookup"><span data-stu-id="2f48b-118">For more information about friend assemblies, see [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f48b-119">`/moduleassemblyname`选项不是在 Visual Studio 开发环境中可用; 该功能仅在您编译时从命令提示符。</span><span class="sxs-lookup"><span data-stu-id="2f48b-119">The `/moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f48b-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f48b-120">See Also</span></span>  
 <span data-ttu-id="2f48b-121">[如何︰ 生成多文件程序集](http://msdn.microsoft.com/library/261c5583-8a76-412d-bda7-9b8ee3b131e5) </span><span class="sxs-lookup"><span data-stu-id="2f48b-121">[How to: Build a Multifile Assembly](http://msdn.microsoft.com/library/261c5583-8a76-412d-bda7-9b8ee3b131e5) </span></span>  
<span data-ttu-id="2f48b-122"> [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="2f48b-122"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="2f48b-123"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="2f48b-123"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="2f48b-124"> [/main](../../../visual-basic/reference/command-line-compiler/main.md) </span><span class="sxs-lookup"><span data-stu-id="2f48b-124"> [/main](../../../visual-basic/reference/command-line-compiler/main.md) </span></span>  
<span data-ttu-id="2f48b-125"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span><span class="sxs-lookup"><span data-stu-id="2f48b-125"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span></span>  
<span data-ttu-id="2f48b-126"> [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) </span><span class="sxs-lookup"><span data-stu-id="2f48b-126"> [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) </span></span>  
<span data-ttu-id="2f48b-127"> [程序集和全局程序集缓存](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="2f48b-127"> [Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="2f48b-128"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="2f48b-128"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="2f48b-129"> [友元程序集](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)</span><span class="sxs-lookup"><span data-stu-id="2f48b-129"> [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)</span></span>
