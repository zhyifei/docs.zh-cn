---
title: "对象变量或 With 块变量未设置 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID91
dev_langs:
- VB
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4db2c827c3e77cfa6cc51132f0d647a58c93c769
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="object-variable-or-with-block-variable-not-set"></a><span data-ttu-id="bf30a-102">未设置对象变量或 With 块变量</span><span class="sxs-lookup"><span data-stu-id="bf30a-102">Object variable or With block variable not set</span></span>
<span data-ttu-id="bf30a-103">正在引用无效的对象变量。</span><span class="sxs-lookup"><span data-stu-id="bf30a-103">An invalid object variable is being referenced.</span></span>   <span data-ttu-id="bf30a-104">出现此错误的原因可能有多种：</span><span class="sxs-lookup"><span data-stu-id="bf30a-104">This error can occur for several reasons:</span></span>  
  
-   <span data-ttu-id="bf30a-105">已声明变量，而无需指定一种类型。</span><span class="sxs-lookup"><span data-stu-id="bf30a-105">A variable was declared without specifying a type.</span></span> <span data-ttu-id="bf30a-106">如果不指定类型声明的变量，则默认键入`Object`。</span><span class="sxs-lookup"><span data-stu-id="bf30a-106">If a variable is declared without specifying a type, it defaults to type `Object`.</span></span>  
  
     <span data-ttu-id="bf30a-107">例如，与声明的变量`Dim x`属于类型`Object;`与声明的变量`Dim x As String`属于类型`String`。</span><span class="sxs-lookup"><span data-stu-id="bf30a-107">For example, a variable declared with `Dim x` would be of type `Object;` a variable declared with `Dim x As String` would be of type `String`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="bf30a-108">`Option Strict`语句不允许隐式类型化会导致`Object`类型。</span><span class="sxs-lookup"><span data-stu-id="bf30a-108">The `Option Strict` statement disallows implicit typing that results in an `Object` type.</span></span> <span data-ttu-id="bf30a-109">如果省略该类型时，将发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="bf30a-109">If you omit the type, a compile-time error will occur.</span></span> <span data-ttu-id="bf30a-110">请参阅[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="bf30a-110">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
-   <span data-ttu-id="bf30a-111">您试图引用已被设置为的对象`Nothing`</span><span class="sxs-lookup"><span data-stu-id="bf30a-111">You are attempting to reference an object that has been set to `Nothing`</span></span>  
  
     <span data-ttu-id="bf30a-112">。</span><span class="sxs-lookup"><span data-stu-id="bf30a-112">.</span></span>  
  
-   <span data-ttu-id="bf30a-113">您试图访问未被正确声明一个数组变量中的元素。</span><span class="sxs-lookup"><span data-stu-id="bf30a-113">You are attempting to access an element of an array variable that wasn't properly declared.</span></span>  
  
     <span data-ttu-id="bf30a-114">例如，数组声明为`products() As String`将触发该错误，如果您尝试引用数组的元素`products(3) = "Widget"`。</span><span class="sxs-lookup"><span data-stu-id="bf30a-114">For example, an array declared as `products() As String` will trigger the error if you try to reference an element of the array `products(3) = "Widget"`.</span></span> <span data-ttu-id="bf30a-115">该数组不包含任何元素，将被视为对象。</span><span class="sxs-lookup"><span data-stu-id="bf30a-115">The array has no elements and is treated as an object.</span></span>  
  
-   <span data-ttu-id="bf30a-116">您正尝试访问代码中的`With...End With`阻止在初始化块之前。</span><span class="sxs-lookup"><span data-stu-id="bf30a-116">You are attempting to access code within a `With...End With` block before the block has been initialized.</span></span>   <span data-ttu-id="bf30a-117">一个`With...End With`块必须通过执行初始化`With`语句入口点。</span><span class="sxs-lookup"><span data-stu-id="bf30a-117">A `With...End With` block must be initialized by executing the `With` statement entry point.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf30a-118">在早期版本的 Visual Basic 或 VBA 此错误也由分配给变量的一个值，而无需使用触发`Set`关键字 (`x = "name"`而不是`Set x = "name"`)。</span><span class="sxs-lookup"><span data-stu-id="bf30a-118">In earlier versions of Visual Basic or VBA this error was also triggered by assigning a value to a variable without using the `Set` keyword (`x = "name"` instead of `Set x = "name"`).</span></span> <span data-ttu-id="bf30a-119">`Set`关键字将不再在 Visual Basic.Net 中有效。</span><span class="sxs-lookup"><span data-stu-id="bf30a-119">The `Set` keyword is no longer valid in Visual Basic .Net.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bf30a-120">更正此错误</span><span class="sxs-lookup"><span data-stu-id="bf30a-120">To correct this error</span></span>  
  
1.  <span data-ttu-id="bf30a-121">设置`Option Strict`到`On`通过将以下代码添加到文件的开头︰</span><span class="sxs-lookup"><span data-stu-id="bf30a-121">Set `Option Strict` to `On` by adding the following code to the beginning of the file:</span></span>  
  
```vb  
Option Strict On  
```  

     When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.  
  
2.  <span data-ttu-id="bf30a-122">如果不想要启用`Option Strict`，搜索您的代码是否已指定但无类型的任何变量 (`Dim x`而不是`Dim x As String`) 并将预期的类型添加到声明。</span><span class="sxs-lookup"><span data-stu-id="bf30a-122">If you don't want to enable `Option Strict`, search your code for any variables that were specified without a type (`Dim x` instead of `Dim x As String`) and add the intended type to the declaration.</span></span>  
  
3.  <span data-ttu-id="bf30a-123">请确保不指已被设置为一个对象变量`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="bf30a-123">Make sure you aren't referring to  an object variable that has been set to `Nothing`.</span></span>  <span data-ttu-id="bf30a-124">搜索关键字代码`Nothing`，并修改您的代码，以便该对象未设置为`Nothing`直到后具有引用它。</span><span class="sxs-lookup"><span data-stu-id="bf30a-124">Search your code for the keyword `Nothing`, and revise your code so that the object isn't set to `Nothing` until after you have referenced it.</span></span>  
  
4.  <span data-ttu-id="bf30a-125">请确保任何数组变量就会标注之前访问它们。</span><span class="sxs-lookup"><span data-stu-id="bf30a-125">Make sure that any array  variables are dimensioned before you access them.</span></span> <span data-ttu-id="bf30a-126">首次创建数组时，既可以分配一个维度 (`Dim x(5) As String`而不是`Dim x() As String`)，或使用`ReDim`关键字可以在第一次访问之前设置数组的维数。</span><span class="sxs-lookup"><span data-stu-id="bf30a-126">You can either assign a dimension when you first create the array (`Dim x(5) As String` instead of `Dim x() As String`), or use the `ReDim` keyword to set the dimensions of the array before you first access it.</span></span>  
  
5.  <span data-ttu-id="bf30a-127">请确保您`With`块初始化通过执行`With`语句入口点。</span><span class="sxs-lookup"><span data-stu-id="bf30a-127">Make sure your `With` block is initialized by executing the `With` statement entry point.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf30a-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf30a-128">See Also</span></span>  
 <span data-ttu-id="bf30a-129">[对象变量声明](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="bf30a-129">[Object Variable Declaration](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span></span>  
<span data-ttu-id="bf30a-130"> [ReDim 语句](../../../visual-basic/language-reference/statements/redim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="bf30a-130"> [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) </span></span>  
<span data-ttu-id="bf30a-131"> [With...End With 语句](../../../visual-basic/language-reference/statements/with-end-with-statement.md)</span><span class="sxs-lookup"><span data-stu-id="bf30a-131"> [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md)</span></span>
