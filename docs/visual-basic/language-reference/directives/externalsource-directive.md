---
title: '#ExternalSource 指令 (Visual Basic)'
ms.date: 07/20/2015
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
ms.openlocfilehash: 550934723a5599573be578ce5746ab7520b59dd1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705964"
---
# <a name="externalsource-directive"></a><span data-ttu-id="f2895-102">#ExternalSource 指令</span><span class="sxs-lookup"><span data-stu-id="f2895-102">#ExternalSource Directive</span></span>
<span data-ttu-id="f2895-103">指示特定行的源代码和源的外部文本之间的映射。</span><span class="sxs-lookup"><span data-stu-id="f2895-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2895-104">语法</span><span class="sxs-lookup"><span data-stu-id="f2895-104">Syntax</span></span>  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="f2895-105">部件</span><span class="sxs-lookup"><span data-stu-id="f2895-105">Parts</span></span>  
 `StringLiteral`  
 <span data-ttu-id="f2895-106">指向外部源的路径。</span><span class="sxs-lookup"><span data-stu-id="f2895-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="f2895-107">外部源的第一行的行数。</span><span class="sxs-lookup"><span data-stu-id="f2895-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="f2895-108">外部源中发生错误的行。</span><span class="sxs-lookup"><span data-stu-id="f2895-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="f2895-109">终止 `#ExternalSource` 块。</span><span class="sxs-lookup"><span data-stu-id="f2895-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2895-110">备注</span><span class="sxs-lookup"><span data-stu-id="f2895-110">Remarks</span></span>  
 <span data-ttu-id="f2895-111">使用此指令时仅由编译器和调试器。</span><span class="sxs-lookup"><span data-stu-id="f2895-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="f2895-112">源代码文件可以包含外部源指令，指示特定行的源文件中的代码和源，例如.aspx 文件的外部文本之间的映射。</span><span class="sxs-lookup"><span data-stu-id="f2895-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="f2895-113">如果在编译期间指定的源代码中遇到错误，则将其标识为来自外部源中。</span><span class="sxs-lookup"><span data-stu-id="f2895-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="f2895-114">外部源指令不会影响编译，而且不能嵌套。</span><span class="sxs-lookup"><span data-stu-id="f2895-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="f2895-115">它们是由应用程序仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="f2895-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2895-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2895-116">See also</span></span>
- [<span data-ttu-id="f2895-117">条件编译</span><span class="sxs-lookup"><span data-stu-id="f2895-117">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
