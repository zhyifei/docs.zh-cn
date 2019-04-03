---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 2de5fe82f1969a2fdb305d45951d7d698252c0c8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816429"
---
# <a name="-addmodule"></a><span data-ttu-id="b667b-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="b667b-102">-addmodule</span></span>
<span data-ttu-id="b667b-103">使编译器让指定文件中的所有类型信息可供当前正在编译的项目使用。</span><span class="sxs-lookup"><span data-stu-id="b667b-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b667b-104">语法</span><span class="sxs-lookup"><span data-stu-id="b667b-104">Syntax</span></span>  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="b667b-105">自变量</span><span class="sxs-lookup"><span data-stu-id="b667b-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="b667b-106">必需。</span><span class="sxs-lookup"><span data-stu-id="b667b-106">Required.</span></span> <span data-ttu-id="b667b-107">以逗号分隔列表，包含元数据，但不是包含程序集清单的文件。</span><span class="sxs-lookup"><span data-stu-id="b667b-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="b667b-108">包含空格的文件名应该用引号引起来 ("")。</span><span class="sxs-lookup"><span data-stu-id="b667b-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b667b-109">备注</span><span class="sxs-lookup"><span data-stu-id="b667b-109">Remarks</span></span>  
 <span data-ttu-id="b667b-110">通过列出的文件`fileList`必须与创建参数`-target:module`选项，或使用其他编译器的等效于`-target:module`。</span><span class="sxs-lookup"><span data-stu-id="b667b-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="b667b-111">添加的所有模块`-addmodule`在运行时必须位于与输出文件相同的目录中。</span><span class="sxs-lookup"><span data-stu-id="b667b-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="b667b-112">也就是说，可以在编译时，在任何目录中指定模块，但在运行时模块必须在应用程序目录。</span><span class="sxs-lookup"><span data-stu-id="b667b-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="b667b-113">如果不存在，则获取<xref:System.TypeLoadException>错误。</span><span class="sxs-lookup"><span data-stu-id="b667b-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="b667b-114">如果指定 （隐式或显式） 任何[-目标 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)选项而`-target:module`与`-addmodule`，将传递到的文件`-addmodule`成为项目的程序集的一部分。</span><span class="sxs-lookup"><span data-stu-id="b667b-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="b667b-115">运行具有一个输出文件所需的程序集或更多的文件添加与`-addmodule`。</span><span class="sxs-lookup"><span data-stu-id="b667b-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="b667b-116">使用[/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)包含程序集文件中导入元数据。</span><span class="sxs-lookup"><span data-stu-id="b667b-116">Use [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b667b-117">`-addmodule`选项不适用于从 Visual Studio 开发环境中，仅当从命令行编译时便可。</span><span class="sxs-lookup"><span data-stu-id="b667b-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b667b-118">示例</span><span class="sxs-lookup"><span data-stu-id="b667b-118">Example</span></span>  
 <span data-ttu-id="b667b-119">下面的代码创建一个模块。</span><span class="sxs-lookup"><span data-stu-id="b667b-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 <span data-ttu-id="b667b-120">以下代码导入模块的类型。</span><span class="sxs-lookup"><span data-stu-id="b667b-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 <span data-ttu-id="b667b-121">在运行时`t1`，它将输出`802`。</span><span class="sxs-lookup"><span data-stu-id="b667b-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b667b-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="b667b-122">See also</span></span>

- [<span data-ttu-id="b667b-123">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="b667b-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="b667b-124">-目标 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b667b-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="b667b-125">-参考 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b667b-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="b667b-126">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="b667b-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
