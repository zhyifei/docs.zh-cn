---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: b108a99c799523f3eb50c075a5dc67f0648403fa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552328"
---
# <a name="-recurse"></a><span data-ttu-id="4844f-102">-recurse</span><span class="sxs-lookup"><span data-stu-id="4844f-102">-recurse</span></span>
<span data-ttu-id="4844f-103">编译源代码文件中指定的目录或项目目录的所有子目录。</span><span class="sxs-lookup"><span data-stu-id="4844f-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4844f-104">语法</span><span class="sxs-lookup"><span data-stu-id="4844f-104">Syntax</span></span>  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="4844f-105">自变量</span><span class="sxs-lookup"><span data-stu-id="4844f-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="4844f-106">可选。</span><span class="sxs-lookup"><span data-stu-id="4844f-106">Optional.</span></span> <span data-ttu-id="4844f-107">希望从中开始搜索的目录。</span><span class="sxs-lookup"><span data-stu-id="4844f-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="4844f-108">如果未指定，在项目目录中开始搜索。</span><span class="sxs-lookup"><span data-stu-id="4844f-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="4844f-109">必需。</span><span class="sxs-lookup"><span data-stu-id="4844f-109">Required.</span></span> <span data-ttu-id="4844f-110">要搜索的文件。</span><span class="sxs-lookup"><span data-stu-id="4844f-110">The file(s) to search for.</span></span> <span data-ttu-id="4844f-111">允许通配符。</span><span class="sxs-lookup"><span data-stu-id="4844f-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4844f-112">备注</span><span class="sxs-lookup"><span data-stu-id="4844f-112">Remarks</span></span>  
 <span data-ttu-id="4844f-113">可以在文件名中使用通配符来编译项目目录中的所有匹配文件无需使用`-recurse`。</span><span class="sxs-lookup"><span data-stu-id="4844f-113">You can use wildcards in a file name to compile all matching files in the project directory without using `-recurse`.</span></span> <span data-ttu-id="4844f-114">如果不指定任何输出文件的名称，编译器将基于处理的第一个输入文件上的输出文件名称。</span><span class="sxs-lookup"><span data-stu-id="4844f-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="4844f-115">这通常是在编译时按字母顺序查看的文件列表中的第一个文件。</span><span class="sxs-lookup"><span data-stu-id="4844f-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="4844f-116">出于此原因，最好指定输出文件使用`-out`选项。</span><span class="sxs-lookup"><span data-stu-id="4844f-116">For this reason, it is best to specify an output file using the `-out` option.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4844f-117">`-recurse`选项不适用于从 Visual Studio 开发环境中，仅当从命令行编译时便可。</span><span class="sxs-lookup"><span data-stu-id="4844f-117">The `-recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4844f-118">示例</span><span class="sxs-lookup"><span data-stu-id="4844f-118">Example</span></span>  
 <span data-ttu-id="4844f-119">下面的命令编译当前目录中的所有 Visual Basic 文件。</span><span class="sxs-lookup"><span data-stu-id="4844f-119">The following command compiles all Visual Basic files in the current directory.</span></span>  
  
```console
vbc *.vb  
```  
  
 <span data-ttu-id="4844f-120">下面的命令编译中的所有 Visual Basic 文件`Test\ABC`directory 和任何目录，然后生成`Test.ABC.dll`。</span><span class="sxs-lookup"><span data-stu-id="4844f-120">The following command compiles all Visual Basic files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4844f-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="4844f-121">See also</span></span>
- [<span data-ttu-id="4844f-122">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="4844f-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="4844f-123">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4844f-123">-out (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/out.md)
- [<span data-ttu-id="4844f-124">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="4844f-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
