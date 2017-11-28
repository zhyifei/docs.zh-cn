---
title: "@（C# 编译器选项）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '@'
helpviewer_keywords:
- response files, specifying for compilation [C#]
- '@ compiler option'
ms.assetid: dda4fa9f-a02c-400f-8b6a-d58834e13d7f
caps.latest.revision: "9"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d4dc8c81a9afd60add4c2a62be6804a0f6446124
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="-c-compiler-options"></a><span data-ttu-id="211d4-102">@（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="211d4-102">@ (C# Compiler Options)</span></span>
<span data-ttu-id="211d4-103">通过 @ 选项，可以指定包含编译器选项和要编译的源代码文件的文件。</span><span class="sxs-lookup"><span data-stu-id="211d4-103">The @ option lets you specify a file that contains compiler options and source code files to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="211d4-104">语法</span><span class="sxs-lookup"><span data-stu-id="211d4-104">Syntax</span></span>  
  
```  
@response_file  
```  
  
## <a name="arguments"></a><span data-ttu-id="211d4-105">参数</span><span class="sxs-lookup"><span data-stu-id="211d4-105">Arguments</span></span>  
 `response_file`  
 <span data-ttu-id="211d4-106">列出了编译器选项或要编译的源代码文件的文件。</span><span class="sxs-lookup"><span data-stu-id="211d4-106">A file that lists compiler options or source code files to compile.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="211d4-107">备注</span><span class="sxs-lookup"><span data-stu-id="211d4-107">Remarks</span></span>  
 <span data-ttu-id="211d4-108">编译器选项和源代码文件将由编译器处理，如同在命令行被指定一样。</span><span class="sxs-lookup"><span data-stu-id="211d4-108">The compiler options and source code files will be processed by the compiler just as if they had been specified on the command line.</span></span>  
  
 <span data-ttu-id="211d4-109">若要在一次编译中指定多个响应文件，请指定多个响应文件选项。</span><span class="sxs-lookup"><span data-stu-id="211d4-109">To specify more than one response file in a compilation, specify multiple response file options.</span></span> <span data-ttu-id="211d4-110">例如：</span><span class="sxs-lookup"><span data-stu-id="211d4-110">For example:</span></span>  
  
```  
@file1.rsp @file2.rsp  
```  
  
 <span data-ttu-id="211d4-111">在响应文件中，多个编译器选项和源代码文件可以出现在同一行中。</span><span class="sxs-lookup"><span data-stu-id="211d4-111">In a response file, multiple compiler options and source code files can appear on one line.</span></span> <span data-ttu-id="211d4-112">单个编译器选项的指定必须出现在同一行中（不能跨行）。</span><span class="sxs-lookup"><span data-stu-id="211d4-112">A single compiler option specification must appear on one line (cannot span multiple lines).</span></span> <span data-ttu-id="211d4-113">响应文件的注释可以 # 符号开始。</span><span class="sxs-lookup"><span data-stu-id="211d4-113">Response files can have comments that begin with the # symbol.</span></span>  
  
 <span data-ttu-id="211d4-114">从响应文件内指定编译器选项就如同在命令行发出这些命令。</span><span class="sxs-lookup"><span data-stu-id="211d4-114">Specifying compiler options from within a response file is just like issuing those commands on the command line.</span></span> <span data-ttu-id="211d4-115">有关详细信息，请参阅[从命令行生成](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)。</span><span class="sxs-lookup"><span data-stu-id="211d4-115">See [Building from the Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) for more information.</span></span>  
  
 <span data-ttu-id="211d4-116">编译器在遇到命令选项时会进行处理。</span><span class="sxs-lookup"><span data-stu-id="211d4-116">The compiler processes the command options as they are encountered.</span></span> <span data-ttu-id="211d4-117">因此，命令行参数可以重写先前在响应文件中列出的选项。</span><span class="sxs-lookup"><span data-stu-id="211d4-117">Therefore, command line arguments can override previously listed options in response files.</span></span> <span data-ttu-id="211d4-118">反之，响应文件中的选项也将重写先前在命令行或其他响应文件中列出的选项。</span><span class="sxs-lookup"><span data-stu-id="211d4-118">Conversely, options in a response file will override options listed previously on the command line or in other response files.</span></span>  
  
 <span data-ttu-id="211d4-119">C# 提供 csc.rsp 文件，该文件与 csc.exe 文件位于同一目录。</span><span class="sxs-lookup"><span data-stu-id="211d4-119">C# provides the csc.rsp file, which is located in the same directory as the csc.exe file.</span></span> <span data-ttu-id="211d4-120">有关 csc.rsp 的详细信息，请参阅 [/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)。</span><span class="sxs-lookup"><span data-stu-id="211d4-120">See [/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) for more information on csc.rsp.</span></span>  
  
 <span data-ttu-id="211d4-121">不能在 Visual Studio 开发环境中设置此编译器选项，也不能以编程方式对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="211d4-121">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="211d4-122">示例</span><span class="sxs-lookup"><span data-stu-id="211d4-122">Example</span></span>  
 <span data-ttu-id="211d4-123">以下几行来自示例响应文件：</span><span class="sxs-lookup"><span data-stu-id="211d4-123">The following are a few lines from a sample response file:</span></span>  
  
```console  
# build the first output file  
/target:exe /out:MyExe.exe source1.cs source2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="211d4-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="211d4-124">See Also</span></span>  
 [<span data-ttu-id="211d4-125">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="211d4-125">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
