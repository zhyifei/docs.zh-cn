---
title: -netcf
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82a0adc9e821df3a789cf19e798d4bad9e9a69e3
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="-netcf"></a><span data-ttu-id="d3032-102">-netcf</span><span class="sxs-lookup"><span data-stu-id="d3032-102">-netcf</span></span>
<span data-ttu-id="d3032-103">设置编译器从而以 [!INCLUDE[Compact](~/includes/compact-md.md)] 为目标。</span><span class="sxs-lookup"><span data-stu-id="d3032-103">Sets the compiler to target the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3032-104">语法</span><span class="sxs-lookup"><span data-stu-id="d3032-104">Syntax</span></span>  
  
```  
-netcf  
```  
  
## <a name="remarks"></a><span data-ttu-id="d3032-105">备注</span><span class="sxs-lookup"><span data-stu-id="d3032-105">Remarks</span></span>  
 <span data-ttu-id="d3032-106">`-netcf`选项使[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]编译器将编译目标[!INCLUDE[Compact](~/includes/compact-md.md)]而不是完整[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d3032-106">The `-netcf` option causes the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler to target the [!INCLUDE[Compact](~/includes/compact-md.md)] rather than the full [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="d3032-107">仅存在于完整的语言功能[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="d3032-107">Language functionality that is present only in the full [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] is disabled.</span></span>  
  
 <span data-ttu-id="d3032-108">`-netcf`选项旨在用于[-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)。</span><span class="sxs-lookup"><span data-stu-id="d3032-108">The `-netcf` option is designed to be used with [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="d3032-109">通过禁用的语言功能`-netcf`是相同的语言功能和目标的文件中不存在`-sdkpath`。</span><span class="sxs-lookup"><span data-stu-id="d3032-109">The language features disabled by `-netcf` are the same language features not present in the files targeted with `-sdkpath`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3032-110">`-netcf`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="d3032-110">The `-netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="d3032-111">`-netcf`时会设置选项[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]加载设备项目。</span><span class="sxs-lookup"><span data-stu-id="d3032-111">The `-netcf` option is set when a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] device project is loaded.</span></span>  
  
 <span data-ttu-id="d3032-112">`-netcf`选项更改下列语言功能：</span><span class="sxs-lookup"><span data-stu-id="d3032-112">The `-netcf` option changes the following language features:</span></span>  
  
-   <span data-ttu-id="d3032-113">[结束\<关键字 > 语句](../../../visual-basic/language-reference/statements/end-keyword-statement.md)关键字，终止执行程序，已禁用。</span><span class="sxs-lookup"><span data-stu-id="d3032-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="d3032-114">下面的程序不编译和运行`-netcf`但在编译时进行故障`-netcf`。</span><span class="sxs-lookup"><span data-stu-id="d3032-114">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>  
  
     [!code-vb[VbVbalrCompiler#34](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]  
  
-   <span data-ttu-id="d3032-115">后期绑定，在所有窗体中处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="d3032-115">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="d3032-116">遇到识别后期绑定方案时，将产生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="d3032-116">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="d3032-117">下面的程序不编译和运行`-netcf`但在编译时进行故障`-netcf`。</span><span class="sxs-lookup"><span data-stu-id="d3032-117">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>  
  
     [!code-vb[VbVbalrCompiler#35](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]  
  
-   <span data-ttu-id="d3032-118">[自动](../../../visual-basic/language-reference/modifiers/auto.md)， [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)，和[Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)修饰符处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="d3032-118">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="d3032-119">语法[声明语句](../../../visual-basic/language-reference/statements/declare-statement.md)语句也被修改为`Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`。</span><span class="sxs-lookup"><span data-stu-id="d3032-119">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) statement is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="d3032-120">下面的代码演示的效果`-netcf`上一次编译。</span><span class="sxs-lookup"><span data-stu-id="d3032-120">The following code shows the effect of `-netcf` on a compilation.</span></span>  
  
     [!code-vb[VbVbalrCompiler#36](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]  
  
-   <span data-ttu-id="d3032-121">使用 Visual Basic 6.0 关键字已从删除[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]生成一个不同的错误时`-netcf`使用。</span><span class="sxs-lookup"><span data-stu-id="d3032-121">Using Visual Basic 6.0 keywords that were removed from [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] generates a different error when `-netcf` is used.</span></span> <span data-ttu-id="d3032-122">这会影响以下关键字的错误消息：</span><span class="sxs-lookup"><span data-stu-id="d3032-122">This affects the error messages for the following keywords:</span></span>  
  
    -   `Open`  
  
    -   `Close`  
  
    -   `Put`  
  
    -   `Print`  
  
    -   `Write`  
  
    -   `Input`  
  
    -   `Lock`  
  
    -   `Unlock`  
  
    -   `Seek`  
  
    -   `Width`  
  
    -   `Name`  
  
    -   `FreeFile`  
  
    -   `EOF`  
  
    -   `Loc`  
  
    -   `LOF`  
  
    -   `Line`  
  
## <a name="example"></a><span data-ttu-id="d3032-123">示例</span><span class="sxs-lookup"><span data-stu-id="d3032-123">Example</span></span>  
 <span data-ttu-id="d3032-124">下面的代码编译`Myfile.vb`与[!INCLUDE[Compact](~/includes/compact-md.md)]，使用版本的 mscorlib.dll 和 Microsoft.VisualBasic.dll 的默认安装目录中找到[!INCLUDE[Compact](~/includes/compact-md.md)]C 驱动器上。</span><span class="sxs-lookup"><span data-stu-id="d3032-124">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](~/includes/compact-md.md)], using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](~/includes/compact-md.md)] on the C drive.</span></span> <span data-ttu-id="d3032-125">通常情况下，将使用的最新版本[!INCLUDE[Compact](~/includes/compact-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d3032-125">Typically, you would use the most recent version of the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
```console  
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3032-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3032-126">See Also</span></span>  
 [<span data-ttu-id="d3032-127">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="d3032-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="d3032-128">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="d3032-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="d3032-129">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="d3032-129">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
