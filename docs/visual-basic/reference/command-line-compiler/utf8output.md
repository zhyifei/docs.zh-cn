---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 753c92cdf2124ee7fb1b471c7bc543b6db6f3daa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653580"
---
# <a name="-utf8output-visual-basic"></a><span data-ttu-id="4ca6f-102">-utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ca6f-102">-utf8output (Visual Basic)</span></span>
<span data-ttu-id="4ca6f-103">显示使用 UTF-8 编码的编译器输出。</span><span class="sxs-lookup"><span data-stu-id="4ca6f-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ca6f-104">语法</span><span class="sxs-lookup"><span data-stu-id="4ca6f-104">Syntax</span></span>  
  
```  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="4ca6f-105">自变量</span><span class="sxs-lookup"><span data-stu-id="4ca6f-105">Arguments</span></span>  
 <span data-ttu-id="4ca6f-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="4ca6f-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="4ca6f-107">可选。</span><span class="sxs-lookup"><span data-stu-id="4ca6f-107">Optional.</span></span> <span data-ttu-id="4ca6f-108">此选项的默认值是`-utf8output-`，这意味着编译器输出不使用 utf-8 编码。</span><span class="sxs-lookup"><span data-stu-id="4ca6f-108">The default for this option is `-utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="4ca6f-109">指定`-utf8output`等同于指定`-utf8output+`。</span><span class="sxs-lookup"><span data-stu-id="4ca6f-109">Specifying `-utf8output` is the same as specifying `-utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ca6f-110">备注</span><span class="sxs-lookup"><span data-stu-id="4ca6f-110">Remarks</span></span>  
 <span data-ttu-id="4ca6f-111">某些国际配置中，在编译器输出不能在控制台中正确显示。</span><span class="sxs-lookup"><span data-stu-id="4ca6f-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="4ca6f-112">在这种情况下，使用`-utf8output`和编译器输出重定向到一个文件。</span><span class="sxs-lookup"><span data-stu-id="4ca6f-112">In such situations, use `-utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ca6f-113">`-utf8output`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="4ca6f-113">The `-utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ca6f-114">示例</span><span class="sxs-lookup"><span data-stu-id="4ca6f-114">Example</span></span>  
 <span data-ttu-id="4ca6f-115">下面的代码编译`In.vb`和指示编译器显示输出使用 utf-8 编码。</span><span class="sxs-lookup"><span data-stu-id="4ca6f-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ca6f-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ca6f-116">See Also</span></span>  
 [<span data-ttu-id="4ca6f-117">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="4ca6f-117">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="4ca6f-118">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="4ca6f-118">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
