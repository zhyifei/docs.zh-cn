---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 5b3899462af7c4aa8e0f77377a8d7485975f9867
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937263"
---
# <a name="-verbose"></a><span data-ttu-id="b042c-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="b042c-102">-verbose</span></span>
<span data-ttu-id="b042c-103">导致编译器生成详细的状态和错误消息。</span><span class="sxs-lookup"><span data-stu-id="b042c-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b042c-104">语法</span><span class="sxs-lookup"><span data-stu-id="b042c-104">Syntax</span></span>  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="b042c-105">自变量</span><span class="sxs-lookup"><span data-stu-id="b042c-105">Arguments</span></span>  
 <span data-ttu-id="b042c-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="b042c-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="b042c-107">可选。</span><span class="sxs-lookup"><span data-stu-id="b042c-107">Optional.</span></span> <span data-ttu-id="b042c-108">指定`-verbose`与指定`-verbose+`的相同, 这将导致编译器发出详细消息。</span><span class="sxs-lookup"><span data-stu-id="b042c-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="b042c-109">此选项的默认值为`-verbose-`。</span><span class="sxs-lookup"><span data-stu-id="b042c-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b042c-110">备注</span><span class="sxs-lookup"><span data-stu-id="b042c-110">Remarks</span></span>  
 <span data-ttu-id="b042c-111">`-verbose`选项显示编译器发出的错误总数的相关信息, 报告模块正在加载哪些程序集, 并显示当前正在编译的文件。</span><span class="sxs-lookup"><span data-stu-id="b042c-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b042c-112">此`-verbose`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。</span><span class="sxs-lookup"><span data-stu-id="b042c-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b042c-113">示例</span><span class="sxs-lookup"><span data-stu-id="b042c-113">Example</span></span>  
 <span data-ttu-id="b042c-114">下面的代码将`In.vb`编译并指示编译器显示详细状态信息。</span><span class="sxs-lookup"><span data-stu-id="b042c-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b042c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="b042c-115">See also</span></span>

- [<span data-ttu-id="b042c-116">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="b042c-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="b042c-117">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="b042c-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
