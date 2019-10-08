---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: fbe3634d1fbc03acd56ef7276d65fd54493b9806
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002412"
---
# <a name="-addmodule"></a><span data-ttu-id="86b42-102">-addmodule</span><span class="sxs-lookup"><span data-stu-id="86b42-102">-addmodule</span></span>
<span data-ttu-id="86b42-103">使编译器让指定文件中的所有类型信息可供当前正在编译的项目使用。</span><span class="sxs-lookup"><span data-stu-id="86b42-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86b42-104">语法</span><span class="sxs-lookup"><span data-stu-id="86b42-104">Syntax</span></span>  
  
```console  
-addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="86b42-105">参数</span><span class="sxs-lookup"><span data-stu-id="86b42-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="86b42-106">必需。</span><span class="sxs-lookup"><span data-stu-id="86b42-106">Required.</span></span> <span data-ttu-id="86b42-107">包含元数据但不包含程序集清单的文件的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="86b42-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="86b42-108">包含空格的文件名应括在引号（""）中。</span><span class="sxs-lookup"><span data-stu-id="86b42-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86b42-109">备注</span><span class="sxs-lookup"><span data-stu-id="86b42-109">Remarks</span></span>  
 <span data-ttu-id="86b42-110">@No__t-0 参数列出的文件必须使用 `-target:module` 选项创建，或与另一个编译器等效于 `-target:module`。</span><span class="sxs-lookup"><span data-stu-id="86b42-110">The files listed by the `fileList` parameter must be created with the `-target:module` option, or with another compiler's equivalent to `-target:module`.</span></span>  
  
 <span data-ttu-id="86b42-111">与 @no__t 一起添加的所有模块在运行时必须位于与输出文件相同的目录中。</span><span class="sxs-lookup"><span data-stu-id="86b42-111">All modules added with `-addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="86b42-112">也就是说，您可以在编译时在任何目录中指定一个模块，但该模块必须在运行时在应用程序目录中。</span><span class="sxs-lookup"><span data-stu-id="86b42-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="86b42-113">如果不是，则会出现 <xref:System.TypeLoadException> 错误。</span><span class="sxs-lookup"><span data-stu-id="86b42-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="86b42-114">如果指定（隐式或显式）除 `-addmodule` @no__t 以外的任何[目标（Visual Basic）](../../../visual-basic/reference/command-line-compiler/target.md)选项，则传递到 @no__t 的文件将成为项目的程序集的一部分。</span><span class="sxs-lookup"><span data-stu-id="86b42-114">If you specify (implicitly or explicitly) any[-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `-target:module` with `-addmodule`, the files you pass to `-addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="86b42-115">需要一个程序集来运行一个输出文件，其中包含一个或多个文件，并 `-addmodule`。</span><span class="sxs-lookup"><span data-stu-id="86b42-115">An assembly is required to run an output file that has one or more files added with `-addmodule`.</span></span>  
  
 <span data-ttu-id="86b42-116">使用[/reference （Visual Basic）](../../../visual-basic/reference/command-line-compiler/reference.md)从包含程序集的文件导入元数据。</span><span class="sxs-lookup"><span data-stu-id="86b42-116">Use [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="86b42-117">在 Visual Studio 开发环境中，不能使用 `-addmodule` 选项;仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="86b42-117">The `-addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86b42-118">示例</span><span class="sxs-lookup"><span data-stu-id="86b42-118">Example</span></span>  
 <span data-ttu-id="86b42-119">下面的代码将创建一个模块。</span><span class="sxs-lookup"><span data-stu-id="86b42-119">The following code creates a module.</span></span>  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 <span data-ttu-id="86b42-120">下面的代码将导入模块的类型。</span><span class="sxs-lookup"><span data-stu-id="86b42-120">The following code imports the module's types.</span></span>  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 <span data-ttu-id="86b42-121">当你运行 `t1` 时，它将输出 `802`。</span><span class="sxs-lookup"><span data-stu-id="86b42-121">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86b42-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="86b42-122">See also</span></span>

- [<span data-ttu-id="86b42-123">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="86b42-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="86b42-124">-target （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="86b42-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="86b42-125">-reference （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="86b42-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="86b42-126">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="86b42-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
