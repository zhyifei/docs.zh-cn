---
title: '#Const 指令'
ms.date: 07/20/2015
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
ms.openlocfilehash: a3b3318f6b44f7d1798e08195be5aeb920b61c0c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588062"
---
# <a name="const-directive"></a><span data-ttu-id="a9ee7-102">#Const 指令</span><span class="sxs-lookup"><span data-stu-id="a9ee7-102">#Const Directive</span></span>
<span data-ttu-id="a9ee7-103">适用于 Visual Basic 中定义条件编译器常数。</span><span class="sxs-lookup"><span data-stu-id="a9ee7-103">Defines conditional compiler constants for Visual Basic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9ee7-104">语法</span><span class="sxs-lookup"><span data-stu-id="a9ee7-104">Syntax</span></span>  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a><span data-ttu-id="a9ee7-105">部件</span><span class="sxs-lookup"><span data-stu-id="a9ee7-105">Parts</span></span>  
 `constname`  
 <span data-ttu-id="a9ee7-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="a9ee7-106">Required.</span></span> <span data-ttu-id="a9ee7-107">正在定义的常数的名称。</span><span class="sxs-lookup"><span data-stu-id="a9ee7-107">Name of the constant being defined.</span></span>  
  
 `expression`  
 <span data-ttu-id="a9ee7-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="a9ee7-108">Required.</span></span> <span data-ttu-id="a9ee7-109">文本、 其他条件编译器常量或包括除之外的任何或所有算术或逻辑运算符的任意组合的`Is`。</span><span class="sxs-lookup"><span data-stu-id="a9ee7-109">Literal, other conditional compiler constant, or any combination that includes any or all arithmetic or logical operators except `Is`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9ee7-110">备注</span><span class="sxs-lookup"><span data-stu-id="a9ee7-110">Remarks</span></span>  
 <span data-ttu-id="a9ee7-111">条件编译器常数始终是私有它们出现的文件类型。</span><span class="sxs-lookup"><span data-stu-id="a9ee7-111">Conditional compiler constants are always private to the file in which they appear.</span></span> <span data-ttu-id="a9ee7-112">无法创建公共编译器常量使用`#Const`指令; 你可以创建它们仅在用户界面中或使用`/define`编译器选项。</span><span class="sxs-lookup"><span data-stu-id="a9ee7-112">You cannot create public compiler constants using the `#Const` directive; you can create them only in the user interface or with the `/define` compiler option.</span></span>  
  
 <span data-ttu-id="a9ee7-113">你可以使用仅条件编译器常数和中的文本`expression`。</span><span class="sxs-lookup"><span data-stu-id="a9ee7-113">You can use only conditional compiler constants and literals in `expression`.</span></span> <span data-ttu-id="a9ee7-114">使用与定义的标准常量`Const`会导致错误。</span><span class="sxs-lookup"><span data-stu-id="a9ee7-114">Using a standard constant defined with `Const` causes an error.</span></span> <span data-ttu-id="a9ee7-115">相反，你可以使用定义的常数`#Const`关键字仅用于条件编译。</span><span class="sxs-lookup"><span data-stu-id="a9ee7-115">Conversely, you can use constants defined with the `#Const` keyword only for conditional compilation.</span></span> <span data-ttu-id="a9ee7-116">常量还定义，在这种情况下它们具有值为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="a9ee7-116">Constants can also be undefined, in which case they have a value of `Nothing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9ee7-117">示例</span><span class="sxs-lookup"><span data-stu-id="a9ee7-117">Example</span></span>  
 <span data-ttu-id="a9ee7-118">此示例使用 `#Const` 指令。</span><span class="sxs-lookup"><span data-stu-id="a9ee7-118">This example uses the `#Const` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#3](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/const-directive_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a9ee7-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9ee7-119">See Also</span></span>  
 [<span data-ttu-id="a9ee7-120">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9ee7-120">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)  
 [<span data-ttu-id="a9ee7-121">#If...Then...#Else 指令</span><span class="sxs-lookup"><span data-stu-id="a9ee7-121">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="a9ee7-122">Const 语句</span><span class="sxs-lookup"><span data-stu-id="a9ee7-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="a9ee7-123">条件编译</span><span class="sxs-lookup"><span data-stu-id="a9ee7-123">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [<span data-ttu-id="a9ee7-124">If...Then...Else 语句</span><span class="sxs-lookup"><span data-stu-id="a9ee7-124">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
