---
title: "/ quiet / |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /quiet
- quiet
dev_langs:
- VB
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
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
ms.openlocfilehash: bc21be8982fea52bf25d0bedeec2b78eee1e705f
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="quiet"></a><span data-ttu-id="3a2ee-102">/quiet</span><span class="sxs-lookup"><span data-stu-id="3a2ee-102">/quiet</span></span>
<span data-ttu-id="3a2ee-103">阻止编译器显示与语法相关的错误和警告的代码。</span><span class="sxs-lookup"><span data-stu-id="3a2ee-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a2ee-104">语法</span><span class="sxs-lookup"><span data-stu-id="3a2ee-104">Syntax</span></span>  
  
```  
/quiet  
```  
  
## <a name="remarks"></a><span data-ttu-id="3a2ee-105">备注</span><span class="sxs-lookup"><span data-stu-id="3a2ee-105">Remarks</span></span>  
 <span data-ttu-id="3a2ee-106">默认情况，`/quiet` 是无效的。</span><span class="sxs-lookup"><span data-stu-id="3a2ee-106">By default, `/quiet` is not in effect.</span></span> <span data-ttu-id="3a2ee-107">当编译器报告相关的语法错误或警告时，它还将输出源代码中的代码行。</span><span class="sxs-lookup"><span data-stu-id="3a2ee-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="3a2ee-108">对于分析编译器输出的应用程序，它可能会更方便编译器只将文本诊断输出。</span><span class="sxs-lookup"><span data-stu-id="3a2ee-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>  
  
 <span data-ttu-id="3a2ee-109">在下面的示例中，`Module1`输出包括源代码，而无需在编译时错误`/quiet`。</span><span class="sxs-lookup"><span data-stu-id="3a2ee-109">In the following example, `Module1` outputs an error that includes source code when compiled without `/quiet`.</span></span>  
  
```  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="3a2ee-110">输出：</span><span class="sxs-lookup"><span data-stu-id="3a2ee-110">Output:</span></span>  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
 `x`  
  
 `~`  
  
 <span data-ttu-id="3a2ee-111">使用编译`/quiet`，编译器只输出如下︰</span><span class="sxs-lookup"><span data-stu-id="3a2ee-111">Compiled with `/quiet`, the compiler outputs only the following:</span></span>  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  <span data-ttu-id="3a2ee-112">`/quiet`选项不是在 Visual Studio 开发环境中可用; 只有当从命令行进行编译，它才可用。</span><span class="sxs-lookup"><span data-stu-id="3a2ee-112">The `/quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a2ee-113">示例</span><span class="sxs-lookup"><span data-stu-id="3a2ee-113">Example</span></span>  
 <span data-ttu-id="3a2ee-114">下面的代码编译`T2.vb`并且不显示的相关的语法编译器诊断的代码︰</span><span class="sxs-lookup"><span data-stu-id="3a2ee-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>  
  
```  
vbc /quiet t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a2ee-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a2ee-115">See Also</span></span>  
 <span data-ttu-id="3a2ee-116">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="3a2ee-116">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="3a2ee-117"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="3a2ee-117"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
