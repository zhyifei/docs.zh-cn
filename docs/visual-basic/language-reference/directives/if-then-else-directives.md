---
title: '#如果......#Else 指令'
ms.date: 04/11/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.#EndIf
- '#End If'
- '#Then'
- '#ElseIf'
- vb.#ElseIf
- vb.#Else
- vb.#If
helpviewer_keywords:
- Visual Basic code, compiling
- '#If directive [Visual Basic]'
- conditional compilation [Visual Basic], directives
- '#End if directive [Visual Basic]'
- selective compiling
- else directive (#else)
- '#Else directive [Visual Basic]'
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 884c7ed6f0a346f2d35f01006cea23e47907d13f
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="ifthenelse-directives"></a><span data-ttu-id="576ac-102">#If...Then...#Else 指令</span><span class="sxs-lookup"><span data-stu-id="576ac-102">#If...Then...#Else Directives</span></span>
<span data-ttu-id="576ac-103">有条件地编译选定的 Visual Basic 代码块。</span><span class="sxs-lookup"><span data-stu-id="576ac-103">Conditionally compiles selected blocks of Visual Basic code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="576ac-104">语法</span><span class="sxs-lookup"><span data-stu-id="576ac-104">Syntax</span></span>  
  
```  
#If expression Then  
   statements  
[ #ElseIf expression Then  
   [ statements ]  
...  
#ElseIf expression Then  
   [ statements ] ]  
[ #Else  
   [ statements ] ]  
#End If  
```  
  
## <a name="parts"></a><span data-ttu-id="576ac-105">部件</span><span class="sxs-lookup"><span data-stu-id="576ac-105">Parts</span></span>  
 `expression`  
 <span data-ttu-id="576ac-106">所需的`#If`和`#ElseIf`语句，可选在其他位置。</span><span class="sxs-lookup"><span data-stu-id="576ac-106">Required for `#If` and `#ElseIf` statements, optional elsewhere.</span></span> <span data-ttu-id="576ac-107">任何表达式，以独占方式包含一个或多个条件编译器常量、 文本和运算符，计算结果为`True`或`False`。</span><span class="sxs-lookup"><span data-stu-id="576ac-107">Any expression, consisting exclusively of one or more conditional compiler constants, literals, and operators, that evaluates to `True` or `False`.</span></span>  
  
 `statements`  
 <span data-ttu-id="576ac-108">所需的`#If`语句块，可选在其他位置。</span><span class="sxs-lookup"><span data-stu-id="576ac-108">Required for `#If` statement block, optional elsewhere.</span></span> <span data-ttu-id="576ac-109">Visual Basic 程序线条或如果关联的表达式的计算结果为编译的编译器指令`True`。</span><span class="sxs-lookup"><span data-stu-id="576ac-109">Visual Basic program lines or compiler directives that are compiled if the associated expression evaluates to `True`.</span></span>  
  
 `#End If`  
 <span data-ttu-id="576ac-110">终止`#If`语句块。</span><span class="sxs-lookup"><span data-stu-id="576ac-110">Terminates the `#If` statement block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="576ac-111">备注</span><span class="sxs-lookup"><span data-stu-id="576ac-111">Remarks</span></span>  
 <span data-ttu-id="576ac-112">行为、 表面上`#If...Then...#Else`指令显示相同的为`If...Then...Else`语句。</span><span class="sxs-lookup"><span data-stu-id="576ac-112">On the surface, the behavior of the `#If...Then...#Else` directives appears the same as that of the `If...Then...Else` statements.</span></span> <span data-ttu-id="576ac-113">但是，`#If...Then...#Else`指令评估什么编译的编译器，而`If...Then...Else`语句在运行时计算条件。</span><span class="sxs-lookup"><span data-stu-id="576ac-113">However, the `#If...Then...#Else` directives evaluate what is compiled by the compiler, whereas the `If...Then...Else` statements evaluate conditions at run time.</span></span>  
  
 <span data-ttu-id="576ac-114">条件编译通常用于编译不同平台的同一个程序。</span><span class="sxs-lookup"><span data-stu-id="576ac-114">Conditional compilation is typically used to compile the same program for different platforms.</span></span> <span data-ttu-id="576ac-115">它还用来防止调试可执行文件中显示的代码。</span><span class="sxs-lookup"><span data-stu-id="576ac-115">It is also used to prevent debugging code from appearing in an executable file.</span></span> <span data-ttu-id="576ac-116">在条件编译期间被排除的代码完全省略从最终的可执行文件，因此它具有大小或性能没有影响。</span><span class="sxs-lookup"><span data-stu-id="576ac-116">Code excluded during conditional compilation is completely omitted from the final executable file, so it has no effect on size or performance.</span></span>  
  
 <span data-ttu-id="576ac-117">而不考虑任何评估的结果，将计算所有表达式使用`Option Compare Binary`。</span><span class="sxs-lookup"><span data-stu-id="576ac-117">Regardless of the outcome of any evaluation, all expressions are evaluated using `Option Compare Binary`.</span></span> <span data-ttu-id="576ac-118">`Option Compare`语句不会影响中的表达式`#If`和`#ElseIf`语句。</span><span class="sxs-lookup"><span data-stu-id="576ac-118">The `Option Compare` statement does not affect expressions in `#If` and `#ElseIf` statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="576ac-119">任何单行形式的`#If`， `#Else`， `#ElseIf`，和`#End If`指令存在。</span><span class="sxs-lookup"><span data-stu-id="576ac-119">No single-line form of the `#If`, `#Else`, `#ElseIf`, and `#End If` directives exists.</span></span> <span data-ttu-id="576ac-120">没有其他代码可出现在任何指令所在的行。</span><span class="sxs-lookup"><span data-stu-id="576ac-120">No other code can appear on the same line as any of the directives.</span></span> 

<span data-ttu-id="576ac-121">条件编译块内的语句必须是完整的逻辑语句。</span><span class="sxs-lookup"><span data-stu-id="576ac-121">The statements within a conditional compilation block must be complete logical statements.</span></span> <span data-ttu-id="576ac-122">例如，你不能有条件地编译只有函数的属性，但你可以有条件地声明及其属性以及函数：</span><span class="sxs-lookup"><span data-stu-id="576ac-122">For example, you cannot conditionally compile only the attributes of a function, but you can conditionally declare the function along with its attributes:</span></span>

```vb
   #If DEBUG Then
   <WebMethod()>
   Public Function SomeFunction() As String
   #Else
   <WebMethod(CacheDuration:=86400)>
   Public Function SomeFunction() As String
   #End If
```

## <a name="example"></a><span data-ttu-id="576ac-123">示例</span><span class="sxs-lookup"><span data-stu-id="576ac-123">Example</span></span>
 <span data-ttu-id="576ac-124">此示例使用`#If...Then...#Else`构造来确定是否编译某些语句。</span><span class="sxs-lookup"><span data-stu-id="576ac-124">This example uses the `#If...Then...#Else` construct to determine whether to compile certain statements.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#1](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/if-then-else-directives_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="576ac-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="576ac-125">See Also</span></span>  
[<span data-ttu-id="576ac-126">#Const 指令</span><span class="sxs-lookup"><span data-stu-id="576ac-126">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
[<span data-ttu-id="576ac-127">If...Then...Else 语句</span><span class="sxs-lookup"><span data-stu-id="576ac-127">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
<span data-ttu-id="576ac-128">[条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span><span class="sxs-lookup"><span data-stu-id="576ac-128">[Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span></span>  
<xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>   


