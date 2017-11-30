---
title: "@（指定响应文件）(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ced258713983ded06fa70cb65d56071b41cdc75b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-specify-response-file-visual-basic"></a><span data-ttu-id="627fa-102">@（指定响应文件）(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="627fa-102">@ (Specify Response File) (Visual Basic)</span></span>
<span data-ttu-id="627fa-103">指定包含编译器选项的文件和要编译的源代码文件。</span><span class="sxs-lookup"><span data-stu-id="627fa-103">Specifies a file that contains compiler options and source-code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="627fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="627fa-104">Syntax</span></span>  
  
```  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="627fa-105">参数</span><span class="sxs-lookup"><span data-stu-id="627fa-105">Arguments</span></span>  
 `response_file`  
 <span data-ttu-id="627fa-106">必需。</span><span class="sxs-lookup"><span data-stu-id="627fa-106">Required.</span></span> <span data-ttu-id="627fa-107">列出编译器选项或要编译的源代码文件的文件。</span><span class="sxs-lookup"><span data-stu-id="627fa-107">A file that lists compiler options or source-code files to compile.</span></span> <span data-ttu-id="627fa-108">将文件名括在双引号 ("") 如果它包含空格。</span><span class="sxs-lookup"><span data-stu-id="627fa-108">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="627fa-109">备注</span><span class="sxs-lookup"><span data-stu-id="627fa-109">Remarks</span></span>  
 <span data-ttu-id="627fa-110">编译器处理的编译器选项和源代码文件的响应文件中指定，如同它们已在命令行上指定的一样。</span><span class="sxs-lookup"><span data-stu-id="627fa-110">The compiler processes the compiler options and source-code files specified in a response file as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="627fa-111">若要指定多个响应文件在编译中，指定响应文件中的多个选项，如下所示。</span><span class="sxs-lookup"><span data-stu-id="627fa-111">To specify more than one response file in a compilation, specify multiple response-file options, such as the following.</span></span>  
  
```  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="627fa-112">在响应文件、 多个编译器选项和源代码文件可以出现在同一行中。</span><span class="sxs-lookup"><span data-stu-id="627fa-112">In a response file, multiple compiler options and source-code files can appear on one line.</span></span> <span data-ttu-id="627fa-113">单个的编译器选项规范必须出现在同一行中 （不能跨越多个行）。</span><span class="sxs-lookup"><span data-stu-id="627fa-113">A single compiler-option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="627fa-114">响应文件可以具有开头的注释`#`符号。</span><span class="sxs-lookup"><span data-stu-id="627fa-114">Response files can have comments that begin with the `#` symbol.</span></span>  
  
 <span data-ttu-id="627fa-115">你可以组合与在一个或多个响应文件中指定的选项一起指定命令行上的选项。</span><span class="sxs-lookup"><span data-stu-id="627fa-115">You can combine options specified on the command line with options specified in one or more response files.</span></span> <span data-ttu-id="627fa-116">编译器处理的命令选项，当它遇到它们。</span><span class="sxs-lookup"><span data-stu-id="627fa-116">The compiler processes the command options as it encounters them.</span></span> <span data-ttu-id="627fa-117">因此，命令行自变量可以重写以前列出的响应文件中的选项。</span><span class="sxs-lookup"><span data-stu-id="627fa-117">Therefore, command-line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="627fa-118">相反，响应文件中的选项将覆盖前面列出的命令行上或其他响应文件中的选项。</span><span class="sxs-lookup"><span data-stu-id="627fa-118">Conversely, options in a response file override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="627fa-119">Visual Basic 提供 Vbc.rsp 文件，它位于 Vbc.exe 文件所在的同一目录中。</span><span class="sxs-lookup"><span data-stu-id="627fa-119">Visual Basic provides the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="627fa-120">默认情况下，包含 Vbc.rsp 文件，除非`/noconfig`使用选项。</span><span class="sxs-lookup"><span data-stu-id="627fa-120">The Vbc.rsp file is included by default, unless the `/noconfig` option is used.</span></span> <span data-ttu-id="627fa-121">有关详细信息，请参阅[/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)。</span><span class="sxs-lookup"><span data-stu-id="627fa-121">For more information, see [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="627fa-122">`@`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="627fa-122">The `@` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="627fa-123">示例</span><span class="sxs-lookup"><span data-stu-id="627fa-123">Example</span></span>  
 <span data-ttu-id="627fa-124">下面的行是从示例响应文件。</span><span class="sxs-lookup"><span data-stu-id="627fa-124">The following lines are from a sample response file.</span></span>  
  
```  
# build the first output file  
/target:exe   
/out:MyExe.exe  
source1.vb   
source2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="627fa-125">示例</span><span class="sxs-lookup"><span data-stu-id="627fa-125">Example</span></span>  
 <span data-ttu-id="627fa-126">下面的示例演示如何使用`@`与名为的响应文件的选项`File1.rsp`。</span><span class="sxs-lookup"><span data-stu-id="627fa-126">The following example demonstrates how to use the `@` option with the response file named `File1.rsp`.</span></span>  
  
```  
vbc @file1.rsp  
```  
  
## <a name="see-also"></a><span data-ttu-id="627fa-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="627fa-127">See Also</span></span>  
 [<span data-ttu-id="627fa-128">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="627fa-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="627fa-129">/noconfig</span><span class="sxs-lookup"><span data-stu-id="627fa-129">/noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [<span data-ttu-id="627fa-130">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="627fa-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
