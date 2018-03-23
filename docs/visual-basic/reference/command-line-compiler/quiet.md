---
title: -quiet
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- -quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a0ed08e013f088f512ae915daa9aeb2fa6b249b0
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="-quiet"></a><span data-ttu-id="b2d6e-102">-quiet</span><span class="sxs-lookup"><span data-stu-id="b2d6e-102">-quiet</span></span>
<span data-ttu-id="b2d6e-103">阻止编译器显示与语法相关的错误和警告的代码。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2d6e-104">语法</span><span class="sxs-lookup"><span data-stu-id="b2d6e-104">Syntax</span></span>  
  
```  
-quiet  
```  
  
## <a name="remarks"></a><span data-ttu-id="b2d6e-105">备注</span><span class="sxs-lookup"><span data-stu-id="b2d6e-105">Remarks</span></span>  
 <span data-ttu-id="b2d6e-106">默认情况，`-quiet` 是无效的。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-106">By default, `-quiet` is not in effect.</span></span> <span data-ttu-id="b2d6e-107">当编译器报告与语法相关的错误或警告时，它还将输出从源代码行。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="b2d6e-108">对于应用程序分析编译器输出，它可能会更方便编译器输出的诊断的文本。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>  
  
 <span data-ttu-id="b2d6e-109">在下面的示例中，`Module1`输出包括源代码，而无需在编译时错误`-quiet`。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-109">In the following example, `Module1` outputs an error that includes source code when compiled without `-quiet`.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="b2d6e-110">输出：</span><span class="sxs-lookup"><span data-stu-id="b2d6e-110">Output:</span></span>  
 
```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
``` 
 <span data-ttu-id="b2d6e-111">使用编译`-quiet`，则编译器输出仅如下：</span><span class="sxs-lookup"><span data-stu-id="b2d6e-111">Compiled with `-quiet`, the compiler outputs only the following:</span></span>  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  <span data-ttu-id="b2d6e-112">`-quiet`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="b2d6e-112">The `-quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2d6e-113">示例</span><span class="sxs-lookup"><span data-stu-id="b2d6e-113">Example</span></span>  
 <span data-ttu-id="b2d6e-114">下面的代码编译`T2.vb`并且不显示与语法相关编译器诊断的代码：</span><span class="sxs-lookup"><span data-stu-id="b2d6e-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>  
  
```  
vbc -quiet t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2d6e-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2d6e-115">See Also</span></span>  
 [<span data-ttu-id="b2d6e-116">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="b2d6e-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="b2d6e-117">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="b2d6e-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
