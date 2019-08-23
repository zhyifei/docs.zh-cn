---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 789df84bb4011d1ad128c50a9c689d1217be6694
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937276"
---
# <a name="-utf8output-visual-basic"></a><span data-ttu-id="ae504-102">-utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae504-102">-utf8output (Visual Basic)</span></span>
<span data-ttu-id="ae504-103">显示使用 UTF-8 编码的编译器输出。</span><span class="sxs-lookup"><span data-stu-id="ae504-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae504-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae504-104">Syntax</span></span>  
  
```  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="ae504-105">自变量</span><span class="sxs-lookup"><span data-stu-id="ae504-105">Arguments</span></span>  
 <span data-ttu-id="ae504-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="ae504-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="ae504-107">可选。</span><span class="sxs-lookup"><span data-stu-id="ae504-107">Optional.</span></span> <span data-ttu-id="ae504-108">此选项的默认值为`-utf8output-`, 这意味着编译器输出不使用 utf-8 编码。</span><span class="sxs-lookup"><span data-stu-id="ae504-108">The default for this option is `-utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="ae504-109">指定 `-utf8output` 与指定 `-utf8output+` 相同。</span><span class="sxs-lookup"><span data-stu-id="ae504-109">Specifying `-utf8output` is the same as specifying `-utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae504-110">备注</span><span class="sxs-lookup"><span data-stu-id="ae504-110">Remarks</span></span>  
 <span data-ttu-id="ae504-111">在某些国际化配置中, 无法在控制台中正确显示编译器输出。</span><span class="sxs-lookup"><span data-stu-id="ae504-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="ae504-112">在这种情况下`-utf8output` , 请使用并将编译器输出重定向到文件。</span><span class="sxs-lookup"><span data-stu-id="ae504-112">In such situations, use `-utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ae504-113">此`-utf8output`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。</span><span class="sxs-lookup"><span data-stu-id="ae504-113">The `-utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae504-114">示例</span><span class="sxs-lookup"><span data-stu-id="ae504-114">Example</span></span>  
 <span data-ttu-id="ae504-115">下面的代码将`In.vb`编译并指示编译器使用 utf-8 编码显示输出。</span><span class="sxs-lookup"><span data-stu-id="ae504-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae504-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae504-116">See also</span></span>

- [<span data-ttu-id="ae504-117">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="ae504-117">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="ae504-118">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="ae504-118">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
