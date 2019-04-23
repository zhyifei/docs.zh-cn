---
title: 如何：创建新的变量 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: ee1e93b4e9819992f17738eb024004a4d66210d1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59332581"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="b6fa8-102">如何：创建新的变量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6fa8-102">How to: Create a New Variable (Visual Basic)</span></span>
<span data-ttu-id="b6fa8-103">创建的变量[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="b6fa8-103">You create a variable with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
### <a name="to-create-a-new-variable"></a><span data-ttu-id="b6fa8-104">创建新变量</span><span class="sxs-lookup"><span data-stu-id="b6fa8-104">To create a new variable</span></span>  
  
1. <span data-ttu-id="b6fa8-105">声明中的变量`Dim`语句。</span><span class="sxs-lookup"><span data-stu-id="b6fa8-105">Declare the variable in a `Dim` statement.</span></span>  
  
    ```  
    Dim newCustomer  
    ```  
  
2. <span data-ttu-id="b6fa8-106">包括变量的特征的规范如下所述[私有](../../../../visual-basic/language-reference/modifiers/private.md)，[静态](../../../../visual-basic/language-reference/modifiers/static.md)，[阴影](../../../../visual-basic/language-reference/modifiers/shadows.md)，或者[WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)。</span><span class="sxs-lookup"><span data-stu-id="b6fa8-106">Include specifications for the variable's characteristics, such as [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), or [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="b6fa8-107">有关详细信息，请参阅[声明元素的特性](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)。</span><span class="sxs-lookup"><span data-stu-id="b6fa8-107">For more information, see [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
     <span data-ttu-id="b6fa8-108">不需要`Dim`关键字声明中使用其他关键字。</span><span class="sxs-lookup"><span data-stu-id="b6fa8-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>  
  
3. <span data-ttu-id="b6fa8-109">请按照与变量的名称，必须遵循 Visual Basic 规则和约定规范。</span><span class="sxs-lookup"><span data-stu-id="b6fa8-109">Follow the specifications with the variable's name, which must follow Visual Basic rules and conventions.</span></span> <span data-ttu-id="b6fa8-110">有关详细信息，请参阅[声明的元素名称](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="b6fa8-110">For more information, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
4. <span data-ttu-id="b6fa8-111">名称后接[作为](../../../../visual-basic/language-reference/statements/as-clause.md)子句来指定变量的数据类型。</span><span class="sxs-lookup"><span data-stu-id="b6fa8-111">Follow the name with the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     <span data-ttu-id="b6fa8-112">如果未指定的数据类型，它使用默认值： `Object`。</span><span class="sxs-lookup"><span data-stu-id="b6fa8-112">If you do not specify the data type, it uses the default: `Object`.</span></span>  
  
5. <span data-ttu-id="b6fa8-113">请按照`As`子句以等号 (`=`) 和等号后使用该变量的初始值。</span><span class="sxs-lookup"><span data-stu-id="b6fa8-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>  
  
     <span data-ttu-id="b6fa8-114">Visual Basic 将指定的值分配给变量每次运行时`Dim`语句。</span><span class="sxs-lookup"><span data-stu-id="b6fa8-114">Visual Basic assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="b6fa8-115">如果不指定一个初始值，Visual Basic 时赋给变量的数据类型的默认初始值首次进入包含的代码`Dim`语句。</span><span class="sxs-lookup"><span data-stu-id="b6fa8-115">If you do not specify an initial value, Visual Basic assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>  
  
     <span data-ttu-id="b6fa8-116">如果变量为引用类型，则可以通过包括创建其类的实例[New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)中的关键字`As`子句。</span><span class="sxs-lookup"><span data-stu-id="b6fa8-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="b6fa8-117">如果不使用`New`，该变量的初始值是[Nothing](../../../../visual-basic/language-reference/nothing.md)。</span><span class="sxs-lookup"><span data-stu-id="b6fa8-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b6fa8-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6fa8-118">See also</span></span>

- [<span data-ttu-id="b6fa8-119">变量</span><span class="sxs-lookup"><span data-stu-id="b6fa8-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="b6fa8-120">变量声明</span><span class="sxs-lookup"><span data-stu-id="b6fa8-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="b6fa8-121">已声明的元素名称</span><span class="sxs-lookup"><span data-stu-id="b6fa8-121">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="b6fa8-122">已声明元素的特性</span><span class="sxs-lookup"><span data-stu-id="b6fa8-122">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="b6fa8-123">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="b6fa8-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="b6fa8-124">语句</span><span class="sxs-lookup"><span data-stu-id="b6fa8-124">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
- [<span data-ttu-id="b6fa8-125">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="b6fa8-125">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="b6fa8-126">Option Infer 语句</span><span class="sxs-lookup"><span data-stu-id="b6fa8-126">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
