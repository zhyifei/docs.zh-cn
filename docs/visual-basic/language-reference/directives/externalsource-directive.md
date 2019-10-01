---
title: '#ExternalSource 指令（Visual Basic）'
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
ms.openlocfilehash: ac7096e998dd8d2a416dc739e1d7625e1abff7a6
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696826"
---
# <a name="externalsource-directive"></a><span data-ttu-id="bfcca-102">#ExternalSource 指令</span><span class="sxs-lookup"><span data-stu-id="bfcca-102">#ExternalSource Directive</span></span>
<span data-ttu-id="bfcca-103">指示源代码的特定行与源外部的文本之间的映射。</span><span class="sxs-lookup"><span data-stu-id="bfcca-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfcca-104">语法</span><span class="sxs-lookup"><span data-stu-id="bfcca-104">Syntax</span></span>  
  
```vb  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="bfcca-105">部件</span><span class="sxs-lookup"><span data-stu-id="bfcca-105">Parts</span></span>  
 `StringLiteral`  
 <span data-ttu-id="bfcca-106">外部源的路径。</span><span class="sxs-lookup"><span data-stu-id="bfcca-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="bfcca-107">外部源的第一行的行号。</span><span class="sxs-lookup"><span data-stu-id="bfcca-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="bfcca-108">外部源中发生错误的行。</span><span class="sxs-lookup"><span data-stu-id="bfcca-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="bfcca-109">终止 `#ExternalSource` 块。</span><span class="sxs-lookup"><span data-stu-id="bfcca-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfcca-110">备注</span><span class="sxs-lookup"><span data-stu-id="bfcca-110">Remarks</span></span>  
 <span data-ttu-id="bfcca-111">此指令仅由编译器和调试器使用。</span><span class="sxs-lookup"><span data-stu-id="bfcca-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="bfcca-112">源文件可能包含外部源指令，这表示源文件中特定代码行与源外部的文本之间的映射，如 .aspx 文件。</span><span class="sxs-lookup"><span data-stu-id="bfcca-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="bfcca-113">如果编译过程中在指定的源代码中遇到错误，则会将它们标识为来自外部源。</span><span class="sxs-lookup"><span data-stu-id="bfcca-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="bfcca-114">外部源指令对编译不起作用，因此不能嵌套。</span><span class="sxs-lookup"><span data-stu-id="bfcca-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="bfcca-115">它们仅供应用程序内部使用。</span><span class="sxs-lookup"><span data-stu-id="bfcca-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfcca-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="bfcca-116">See also</span></span>

- [<span data-ttu-id="bfcca-117">条件编译</span><span class="sxs-lookup"><span data-stu-id="bfcca-117">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
