---
title: -addmodule
ms.date: 03/09/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c17d5541fe2d02ba88f4c5ef259b2248f371dfe5
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="-addmodule"></a><span data-ttu-id="caa82-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="caa82-102">-addmodule</span></span>
<span data-ttu-id="caa82-103">使编译器让指定文件中的所有类型信息可供当前正在编译的项目使用。</span><span class="sxs-lookup"><span data-stu-id="caa82-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caa82-104">语法</span><span class="sxs-lookup"><span data-stu-id="caa82-104">Syntax</span></span>  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="caa82-105">自变量</span><span class="sxs-lookup"><span data-stu-id="caa82-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="caa82-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="caa82-106">Required.</span></span> <span data-ttu-id="caa82-107">包含的元数据，但不是包含程序集清单的文件以逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="caa82-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="caa82-108">文件名称中包含空格应该用引号引起来 ("")。</span><span class="sxs-lookup"><span data-stu-id="caa82-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="caa82-109">备注</span><span class="sxs-lookup"><span data-stu-id="caa82-109">Remarks</span></span>  
 <span data-ttu-id="caa82-110">通过列出的文件`fileList`参数必须用来创建`-target:module`选项，或与另一编译器等效于`-target:module`。</span><span class="sxs-lookup"><span data-stu-id="caa82-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="caa82-111">使用添加的所有模块`-addmodule`必须在运行时是输出文件所在的同一目录中。</span><span class="sxs-lookup"><span data-stu-id="caa82-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="caa82-112">也就是说，你也可以在编译时，指定在任何目录中的模块，但在运行时的模块必须在应用程序目录。</span><span class="sxs-lookup"><span data-stu-id="caa82-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="caa82-113">如果不是这样，你将获取<xref:System.TypeLoadException>错误。</span><span class="sxs-lookup"><span data-stu-id="caa82-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="caa82-114">如果您指定 （隐式或显式） 任何[-目标 (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/target.md)选项而不`-target:module`与`-addmodule`，传递给文件`-addmodule`成为项目的程序集的一部分。</span><span class="sxs-lookup"><span data-stu-id="caa82-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="caa82-115">运行具有一个输出文件所需的程序集或使用更多的文件添加`-addmodule`。</span><span class="sxs-lookup"><span data-stu-id="caa82-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="caa82-116">使用[/reference (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/reference.md)从包含程序集的文件导入元数据。</span><span class="sxs-lookup"><span data-stu-id="caa82-116">Use [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="caa82-117">`-addmodule`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="caa82-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="caa82-118">示例</span><span class="sxs-lookup"><span data-stu-id="caa82-118">Example</span></span>  
 <span data-ttu-id="caa82-119">下面的代码创建一个模块。</span><span class="sxs-lookup"><span data-stu-id="caa82-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]  
  
 <span data-ttu-id="caa82-120">下面的代码导入模块的类型。</span><span class="sxs-lookup"><span data-stu-id="caa82-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]  
  
 <span data-ttu-id="caa82-121">当你运行`t1`，它将输出`802`。</span><span class="sxs-lookup"><span data-stu-id="caa82-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caa82-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="caa82-122">See Also</span></span>  
 [<span data-ttu-id="caa82-123">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="caa82-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="caa82-124">-目标 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="caa82-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="caa82-125">-参考 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="caa82-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [<span data-ttu-id="caa82-126">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="caa82-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
