---
title: "/verbose |Microsoft 文档"
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
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
caps.latest.revision: 11
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
ms.openlocfilehash: 62285a727217aa897a83a9e746588c80a2c519c0
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="verbose"></a><span data-ttu-id="96137-102">/verbose</span><span class="sxs-lookup"><span data-stu-id="96137-102">/verbose</span></span>
<span data-ttu-id="96137-103">使编译器来生成详细的状态和错误消息。</span><span class="sxs-lookup"><span data-stu-id="96137-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96137-104">语法</span><span class="sxs-lookup"><span data-stu-id="96137-104">Syntax</span></span>  
  
```  
/verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="96137-105">参数</span><span class="sxs-lookup"><span data-stu-id="96137-105">Arguments</span></span>  
 <span data-ttu-id="96137-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="96137-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="96137-107">可选。</span><span class="sxs-lookup"><span data-stu-id="96137-107">Optional.</span></span> <span data-ttu-id="96137-108">指定`/verbose`相当于将指定`/verbose+`，这将导致编译器发出详细消息。</span><span class="sxs-lookup"><span data-stu-id="96137-108">Specifying `/verbose` is the same as specifying `/verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="96137-109">此选项的默认值是`/verbose-`。</span><span class="sxs-lookup"><span data-stu-id="96137-109">The default for this option is `/verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96137-110">备注</span><span class="sxs-lookup"><span data-stu-id="96137-110">Remarks</span></span>  
 <span data-ttu-id="96137-111">`/verbose`选项显示有关由编译器发出的错误总数的信息、 报告哪些程序集正在加载的模块，并显示当前正在编译的文件。</span><span class="sxs-lookup"><span data-stu-id="96137-111">The `/verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96137-112">`/verbose`选项不是在 Visual Studio 开发环境中可用; 只有当从命令行进行编译，它才可用。</span><span class="sxs-lookup"><span data-stu-id="96137-112">The `/verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96137-113">示例</span><span class="sxs-lookup"><span data-stu-id="96137-113">Example</span></span>  
 <span data-ttu-id="96137-114">下面的代码编译`In.vb`并指示编译器以显示详细的状态信息。</span><span class="sxs-lookup"><span data-stu-id="96137-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```  
vbc /verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="96137-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96137-115">See Also</span></span>  
 <span data-ttu-id="96137-116">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="96137-116">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="96137-117"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="96137-117"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
