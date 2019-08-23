---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 4281c7bf5a7972d323e1e649aaef437c7ee901ff
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956262"
---
# <a name="-recurse"></a><span data-ttu-id="e6a85-102">-recurse</span><span class="sxs-lookup"><span data-stu-id="e6a85-102">-recurse</span></span>
<span data-ttu-id="e6a85-103">在指定目录或项目目录的所有子目录中编译源代码文件。</span><span class="sxs-lookup"><span data-stu-id="e6a85-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6a85-104">语法</span><span class="sxs-lookup"><span data-stu-id="e6a85-104">Syntax</span></span>  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="e6a85-105">自变量</span><span class="sxs-lookup"><span data-stu-id="e6a85-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="e6a85-106">可选。</span><span class="sxs-lookup"><span data-stu-id="e6a85-106">Optional.</span></span> <span data-ttu-id="e6a85-107">希望从中开始搜索的目录。</span><span class="sxs-lookup"><span data-stu-id="e6a85-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="e6a85-108">如果未指定, 则从项目目录中开始搜索。</span><span class="sxs-lookup"><span data-stu-id="e6a85-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="e6a85-109">必需。</span><span class="sxs-lookup"><span data-stu-id="e6a85-109">Required.</span></span> <span data-ttu-id="e6a85-110">要搜索的文件。</span><span class="sxs-lookup"><span data-stu-id="e6a85-110">The file(s) to search for.</span></span> <span data-ttu-id="e6a85-111">允许通配符。</span><span class="sxs-lookup"><span data-stu-id="e6a85-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6a85-112">备注</span><span class="sxs-lookup"><span data-stu-id="e6a85-112">Remarks</span></span>  
 <span data-ttu-id="e6a85-113">你可以在文件名中使用通配符, 以便在不使用`-recurse`的情况下编译项目目录中的所有匹配文件。</span><span class="sxs-lookup"><span data-stu-id="e6a85-113">You can use wildcards in a file name to compile all matching files in the project directory without using `-recurse`.</span></span> <span data-ttu-id="e6a85-114">如果未指定输出文件名, 编译器将基于处理的第一个输入文件的输出文件名。</span><span class="sxs-lookup"><span data-stu-id="e6a85-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="e6a85-115">这通常是按字母顺序查看时所编译文件列表中的第一个文件。</span><span class="sxs-lookup"><span data-stu-id="e6a85-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="e6a85-116">出于此原因, 最好使用`-out`选项指定输出文件。</span><span class="sxs-lookup"><span data-stu-id="e6a85-116">For this reason, it is best to specify an output file using the `-out` option.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6a85-117">此`-recurse`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。</span><span class="sxs-lookup"><span data-stu-id="e6a85-117">The `-recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6a85-118">示例</span><span class="sxs-lookup"><span data-stu-id="e6a85-118">Example</span></span>  
 <span data-ttu-id="e6a85-119">以下命令编译当前目录中的所有 Visual Basic 文件。</span><span class="sxs-lookup"><span data-stu-id="e6a85-119">The following command compiles all Visual Basic files in the current directory.</span></span>  
  
```console
vbc *.vb  
```  
  
 <span data-ttu-id="e6a85-120">以下命令编译目录中的`Test\ABC`所有 Visual Basic 文件以及它下面的所有目录, 然后生成。 `Test.ABC.dll`</span><span class="sxs-lookup"><span data-stu-id="e6a85-120">The following command compiles all Visual Basic files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6a85-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6a85-121">See also</span></span>

- [<span data-ttu-id="e6a85-122">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="e6a85-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="e6a85-123">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6a85-123">-out (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/out.md)
- [<span data-ttu-id="e6a85-124">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="e6a85-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
