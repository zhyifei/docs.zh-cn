---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: f6d896fb0d41a8fa3ed613d29bc3fca2bd14cc5e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832784"
---
# <a name="-verbose"></a><span data-ttu-id="c9cbd-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="c9cbd-102">-verbose</span></span>
<span data-ttu-id="c9cbd-103">会导致编译器生成详细的状态和错误消息。</span><span class="sxs-lookup"><span data-stu-id="c9cbd-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9cbd-104">语法</span><span class="sxs-lookup"><span data-stu-id="c9cbd-104">Syntax</span></span>  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c9cbd-105">自变量</span><span class="sxs-lookup"><span data-stu-id="c9cbd-105">Arguments</span></span>  
 <span data-ttu-id="c9cbd-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="c9cbd-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="c9cbd-107">可选。</span><span class="sxs-lookup"><span data-stu-id="c9cbd-107">Optional.</span></span> <span data-ttu-id="c9cbd-108">指定`-verbose`相当于将指定`-verbose+`，这将导致编译器发出详细消息。</span><span class="sxs-lookup"><span data-stu-id="c9cbd-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="c9cbd-109">此选项的默认值是`-verbose-`。</span><span class="sxs-lookup"><span data-stu-id="c9cbd-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9cbd-110">备注</span><span class="sxs-lookup"><span data-stu-id="c9cbd-110">Remarks</span></span>  
 <span data-ttu-id="c9cbd-111">`-verbose`选项显示有关由编译器发出的错误总数信息、 报告的程序集加载的模块，并显示当前正在编译的文件。</span><span class="sxs-lookup"><span data-stu-id="c9cbd-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9cbd-112">`-verbose`选项不适用于从 Visual Studio 开发环境中，仅当从命令行编译时便可。</span><span class="sxs-lookup"><span data-stu-id="c9cbd-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9cbd-113">示例</span><span class="sxs-lookup"><span data-stu-id="c9cbd-113">Example</span></span>  
 <span data-ttu-id="c9cbd-114">下面的代码编译`In.vb`并指示编译器以显示详细的状态信息。</span><span class="sxs-lookup"><span data-stu-id="c9cbd-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9cbd-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9cbd-115">See also</span></span>

- [<span data-ttu-id="c9cbd-116">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="c9cbd-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="c9cbd-117">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="c9cbd-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
