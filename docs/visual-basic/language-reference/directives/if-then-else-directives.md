---
title: '#If .。。Then ... #Else 指令 (Visual Basic)'
ms.date: 04/11/2018
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
ms.openlocfilehash: 697521276e2d5a8d0a4aaae38789a21b7aa87fcb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940761"
---
# <a name="ifthenelse-directives"></a><span data-ttu-id="3c0c1-102">#If...Then...#Else 指令</span><span class="sxs-lookup"><span data-stu-id="3c0c1-102">#If...Then...#Else Directives</span></span>
<span data-ttu-id="3c0c1-103">有条件地编译选定的 Visual Basic 代码块。</span><span class="sxs-lookup"><span data-stu-id="3c0c1-103">Conditionally compiles selected blocks of Visual Basic code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c0c1-104">语法</span><span class="sxs-lookup"><span data-stu-id="3c0c1-104">Syntax</span></span>  
  
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
  
## <a name="parts"></a><span data-ttu-id="3c0c1-105">部件</span><span class="sxs-lookup"><span data-stu-id="3c0c1-105">Parts</span></span>  
 `expression`  
 <span data-ttu-id="3c0c1-106">对于和`#If` `#ElseIf`语句是必需的, 在其他位置为可选。</span><span class="sxs-lookup"><span data-stu-id="3c0c1-106">Required for `#If` and `#ElseIf` statements, optional elsewhere.</span></span> <span data-ttu-id="3c0c1-107">任何表达式 (仅由一个或多个条件编译器常量、文本和运算符组成), 其计算`True`结果`False`为或。</span><span class="sxs-lookup"><span data-stu-id="3c0c1-107">Any expression, consisting exclusively of one or more conditional compiler constants, literals, and operators, that evaluates to `True` or `False`.</span></span>  
  
 `statements`  
 <span data-ttu-id="3c0c1-108">语句块`#If`必需, 在其他位置为可选。</span><span class="sxs-lookup"><span data-stu-id="3c0c1-108">Required for `#If` statement block, optional elsewhere.</span></span> <span data-ttu-id="3c0c1-109">如果关联的表达式的计算结果为`True`, 则 Visual Basic 编译的程序行或编译器指令。</span><span class="sxs-lookup"><span data-stu-id="3c0c1-109">Visual Basic program lines or compiler directives that are compiled if the associated expression evaluates to `True`.</span></span>  
  
 `#End If`  
 <span data-ttu-id="3c0c1-110">`#If`终止语句块。</span><span class="sxs-lookup"><span data-stu-id="3c0c1-110">Terminates the `#If` statement block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c0c1-111">备注</span><span class="sxs-lookup"><span data-stu-id="3c0c1-111">Remarks</span></span>  
 <span data-ttu-id="3c0c1-112">在表面上, `#If...Then...#Else`指令的行为将与`If...Then...Else`语句的行为相同。</span><span class="sxs-lookup"><span data-stu-id="3c0c1-112">On the surface, the behavior of the `#If...Then...#Else` directives appears the same as that of the `If...Then...Else` statements.</span></span> <span data-ttu-id="3c0c1-113">但是, `#If...Then...#Else`指令将计算编译器编译的内容, `If...Then...Else`而语句则计算运行时的条件。</span><span class="sxs-lookup"><span data-stu-id="3c0c1-113">However, the `#If...Then...#Else` directives evaluate what is compiled by the compiler, whereas the `If...Then...Else` statements evaluate conditions at run time.</span></span>  
  
 <span data-ttu-id="3c0c1-114">条件编译通常用于针对不同平台编译相同的程序。</span><span class="sxs-lookup"><span data-stu-id="3c0c1-114">Conditional compilation is typically used to compile the same program for different platforms.</span></span> <span data-ttu-id="3c0c1-115">它还用于阻止调试代码出现在可执行文件中。</span><span class="sxs-lookup"><span data-stu-id="3c0c1-115">It is also used to prevent debugging code from appearing in an executable file.</span></span> <span data-ttu-id="3c0c1-116">在条件编译期间排除的代码在最终可执行文件中被完全省略, 因此它不会对大小或性能产生任何影响。</span><span class="sxs-lookup"><span data-stu-id="3c0c1-116">Code excluded during conditional compilation is completely omitted from the final executable file, so it has no effect on size or performance.</span></span>  
  
 <span data-ttu-id="3c0c1-117">不管任何计算结果如何, 都将使用`Option Compare Binary`计算所有表达式。</span><span class="sxs-lookup"><span data-stu-id="3c0c1-117">Regardless of the outcome of any evaluation, all expressions are evaluated using `Option Compare Binary`.</span></span> <span data-ttu-id="3c0c1-118">语句`Option Compare`不影响和`#ElseIf`语句中`#If`的表达式。</span><span class="sxs-lookup"><span data-stu-id="3c0c1-118">The `Option Compare` statement does not affect expressions in `#If` and `#ElseIf` statements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3c0c1-119">`#If`不存在`#Else` 、、和`#End If`指令的单行形式。 `#ElseIf`</span><span class="sxs-lookup"><span data-stu-id="3c0c1-119">No single-line form of the `#If`, `#Else`, `#ElseIf`, and `#End If` directives exists.</span></span> <span data-ttu-id="3c0c1-120">任何其他代码都不能与任何指令出现在同一行上。</span><span class="sxs-lookup"><span data-stu-id="3c0c1-120">No other code can appear on the same line as any of the directives.</span></span> 

<span data-ttu-id="3c0c1-121">条件编译块内的语句必须是完整的逻辑语句。</span><span class="sxs-lookup"><span data-stu-id="3c0c1-121">The statements within a conditional compilation block must be complete logical statements.</span></span> <span data-ttu-id="3c0c1-122">例如, 你无法有条件地仅编译函数的属性, 但你可以有条件地声明函数及其属性:</span><span class="sxs-lookup"><span data-stu-id="3c0c1-122">For example, you cannot conditionally compile only the attributes of a function, but you can conditionally declare the function along with its attributes:</span></span>

```vb
   #If DEBUG Then
   <WebMethod()>
   Public Function SomeFunction() As String
   #Else
   <WebMethod(CacheDuration:=86400)>
   Public Function SomeFunction() As String
   #End If
```

## <a name="example"></a><span data-ttu-id="3c0c1-123">示例</span><span class="sxs-lookup"><span data-stu-id="3c0c1-123">Example</span></span>
 <span data-ttu-id="3c0c1-124">此示例使用`#If...Then...#Else`构造来确定是否编译某些语句。</span><span class="sxs-lookup"><span data-stu-id="3c0c1-124">This example uses the `#If...Then...#Else` construct to determine whether to compile certain statements.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3c0c1-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c0c1-125">See also</span></span>

- [<span data-ttu-id="3c0c1-126">#Const 指令</span><span class="sxs-lookup"><span data-stu-id="3c0c1-126">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="3c0c1-127">If...Then...Else 语句</span><span class="sxs-lookup"><span data-stu-id="3c0c1-127">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="3c0c1-128">条件编译</span><span class="sxs-lookup"><span data-stu-id="3c0c1-128">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>
