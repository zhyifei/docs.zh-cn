---
title: "/addmodule |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2db0db5b5dd94f03e67d8680624e2a4ad23587f7
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="addmodule"></a><span data-ttu-id="2a1cd-102">/addmodule</span><span class="sxs-lookup"><span data-stu-id="2a1cd-102">/addmodule</span></span>
<span data-ttu-id="2a1cd-103">使编译器让指定文件中的所有类型信息可供当前正在编译的项目使用。</span><span class="sxs-lookup"><span data-stu-id="2a1cd-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a1cd-104">语法</span><span class="sxs-lookup"><span data-stu-id="2a1cd-104">Syntax</span></span>  
  
```  
/addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="2a1cd-105">参数</span><span class="sxs-lookup"><span data-stu-id="2a1cd-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="2a1cd-106">必需。</span><span class="sxs-lookup"><span data-stu-id="2a1cd-106">Required.</span></span> <span data-ttu-id="2a1cd-107">包含元数据，但不是包含程序集清单的文件以逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="2a1cd-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="2a1cd-108">包含空格的文件名应该用引号引起来 ("")。</span><span class="sxs-lookup"><span data-stu-id="2a1cd-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a1cd-109">备注</span><span class="sxs-lookup"><span data-stu-id="2a1cd-109">Remarks</span></span>  
 <span data-ttu-id="2a1cd-110">按列出的文件`fileList`参数必须与创建`/target:module`选项，或使用其他编译器等效于`/target:module`。</span><span class="sxs-lookup"><span data-stu-id="2a1cd-110">The files listed by the `fileList` parameter must be created with the `/target:module` option, or with another compiler's equivalent to `/target:module`.</span></span>  
  
 <span data-ttu-id="2a1cd-111">使用添加的所有模块`/addmodule`必须在运行时是与输出文件的相同目录中。</span><span class="sxs-lookup"><span data-stu-id="2a1cd-111">All modules added with `/addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="2a1cd-112">也就是说，您也可以在编译时，指定在任何目录中的模块，但在运行时模块必须在应用程序目录。</span><span class="sxs-lookup"><span data-stu-id="2a1cd-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="2a1cd-113">如果不是这样，您得到<xref:System.TypeLoadException>错误。</xref:System.TypeLoadException></span><span class="sxs-lookup"><span data-stu-id="2a1cd-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="2a1cd-114">如果指定 （隐式或显式） 任何[/target (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/target.md)选项而不`/target:module`与`/addmodule`，文件将传递给`/addmodule`成为项目的程序集的一部分。</span><span class="sxs-lookup"><span data-stu-id="2a1cd-114">If you specify (implicitly or explicitly) any[/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `/target:module` with `/addmodule`, the files you pass to `/addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="2a1cd-115">运行具有一个输出文件所需的程序集或使用更多的文件添加`/addmodule`。</span><span class="sxs-lookup"><span data-stu-id="2a1cd-115">An assembly is required to run an output file that has one or more files added with `/addmodule`.</span></span>  
  
 <span data-ttu-id="2a1cd-116">使用[/reference (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/reference.md)从包含程序集文件中导入元数据。</span><span class="sxs-lookup"><span data-stu-id="2a1cd-116">Use [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a1cd-117">`/addmodule`选项不是在 Visual Studio 开发环境中可用; 只有当从命令行进行编译，它才可用。</span><span class="sxs-lookup"><span data-stu-id="2a1cd-117">The `/addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a1cd-118">示例</span><span class="sxs-lookup"><span data-stu-id="2a1cd-118">Example</span></span>  
 <span data-ttu-id="2a1cd-119">下面的代码创建一个模块。</span><span class="sxs-lookup"><span data-stu-id="2a1cd-119">The following code creates a module.</span></span>  
  
 <span data-ttu-id="2a1cd-120">[!code-vb[VbVbalrCompiler #&47;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2a1cd-120">[!code-vb[VbVbalrCompiler#47](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]</span></span>  
  
 <span data-ttu-id="2a1cd-121">下面的代码将导入该模块的类型。</span><span class="sxs-lookup"><span data-stu-id="2a1cd-121">The following code imports the module's types.</span></span>  
  
 <span data-ttu-id="2a1cd-122">[!code-vb[VbVbalrCompiler #&48;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="2a1cd-122">[!code-vb[VbVbalrCompiler#48](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]</span></span>  
  
 <span data-ttu-id="2a1cd-123">当您运行`t1`，它将输出`802`。</span><span class="sxs-lookup"><span data-stu-id="2a1cd-123">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a1cd-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a1cd-124">See Also</span></span>  
 <span data-ttu-id="2a1cd-125">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="2a1cd-125">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="2a1cd-126"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="2a1cd-126"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="2a1cd-127"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span><span class="sxs-lookup"><span data-stu-id="2a1cd-127"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span></span>  
<span data-ttu-id="2a1cd-128"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="2a1cd-128"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
