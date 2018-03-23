---
title: -verbose
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0523409e53a8c7ea34de7dcc24b1bce2885a183
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="-verbose"></a><span data-ttu-id="0a90b-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="0a90b-102">-verbose</span></span>
<span data-ttu-id="0a90b-103">使编译器生成详细的状态和错误消息。</span><span class="sxs-lookup"><span data-stu-id="0a90b-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a90b-104">语法</span><span class="sxs-lookup"><span data-stu-id="0a90b-104">Syntax</span></span>  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0a90b-105">自变量</span><span class="sxs-lookup"><span data-stu-id="0a90b-105">Arguments</span></span>  
 <span data-ttu-id="0a90b-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="0a90b-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="0a90b-107">可选。</span><span class="sxs-lookup"><span data-stu-id="0a90b-107">Optional.</span></span> <span data-ttu-id="0a90b-108">指定`-verbose`等同于指定`-verbose+`，这将导致编译器发出详细消息。</span><span class="sxs-lookup"><span data-stu-id="0a90b-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="0a90b-109">此选项的默认值是`-verbose-`。</span><span class="sxs-lookup"><span data-stu-id="0a90b-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a90b-110">备注</span><span class="sxs-lookup"><span data-stu-id="0a90b-110">Remarks</span></span>  
 <span data-ttu-id="0a90b-111">`-verbose`选项显示有关由编译器发出的错误总数的信息，报告正在加载哪些程序集由模块，并显示当前正在编译的文件。</span><span class="sxs-lookup"><span data-stu-id="0a90b-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a90b-112">`-verbose`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="0a90b-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a90b-113">示例</span><span class="sxs-lookup"><span data-stu-id="0a90b-113">Example</span></span>  
 <span data-ttu-id="0a90b-114">下面的代码编译`In.vb`和指示编译器显示详细状态信息。</span><span class="sxs-lookup"><span data-stu-id="0a90b-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="0a90b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a90b-115">See Also</span></span>  
 [<span data-ttu-id="0a90b-116">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="0a90b-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="0a90b-117">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="0a90b-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
