---
title: '#Const 指令 (Visual Basic)'
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
ms.openlocfilehash: 58d786c5e16b1e667f7c7c78b0f7857cd9711239
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46537795"
---
# <a name="const-directive"></a><span data-ttu-id="9a8e9-102">#Const 指令</span><span class="sxs-lookup"><span data-stu-id="9a8e9-102">#Const Directive</span></span>
<span data-ttu-id="9a8e9-103">对于 Visual Basic 中定义条件编译器常量。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-103">Defines conditional compiler constants for Visual Basic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a8e9-104">语法</span><span class="sxs-lookup"><span data-stu-id="9a8e9-104">Syntax</span></span>  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a><span data-ttu-id="9a8e9-105">部件</span><span class="sxs-lookup"><span data-stu-id="9a8e9-105">Parts</span></span>  
 `constname`  
 <span data-ttu-id="9a8e9-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-106">Required.</span></span> <span data-ttu-id="9a8e9-107">正在定义的常量的名称。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-107">Name of the constant being defined.</span></span>  
  
 `expression`  
 <span data-ttu-id="9a8e9-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-108">Required.</span></span> <span data-ttu-id="9a8e9-109">文本、 其他条件编译器常量或包括除之外的任何或所有算术或逻辑运算符的任意组合`Is`。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-109">Literal, other conditional compiler constant, or any combination that includes any or all arithmetic or logical operators except `Is`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a8e9-110">备注</span><span class="sxs-lookup"><span data-stu-id="9a8e9-110">Remarks</span></span>  
 <span data-ttu-id="9a8e9-111">条件编译器常量始终是专用于其显示的文件。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-111">Conditional compiler constants are always private to the file in which they appear.</span></span> <span data-ttu-id="9a8e9-112">无法创建使用公共编译器常量`#Const`指令; 仅在用户界面或使用可以创建它们`/define`编译器选项。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-112">You cannot create public compiler constants using the `#Const` directive; you can create them only in the user interface or with the `/define` compiler option.</span></span>  
  
 <span data-ttu-id="9a8e9-113">可以使用只有条件编译器常量和中的文本`expression`。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-113">You can use only conditional compiler constants and literals in `expression`.</span></span> <span data-ttu-id="9a8e9-114">使用与定义的标准常量`Const`将导致错误。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-114">Using a standard constant defined with `Const` causes an error.</span></span> <span data-ttu-id="9a8e9-115">相反，可以使用定义的常数`#Const`关键字用于条件编译。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-115">Conversely, you can use constants defined with the `#Const` keyword only for conditional compilation.</span></span> <span data-ttu-id="9a8e9-116">常量还定义，在这种情况下它们具有值为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-116">Constants can also be undefined, in which case they have a value of `Nothing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a8e9-117">示例</span><span class="sxs-lookup"><span data-stu-id="9a8e9-117">Example</span></span>  
 <span data-ttu-id="9a8e9-118">此示例使用 `#Const` 指令。</span><span class="sxs-lookup"><span data-stu-id="9a8e9-118">This example uses the `#Const` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#3](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/const-directive_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9a8e9-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a8e9-119">See Also</span></span>  
 [<span data-ttu-id="9a8e9-120">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a8e9-120">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)  
 [<span data-ttu-id="9a8e9-121">#If...Then...#Else 指令</span><span class="sxs-lookup"><span data-stu-id="9a8e9-121">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="9a8e9-122">Const 语句</span><span class="sxs-lookup"><span data-stu-id="9a8e9-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="9a8e9-123">条件编译</span><span class="sxs-lookup"><span data-stu-id="9a8e9-123">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [<span data-ttu-id="9a8e9-124">If...Then...Else 语句</span><span class="sxs-lookup"><span data-stu-id="9a8e9-124">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
