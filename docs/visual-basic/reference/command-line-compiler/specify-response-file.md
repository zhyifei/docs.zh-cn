---
title: '@（指定响应文件）(Visual Basic)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: b84d50334e56305c27c5c0bc54578ba871a28365
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937284"
---
# <a name="-specify-response-file-visual-basic"></a><span data-ttu-id="71792-102">@（指定响应文件）(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71792-102">@ (Specify Response File) (Visual Basic)</span></span>
<span data-ttu-id="71792-103">指定包含要编译的编译器选项和源代码文件的文件。</span><span class="sxs-lookup"><span data-stu-id="71792-103">Specifies a file that contains compiler options and source-code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71792-104">语法</span><span class="sxs-lookup"><span data-stu-id="71792-104">Syntax</span></span>  
  
```  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="71792-105">自变量</span><span class="sxs-lookup"><span data-stu-id="71792-105">Arguments</span></span>  
 `response_file`  
 <span data-ttu-id="71792-106">必需。</span><span class="sxs-lookup"><span data-stu-id="71792-106">Required.</span></span> <span data-ttu-id="71792-107">列出编译器选项或要编译的源代码文件的文件。</span><span class="sxs-lookup"><span data-stu-id="71792-107">A file that lists compiler options or source-code files to compile.</span></span> <span data-ttu-id="71792-108">如果文件名包含空格, 请将文件名用引号 ("") 引起来。</span><span class="sxs-lookup"><span data-stu-id="71792-108">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71792-109">备注</span><span class="sxs-lookup"><span data-stu-id="71792-109">Remarks</span></span>  
 <span data-ttu-id="71792-110">编译器将处理在响应文件中指定的编译器选项和源代码文件, 就好像已在命令行中指定了这些选项。</span><span class="sxs-lookup"><span data-stu-id="71792-110">The compiler processes the compiler options and source-code files specified in a response file as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="71792-111">若要在编译中指定多个响应文件, 请指定多个响应文件选项, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="71792-111">To specify more than one response file in a compilation, specify multiple response-file options, such as the following.</span></span>  
  
```  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="71792-112">在响应文件中, 多个编译器选项和源代码文件可以出现在一行中。</span><span class="sxs-lookup"><span data-stu-id="71792-112">In a response file, multiple compiler options and source-code files can appear on one line.</span></span> <span data-ttu-id="71792-113">单个编译器选项规范必须出现在一行中 (不能跨多行)。</span><span class="sxs-lookup"><span data-stu-id="71792-113">A single compiler-option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="71792-114">响应文件可以包含以`#`符号开头的注释。</span><span class="sxs-lookup"><span data-stu-id="71792-114">Response files can have comments that begin with the `#` symbol.</span></span>  
  
 <span data-ttu-id="71792-115">可以将命令行上指定的选项与一个或多个响应文件中指定的选项组合在一起。</span><span class="sxs-lookup"><span data-stu-id="71792-115">You can combine options specified on the command line with options specified in one or more response files.</span></span> <span data-ttu-id="71792-116">编译器在遇到命令选项时进行处理。</span><span class="sxs-lookup"><span data-stu-id="71792-116">The compiler processes the command options as it encounters them.</span></span> <span data-ttu-id="71792-117">因此, 命令行参数可以重写以前在响应文件中列出的选项。</span><span class="sxs-lookup"><span data-stu-id="71792-117">Therefore, command-line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="71792-118">相反, 响应文件中的选项会替代前面的命令行或其他响应文件中列出的选项。</span><span class="sxs-lookup"><span data-stu-id="71792-118">Conversely, options in a response file override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="71792-119">Visual Basic 提供了 Vbc 文件, 该文件与 Vbc 文件位于同一目录中。</span><span class="sxs-lookup"><span data-stu-id="71792-119">Visual Basic provides the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="71792-120">默认情况下, 将包含 Vbc 文件, 除非使用`-noconfig`了选项。</span><span class="sxs-lookup"><span data-stu-id="71792-120">The Vbc.rsp file is included by default unless the `-noconfig` option is used.</span></span> <span data-ttu-id="71792-121">有关详细信息, 请参阅[-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)。</span><span class="sxs-lookup"><span data-stu-id="71792-121">For more information, see [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="71792-122">此`@`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。</span><span class="sxs-lookup"><span data-stu-id="71792-122">The `@` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71792-123">示例</span><span class="sxs-lookup"><span data-stu-id="71792-123">Example</span></span>  
 <span data-ttu-id="71792-124">以下行来自示例响应文件。</span><span class="sxs-lookup"><span data-stu-id="71792-124">The following lines are from a sample response file.</span></span>  
  
```console
# build the first output file  
-target:exe   
-out:MyExe.exe  
source1.vb   
source2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="71792-125">示例</span><span class="sxs-lookup"><span data-stu-id="71792-125">Example</span></span>  
 <span data-ttu-id="71792-126">下面的示例演示如何将`@`选项与名为`File1.rsp`的响应文件一起使用。</span><span class="sxs-lookup"><span data-stu-id="71792-126">The following example demonstrates how to use the `@` option with the response file named `File1.rsp`.</span></span>  
  
```console
vbc @file1.rsp  
```  
  
## <a name="see-also"></a><span data-ttu-id="71792-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="71792-127">See also</span></span>

- [<span data-ttu-id="71792-128">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="71792-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="71792-129">-noconfig</span><span class="sxs-lookup"><span data-stu-id="71792-129">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="71792-130">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="71792-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
