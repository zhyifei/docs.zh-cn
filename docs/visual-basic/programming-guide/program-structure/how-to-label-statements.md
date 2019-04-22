---
title: 如何：标签语句 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: 69ec8c7625410f140c59ba8dd492dca76857eb96
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58828636"
---
# <a name="how-to-label-statements-visual-basic"></a><span data-ttu-id="c1d50-102">如何：标签语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1d50-102">How to: Label Statements (Visual Basic)</span></span>
<span data-ttu-id="c1d50-103">语句块组成的代码由冒号分隔行。</span><span class="sxs-lookup"><span data-stu-id="c1d50-103">Statement blocks are made up of lines of code delimited by colons.</span></span> <span data-ttu-id="c1d50-104">标识字符串或整数的代码注释行被称为*标记为*。</span><span class="sxs-lookup"><span data-stu-id="c1d50-104">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span></span> <span data-ttu-id="c1d50-105">语句标签用于标记的一行代码以将其标识用于与语句如`On Error Goto`。</span><span class="sxs-lookup"><span data-stu-id="c1d50-105">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 <span data-ttu-id="c1d50-106">标签可能是任一有效的 Visual Basic 标识符，如标识编程元素，或整数文本。</span><span class="sxs-lookup"><span data-stu-id="c1d50-106">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span></span> <span data-ttu-id="c1d50-107">标签必须位于源代码的行的开头和必须跟一个冒号，而不考虑它后面的语句置于同一行。</span><span class="sxs-lookup"><span data-stu-id="c1d50-107">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span></span>  
  
 <span data-ttu-id="c1d50-108">编译器通过检查行的开头是否与任何已定义的标识符相匹配来标识标签。</span><span class="sxs-lookup"><span data-stu-id="c1d50-108">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span></span> <span data-ttu-id="c1d50-109">如果不是，编译器将假定它是一个标签。</span><span class="sxs-lookup"><span data-stu-id="c1d50-109">If it does not, the compiler assumes it is a label.</span></span>  
  
 <span data-ttu-id="c1d50-110">标签具有其自己的声明空间并不会干扰其他标识符。</span><span class="sxs-lookup"><span data-stu-id="c1d50-110">Labels have their own declaration space and do not interfere with other identifiers.</span></span> <span data-ttu-id="c1d50-111">标签的作用域是该方法的正文。</span><span class="sxs-lookup"><span data-stu-id="c1d50-111">A label's scope is the body of the method.</span></span> <span data-ttu-id="c1d50-112">标签声明在任何不明确的情况下将优先。</span><span class="sxs-lookup"><span data-stu-id="c1d50-112">Label declaration takes precedence in any ambiguous situation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1d50-113">标签仅用于在方法内的可执行语句。</span><span class="sxs-lookup"><span data-stu-id="c1d50-113">Labels can be used only on executable statements inside methods.</span></span>  
  
### <a name="to-label-a-line-of-code"></a><span data-ttu-id="c1d50-114">若要标记的代码行</span><span class="sxs-lookup"><span data-stu-id="c1d50-114">To label a line of code</span></span>  
  
-   <span data-ttu-id="c1d50-115">将跟一个冒号，源代码的行的开头的标识符。</span><span class="sxs-lookup"><span data-stu-id="c1d50-115">Place an identifier, followed by a colon, at the beginning of the line of source code.</span></span>  
  
     <span data-ttu-id="c1d50-116">例如，以下代码行标记为`Jump`和`120`分别：</span><span class="sxs-lookup"><span data-stu-id="c1d50-116">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span></span>  
  
     [!code-vb[VbVbalrStatements#708](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#708)]  
  
## <a name="see-also"></a><span data-ttu-id="c1d50-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1d50-117">See also</span></span>

- [<span data-ttu-id="c1d50-118">语句</span><span class="sxs-lookup"><span data-stu-id="c1d50-118">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="c1d50-119">已声明的元素名称</span><span class="sxs-lookup"><span data-stu-id="c1d50-119">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="c1d50-120">程序结构和代码约定</span><span class="sxs-lookup"><span data-stu-id="c1d50-120">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
