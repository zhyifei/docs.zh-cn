---
title: 变量
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
ms.openlocfilehash: 26433acea2b98ad0e67b9c35bec4eb8e88f7b7b6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352415"
---
# <a name="variables-in-visual-basic"></a><span data-ttu-id="9235a-102">变量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9235a-102">Variables in Visual Basic</span></span>
<span data-ttu-id="9235a-103">使用 Visual Basic 执行计算时，通常需要存储值。</span><span class="sxs-lookup"><span data-stu-id="9235a-103">You often have to store values when you perform calculations with Visual Basic.</span></span> <span data-ttu-id="9235a-104">例如，可能需要计算、比较多个值，并根据比较结果对这些值执行不同的运算。</span><span class="sxs-lookup"><span data-stu-id="9235a-104">For example, you might want to calculate several values, compare them, and perform different operations on them, depending on the result of the comparison.</span></span> <span data-ttu-id="9235a-105">若要进行比较，必须保留这些值。</span><span class="sxs-lookup"><span data-stu-id="9235a-105">You have to retain the values if you want to compare them.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="9235a-106">用法</span><span class="sxs-lookup"><span data-stu-id="9235a-106">Usage</span></span>  
 <span data-ttu-id="9235a-107">与大多数编程语言一样，Visual Basic 使用变量来存储值。</span><span class="sxs-lookup"><span data-stu-id="9235a-107">Visual Basic, just like most programming languages, uses variables for storing values.</span></span> <span data-ttu-id="9235a-108">变量有名称（用于引用变量中值的词语）。</span><span class="sxs-lookup"><span data-stu-id="9235a-108">A *variable* has a name (the word that you use to refer to the value that the variable contains).</span></span> <span data-ttu-id="9235a-109">变量还具有数据类型（用于确定变量可存储的数据种类）。</span><span class="sxs-lookup"><span data-stu-id="9235a-109">A variable also has a data type (which determines the kind of data that the variable can store).</span></span> <span data-ttu-id="9235a-110">如果变量需要存储一组密切相关的索引数据项，可以表示数组。</span><span class="sxs-lookup"><span data-stu-id="9235a-110">A variable can represent an array if it has to store an indexed set of closely related data items.</span></span>  
  
 <span data-ttu-id="9235a-111">使用本地类型推断，可以声明变量，而无需显式声明数据类型。</span><span class="sxs-lookup"><span data-stu-id="9235a-111">Local type inference enables you to declare variables without explicitly stating a data type.</span></span> <span data-ttu-id="9235a-112">相反，编译器将通过初始化表达式的类型推断出变量的类型。</span><span class="sxs-lookup"><span data-stu-id="9235a-112">Instead, the compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="9235a-113">有关详细信息，请参阅[本地类型推断](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)和 [Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="9235a-113">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) and [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="assigning-values"></a><span data-ttu-id="9235a-114">赋值</span><span class="sxs-lookup"><span data-stu-id="9235a-114">Assigning Values</span></span>  
 <span data-ttu-id="9235a-115">使用赋值语句执行计算，并将结果赋给变量，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="9235a-115">You use assignment statements to perform calculations and assign the result to a variable, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrVariables#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrVariables/VB/Class1.vb#1)]  
  
> [!NOTE]
> <span data-ttu-id="9235a-116">在此示例中，等于号 (`=`) 为赋值运算符，而不是相等运算符。</span><span class="sxs-lookup"><span data-stu-id="9235a-116">The equal sign (`=`) in this example is an assignment operator, not an equality operator.</span></span> <span data-ttu-id="9235a-117">值会赋给变量 `applesSold`。</span><span class="sxs-lookup"><span data-stu-id="9235a-117">The value is being assigned to the variable `applesSold`.</span></span>  
  
 <span data-ttu-id="9235a-118">有关详细信息，请参阅[如何：将数据移入和移出变量](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)。</span><span class="sxs-lookup"><span data-stu-id="9235a-118">For more information, see [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).</span></span>  
  
## <a name="variables-and-properties"></a><span data-ttu-id="9235a-119">变量和属性</span><span class="sxs-lookup"><span data-stu-id="9235a-119">Variables and Properties</span></span>  
 <span data-ttu-id="9235a-120">与变量一样，属性表示可访问的值。</span><span class="sxs-lookup"><span data-stu-id="9235a-120">Like a variable, a *property* represents a value that you can access.</span></span> <span data-ttu-id="9235a-121">不过，它比变量更复杂。</span><span class="sxs-lookup"><span data-stu-id="9235a-121">However, it is more complex than a variable.</span></span> <span data-ttu-id="9235a-122">属性使用代码块来控制如何设置并检索值。</span><span class="sxs-lookup"><span data-stu-id="9235a-122">A property uses code blocks that control how to set and retrieve its value.</span></span> <span data-ttu-id="9235a-123">有关详细信息，请参阅 [Visual Basic 中属性和变量的差异](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)。</span><span class="sxs-lookup"><span data-stu-id="9235a-123">For more information, see [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9235a-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9235a-124">See also</span></span>

- [<span data-ttu-id="9235a-125">变量声明</span><span class="sxs-lookup"><span data-stu-id="9235a-125">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="9235a-126">对象变量</span><span class="sxs-lookup"><span data-stu-id="9235a-126">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="9235a-127">变量疑难解答</span><span class="sxs-lookup"><span data-stu-id="9235a-127">Troubleshooting Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
- [<span data-ttu-id="9235a-128">如何：将数据移入和移出变量</span><span class="sxs-lookup"><span data-stu-id="9235a-128">How to: Move Data Into and Out of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)
- [<span data-ttu-id="9235a-129">Visual Basic 中的属性和变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="9235a-129">Differences Between Properties and Variables in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)
- [<span data-ttu-id="9235a-130">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="9235a-130">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
