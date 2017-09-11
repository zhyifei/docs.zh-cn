---
title: "/recurse |Microsoft 文档"
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
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
caps.latest.revision: 12
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
ms.openlocfilehash: 9ceb2f3bc9e4d0f1088258f504b7a49c58a29e35
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="recurse"></a><span data-ttu-id="b7453-102">/recurse</span><span class="sxs-lookup"><span data-stu-id="b7453-102">/recurse</span></span>
<span data-ttu-id="b7453-103">编译源代码文件的指定的目录或项目目录的所有子目录中。</span><span class="sxs-lookup"><span data-stu-id="b7453-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7453-104">语法</span><span class="sxs-lookup"><span data-stu-id="b7453-104">Syntax</span></span>  
  
```  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="b7453-105">参数</span><span class="sxs-lookup"><span data-stu-id="b7453-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="b7453-106">可选。</span><span class="sxs-lookup"><span data-stu-id="b7453-106">Optional.</span></span> <span data-ttu-id="b7453-107">要在其中执行搜索，以开始目录。</span><span class="sxs-lookup"><span data-stu-id="b7453-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="b7453-108">如果未指定，那么搜索将开始在项目目录中。</span><span class="sxs-lookup"><span data-stu-id="b7453-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="b7453-109">必需。</span><span class="sxs-lookup"><span data-stu-id="b7453-109">Required.</span></span> <span data-ttu-id="b7453-110">要搜索的文件。</span><span class="sxs-lookup"><span data-stu-id="b7453-110">The file(s) to search for.</span></span> <span data-ttu-id="b7453-111">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="b7453-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7453-112">备注</span><span class="sxs-lookup"><span data-stu-id="b7453-112">Remarks</span></span>  
 <span data-ttu-id="b7453-113">可以在文件名中使用通配符来编译项目目录中的所有匹配文件，而无需使用`/recurse`。</span><span class="sxs-lookup"><span data-stu-id="b7453-113">You can use wildcards in a file name to compile all matching files in the project directory without using `/recurse`.</span></span> <span data-ttu-id="b7453-114">如果不指定任何输出文件的名称，则编译器将基于上处理的第一个输入文件的输出文件名称。</span><span class="sxs-lookup"><span data-stu-id="b7453-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="b7453-115">这通常是在编译时按字母顺序查看的文件列表中的第一个文件。</span><span class="sxs-lookup"><span data-stu-id="b7453-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="b7453-116">出于此原因，则最好指定输出文件中使用`/out`选项。</span><span class="sxs-lookup"><span data-stu-id="b7453-116">For this reason, it is best to specify an output file using the `/out` option.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7453-117">`/recurse`选项不是在 Visual Studio 开发环境中可用; 只有当从命令行进行编译，它才可用。</span><span class="sxs-lookup"><span data-stu-id="b7453-117">The `/recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7453-118">示例</span><span class="sxs-lookup"><span data-stu-id="b7453-118">Example</span></span>  
 <span data-ttu-id="b7453-119">下面的代码编译所有[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]当前目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="b7453-119">The following code compiles all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the current directory.</span></span>  
  
```  
vbc *.vb  
```  
  
 <span data-ttu-id="b7453-120">下面的代码编译所有[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]中的文件`Test\ABC`目录和，在它下面的任何目录，然后生成`Test.ABC.dll`。</span><span class="sxs-lookup"><span data-stu-id="b7453-120">The following code compiles all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```  
vbc /target:library /out:Test.ABC.dll /recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7453-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7453-121">See Also</span></span>  
 <span data-ttu-id="b7453-122">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="b7453-122">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="b7453-123"> [/ 输出 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md) </span><span class="sxs-lookup"><span data-stu-id="b7453-123"> [/out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md) </span></span>  
<span data-ttu-id="b7453-124"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="b7453-124"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
