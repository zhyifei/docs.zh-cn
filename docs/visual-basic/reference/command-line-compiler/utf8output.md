---
title: /utf8output (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 23c7c308865a6b6afb07443a42090fff3d9e2efb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="utf8output-visual-basic"></a><span data-ttu-id="9b0c8-102">/utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b0c8-102">/utf8output (Visual Basic)</span></span>
<span data-ttu-id="9b0c8-103">显示使用 UTF-8 编码的编译器输出。</span><span class="sxs-lookup"><span data-stu-id="9b0c8-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b0c8-104">语法</span><span class="sxs-lookup"><span data-stu-id="9b0c8-104">Syntax</span></span>  
  
```  
/utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="9b0c8-105">参数</span><span class="sxs-lookup"><span data-stu-id="9b0c8-105">Arguments</span></span>  
 <span data-ttu-id="9b0c8-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="9b0c8-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="9b0c8-107">可选。</span><span class="sxs-lookup"><span data-stu-id="9b0c8-107">Optional.</span></span> <span data-ttu-id="9b0c8-108">此选项的默认值是`/utf8output-`，这意味着编译器输出不使用 utf-8 编码。</span><span class="sxs-lookup"><span data-stu-id="9b0c8-108">The default for this option is `/utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="9b0c8-109">指定`/utf8output`等同于指定`/utf8output+`。</span><span class="sxs-lookup"><span data-stu-id="9b0c8-109">Specifying `/utf8output` is the same as specifying `/utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b0c8-110">备注</span><span class="sxs-lookup"><span data-stu-id="9b0c8-110">Remarks</span></span>  
 <span data-ttu-id="9b0c8-111">某些国际配置中，在编译器输出不能在控制台中正确显示。</span><span class="sxs-lookup"><span data-stu-id="9b0c8-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="9b0c8-112">在这种情况下，使用`/utf8output`和编译器输出重定向到一个文件。</span><span class="sxs-lookup"><span data-stu-id="9b0c8-112">In such situations, use `/utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b0c8-113">`/utf8output`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="9b0c8-113">The `/utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b0c8-114">示例</span><span class="sxs-lookup"><span data-stu-id="9b0c8-114">Example</span></span>  
 <span data-ttu-id="9b0c8-115">下面的代码编译`In.vb`和指示编译器显示输出使用 utf-8 编码。</span><span class="sxs-lookup"><span data-stu-id="9b0c8-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```  
vbc /utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b0c8-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b0c8-116">See Also</span></span>  
 [<span data-ttu-id="9b0c8-117">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="9b0c8-117">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="9b0c8-118">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="9b0c8-118">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
