---
title: "#<a name=\"externalsource-directive\"></a>ExternalSource 指令"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- '#Externalsource'
- '#ExternalSource'
- vb.ExternalSource
- Externalsource
- vb.#ExternalSource
- ExternalSource
helpviewer_keywords:
- ExternalSource directive (#ExternalSource)
- '#ExternalSource directive'
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
caps.latest.revision: "160"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f90b838e50b65b8652cd9cf6f6ee084e9552f025
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="externalsource-directive"></a><span data-ttu-id="1cded-102">#ExternalSource 指令</span><span class="sxs-lookup"><span data-stu-id="1cded-102">#ExternalSource Directive</span></span>
<span data-ttu-id="1cded-103">指示代码的源代码的特定行和源的外部文本之间的映射。</span><span class="sxs-lookup"><span data-stu-id="1cded-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cded-104">语法</span><span class="sxs-lookup"><span data-stu-id="1cded-104">Syntax</span></span>  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="1cded-105">部件</span><span class="sxs-lookup"><span data-stu-id="1cded-105">Parts</span></span>  
 `StringLiteral`  
 <span data-ttu-id="1cded-106">外部源的路径。</span><span class="sxs-lookup"><span data-stu-id="1cded-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="1cded-107">外部源的第一行的行号。</span><span class="sxs-lookup"><span data-stu-id="1cded-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="1cded-108">外部源中出现错误的行。</span><span class="sxs-lookup"><span data-stu-id="1cded-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="1cded-109">终止 `#ExternalSource` 块。</span><span class="sxs-lookup"><span data-stu-id="1cded-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1cded-110">备注</span><span class="sxs-lookup"><span data-stu-id="1cded-110">Remarks</span></span>  
 <span data-ttu-id="1cded-111">使用此指令时仅由编译器和调试器。</span><span class="sxs-lookup"><span data-stu-id="1cded-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="1cded-112">源文件可能包含外部源指令，指示特定的源文件中的代码行和源，例如一个.aspx 文件的外部文本之间的映射。</span><span class="sxs-lookup"><span data-stu-id="1cded-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="1cded-113">如果在编译期间指定的源代码中遇到错误，则将它们标识作为来自外部源中。</span><span class="sxs-lookup"><span data-stu-id="1cded-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="1cded-114">外部源指令不会影响编译，而且不能嵌套。</span><span class="sxs-lookup"><span data-stu-id="1cded-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="1cded-115">它们是由应用程序仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="1cded-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cded-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1cded-116">See Also</span></span>  
 [<span data-ttu-id="1cded-117">条件编译</span><span class="sxs-lookup"><span data-stu-id="1cded-117">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
