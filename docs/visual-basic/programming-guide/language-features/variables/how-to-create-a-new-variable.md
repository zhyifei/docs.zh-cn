---
title: 如何：创建新变量 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aff160584d3d1fe382020d5b8c25ac57dab66d92
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="e31ea-102">如何：创建新变量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e31ea-102">How to: Create a New Variable (Visual Basic)</span></span>
<span data-ttu-id="e31ea-103">创建的变量[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="e31ea-103">You create a variable with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
### <a name="to-create-a-new-variable"></a><span data-ttu-id="e31ea-104">创建新变量</span><span class="sxs-lookup"><span data-stu-id="e31ea-104">To create a new variable</span></span>  
  
1.  <span data-ttu-id="e31ea-105">声明中的变量`Dim`语句。</span><span class="sxs-lookup"><span data-stu-id="e31ea-105">Declare the variable in a `Dim` statement.</span></span>  
  
    ```  
    Dim newCustomer  
    ```  
  
2.  <span data-ttu-id="e31ea-106">包括变量的特征的规范，例如[私有](../../../../visual-basic/language-reference/modifiers/private.md)，[静态](../../../../visual-basic/language-reference/modifiers/static.md)，[阴影](../../../../visual-basic/language-reference/modifiers/shadows.md)，或[WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)。</span><span class="sxs-lookup"><span data-stu-id="e31ea-106">Include specifications for the variable's characteristics, such as [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), or [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="e31ea-107">有关详细信息，请参阅[声明元素的特性](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)。</span><span class="sxs-lookup"><span data-stu-id="e31ea-107">For more information, see [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
     <span data-ttu-id="e31ea-108">不需要`Dim`关键字如果在声明中使用其他关键字。</span><span class="sxs-lookup"><span data-stu-id="e31ea-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>  
  
3.  <span data-ttu-id="e31ea-109">变量的名称，必须遵循 Visual Basic 规则和约定规范后接。</span><span class="sxs-lookup"><span data-stu-id="e31ea-109">Follow the specifications with the variable's name, which must follow Visual Basic rules and conventions.</span></span> <span data-ttu-id="e31ea-110">有关详细信息，请参阅[声明元素名称](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="e31ea-110">For more information, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  <span data-ttu-id="e31ea-111">名后面加上[作为](../../../../visual-basic/language-reference/statements/as-clause.md)子句以指定变量的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e31ea-111">Follow the name with the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     <span data-ttu-id="e31ea-112">如果不指定数据类型，它将使用默认值： `Object`。</span><span class="sxs-lookup"><span data-stu-id="e31ea-112">If you do not specify the data type, it uses the default: `Object`.</span></span>  
  
5.  <span data-ttu-id="e31ea-113">请按照`As`子句以等号 (`=`) 和等号后使用变量的初始值。</span><span class="sxs-lookup"><span data-stu-id="e31ea-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>  
  
     <span data-ttu-id="e31ea-114">Visual Basic 将指定的值分配给变量每次运行时`Dim`语句。</span><span class="sxs-lookup"><span data-stu-id="e31ea-114">Visual Basic assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="e31ea-115">如果不指定初始值，Visual Basic 时赋给变量的数据类型的默认初始值首次进入包含的代码`Dim`语句。</span><span class="sxs-lookup"><span data-stu-id="e31ea-115">If you do not specify an initial value, Visual Basic assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>  
  
     <span data-ttu-id="e31ea-116">如果变量为引用类型，你可以通过包括创建其类的实例[New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)中的关键字`As`子句。</span><span class="sxs-lookup"><span data-stu-id="e31ea-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="e31ea-117">如果不使用`New`，该变量的初始值是[执行任何操作](../../../../visual-basic/language-reference/nothing.md)。</span><span class="sxs-lookup"><span data-stu-id="e31ea-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e31ea-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="e31ea-118">See Also</span></span>  
 [<span data-ttu-id="e31ea-119">变量</span><span class="sxs-lookup"><span data-stu-id="e31ea-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [<span data-ttu-id="e31ea-120">变量声明</span><span class="sxs-lookup"><span data-stu-id="e31ea-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="e31ea-121">已声明的元素名称</span><span class="sxs-lookup"><span data-stu-id="e31ea-121">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="e31ea-122">已声明元素的特性</span><span class="sxs-lookup"><span data-stu-id="e31ea-122">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [<span data-ttu-id="e31ea-123">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="e31ea-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="e31ea-124">语句</span><span class="sxs-lookup"><span data-stu-id="e31ea-124">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)  
 [<span data-ttu-id="e31ea-125">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="e31ea-125">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="e31ea-126">Option Infer 语句</span><span class="sxs-lookup"><span data-stu-id="e31ea-126">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
