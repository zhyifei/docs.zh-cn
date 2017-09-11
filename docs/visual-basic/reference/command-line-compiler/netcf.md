---
title: "/netcf |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /netcf
- netcf
dev_langs:
- VB
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
caps.latest.revision: 18
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
ms.openlocfilehash: 375ec79fe2bf63bc03988ecaad877eb27f43d55b
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="netcf"></a><span data-ttu-id="add9e-102">/netcf</span><span class="sxs-lookup"><span data-stu-id="add9e-102">/netcf</span></span>
<span data-ttu-id="add9e-103">设置编译器从而以 [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] 为目标。</span><span class="sxs-lookup"><span data-stu-id="add9e-103">Sets the compiler to target the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="add9e-104">语法</span><span class="sxs-lookup"><span data-stu-id="add9e-104">Syntax</span></span>  
  
```  
/netcf  
```  
  
## <a name="remarks"></a><span data-ttu-id="add9e-105">备注</span><span class="sxs-lookup"><span data-stu-id="add9e-105">Remarks</span></span>  
 <span data-ttu-id="add9e-106">`/netcf`选项使[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器将编译目标[!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)]而不是完整[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="add9e-106">The `/netcf` option causes the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler to target the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] rather than the full [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span> <span data-ttu-id="add9e-107">仅存在于完整的语言功能[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]被禁用。</span><span class="sxs-lookup"><span data-stu-id="add9e-107">Language functionality that is present only in the full [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] is disabled.</span></span>  
  
 <span data-ttu-id="add9e-108">`/netcf`选项专门用于与使用[/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)。</span><span class="sxs-lookup"><span data-stu-id="add9e-108">The `/netcf` option is designed to be used with [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="add9e-109">被禁用的语言功能`/netcf`是相同的语言功能在与所针对的文件中不存在`/sdkpath`。</span><span class="sxs-lookup"><span data-stu-id="add9e-109">The language features disabled by `/netcf` are the same language features not present in the files targeted with `/sdkpath`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="add9e-110">`/netcf`选项不是在 Visual Studio 开发环境中可用; 只有当从命令行进行编译，它才可用。</span><span class="sxs-lookup"><span data-stu-id="add9e-110">The `/netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="add9e-111">`/netcf`会设置选项[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]加载设备项目。</span><span class="sxs-lookup"><span data-stu-id="add9e-111">The `/netcf` option is set when a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] device project is loaded.</span></span>  
  
 <span data-ttu-id="add9e-112">`/netcf`选项更改以下语言功能︰</span><span class="sxs-lookup"><span data-stu-id="add9e-112">The `/netcf` option changes the following language features:</span></span>  
  
-   <span data-ttu-id="add9e-113">[结束\<关键字&1;> 语句](../../../visual-basic/language-reference/statements/end-keyword-statement.md)关键字，终止程序执行时，被禁用。</span><span class="sxs-lookup"><span data-stu-id="add9e-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="add9e-114">下面的程序不编译和运行`/netcf`在编译时会失败，但`/netcf`。</span><span class="sxs-lookup"><span data-stu-id="add9e-114">The following program compiles and runs without `/netcf` but fails at compile time with `/netcf`.</span></span>  
  
     <span data-ttu-id="add9e-115">[!code-vb[VbVbalrCompiler #&34;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="add9e-115">[!code-vb[VbVbalrCompiler#34](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]</span></span>  
  
-   <span data-ttu-id="add9e-116">后期绑定，在所有表单中，处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="add9e-116">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="add9e-117">遇到可识别的后期绑定情况时，将生成编译时错误。</span><span class="sxs-lookup"><span data-stu-id="add9e-117">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="add9e-118">下面的程序不编译和运行`/netcf`在编译时会失败，但`/netcf`。</span><span class="sxs-lookup"><span data-stu-id="add9e-118">The following program compiles and runs without `/netcf` but fails at compile time with `/netcf`.</span></span>  
  
     <span data-ttu-id="add9e-119">[!code-vb[VbVbalrCompiler #&35;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="add9e-119">[!code-vb[VbVbalrCompiler#35](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]</span></span>  
  
-   <span data-ttu-id="add9e-120">[自动](../../../visual-basic/language-reference/modifiers/auto.md)， [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)，和[Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)修饰符处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="add9e-120">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="add9e-121">语法[声明语句](../../../visual-basic/language-reference/statements/declare-statement.md)语句也被修改为`Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`。</span><span class="sxs-lookup"><span data-stu-id="add9e-121">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) statement is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="add9e-122">下面的代码演示的效果`/netcf`上一次编译。</span><span class="sxs-lookup"><span data-stu-id="add9e-122">The following code shows the effect of `/netcf` on a compilation.</span></span>  
  
     <span data-ttu-id="add9e-123">[!code-vb[VbVbalrCompiler #&36;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="add9e-123">[!code-vb[VbVbalrCompiler#36](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]</span></span>  
  
-   <span data-ttu-id="add9e-124">使用已删除的 Visual Basic 6.0 关键字[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]生成不同的错误时`/netcf`使用。</span><span class="sxs-lookup"><span data-stu-id="add9e-124">Using Visual Basic 6.0 keywords that were removed from [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] generates a different error when `/netcf` is used.</span></span> <span data-ttu-id="add9e-125">这会影响以下关键字的错误消息︰</span><span class="sxs-lookup"><span data-stu-id="add9e-125">This affects the error messages for the following keywords:</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="add9e-126">示例</span><span class="sxs-lookup"><span data-stu-id="add9e-126">Example</span></span>  
 <span data-ttu-id="add9e-127">下面的代码编译`Myfile.vb`与[!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)]，使用版本的 Mscorlib.dll 和 Microsoft.VisualBasic.dll 的默认安装目录中找到[!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)]C 驱动器上。</span><span class="sxs-lookup"><span data-stu-id="add9e-127">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)], using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] on the C drive.</span></span> <span data-ttu-id="add9e-128">通常情况下，将使用的最新版本[!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="add9e-128">Typically, you would use the most recent version of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span></span>  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="add9e-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="add9e-129">See Also</span></span>  
 <span data-ttu-id="add9e-130">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="add9e-130">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="add9e-131"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="add9e-131"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="add9e-132"> [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)</span><span class="sxs-lookup"><span data-stu-id="add9e-132"> [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)</span></span>
