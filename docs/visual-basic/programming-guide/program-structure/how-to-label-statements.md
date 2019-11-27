---
title: 如何：标记语句
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: be116ac8046c43e89e44c2d9127c6131e4dfaa52
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347385"
---
# <a name="how-to-label-statements-visual-basic"></a><span data-ttu-id="b4a36-102">如何：标记语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4a36-102">How to: Label Statements (Visual Basic)</span></span>

<span data-ttu-id="b4a36-103">语句块由用冒号分隔的代码行组成。</span><span class="sxs-lookup"><span data-stu-id="b4a36-103">Statement blocks are made up of lines of code delimited by colons.</span></span> <span data-ttu-id="b4a36-104">以标识字符串或整数开头的代码行称为 "*标记*"。</span><span class="sxs-lookup"><span data-stu-id="b4a36-104">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span></span> <span data-ttu-id="b4a36-105">语句标签用于标记代码行，以将其标识为与 `On Error Goto`等语句一起使用。</span><span class="sxs-lookup"><span data-stu-id="b4a36-105">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>

<span data-ttu-id="b4a36-106">标签可以是有效 Visual Basic 标识符（如标识编程元素的标识符），也可以是整数文本。</span><span class="sxs-lookup"><span data-stu-id="b4a36-106">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span></span> <span data-ttu-id="b4a36-107">标签必须出现在源代码行的开头，并且必须后跟一个冒号，而不考虑它是否后跟同一行中的语句。</span><span class="sxs-lookup"><span data-stu-id="b4a36-107">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span></span>

<span data-ttu-id="b4a36-108">编译器通过检查行首是否与任何已定义的标识符匹配来标识标签。</span><span class="sxs-lookup"><span data-stu-id="b4a36-108">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span></span> <span data-ttu-id="b4a36-109">如果不是，编译器将假定它是一个标签。</span><span class="sxs-lookup"><span data-stu-id="b4a36-109">If it does not, the compiler assumes it is a label.</span></span>

<span data-ttu-id="b4a36-110">标签具有自己的声明空间，不会干扰其他标识符。</span><span class="sxs-lookup"><span data-stu-id="b4a36-110">Labels have their own declaration space and do not interfere with other identifiers.</span></span> <span data-ttu-id="b4a36-111">标签的范围是方法的主体。</span><span class="sxs-lookup"><span data-stu-id="b4a36-111">A label's scope is the body of the method.</span></span> <span data-ttu-id="b4a36-112">标签声明优先于任何不明确的情况。</span><span class="sxs-lookup"><span data-stu-id="b4a36-112">Label declaration takes precedence in any ambiguous situation.</span></span>

> [!NOTE]
> <span data-ttu-id="b4a36-113">标签只能用于方法中的可执行语句。</span><span class="sxs-lookup"><span data-stu-id="b4a36-113">Labels can be used only on executable statements inside methods.</span></span>

## <a name="to-label-a-line-of-code"></a><span data-ttu-id="b4a36-114">为代码行添加标签</span><span class="sxs-lookup"><span data-stu-id="b4a36-114">To label a line of code</span></span>

<span data-ttu-id="b4a36-115">在源代码行的开头放置一个标识符，后跟一个冒号。</span><span class="sxs-lookup"><span data-stu-id="b4a36-115">Place an identifier, followed by a colon, at the beginning of the line of source code.</span></span>

<span data-ttu-id="b4a36-116">例如，以下代码行将分别标记为 `Jump` 和 `120`：</span><span class="sxs-lookup"><span data-stu-id="b4a36-116">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span></span>

[!code-vb[VbVbalrStatements#708](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#708)]

## <a name="see-also"></a><span data-ttu-id="b4a36-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4a36-117">See also</span></span>

- [<span data-ttu-id="b4a36-118">语句</span><span class="sxs-lookup"><span data-stu-id="b4a36-118">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="b4a36-119">已声明的元素名称</span><span class="sxs-lookup"><span data-stu-id="b4a36-119">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="b4a36-120">程序结构和代码约定</span><span class="sxs-lookup"><span data-stu-id="b4a36-120">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
