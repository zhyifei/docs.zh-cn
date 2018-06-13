---
title: 未设置对象变量或 With 块变量
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: b2bd1be83f57dbdc7a64b407dc1052074e19c74b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597658"
---
# <a name="object-variable-or-with-block-variable-not-set"></a><span data-ttu-id="8d957-102">未设置对象变量或 With 块变量</span><span class="sxs-lookup"><span data-stu-id="8d957-102">Object variable or With block variable not set</span></span>
<span data-ttu-id="8d957-103">正在引用无效的对象变量。</span><span class="sxs-lookup"><span data-stu-id="8d957-103">An invalid object variable is being referenced.</span></span>   <span data-ttu-id="8d957-104">出现此错误的原因可能有多种：</span><span class="sxs-lookup"><span data-stu-id="8d957-104">This error can occur for several reasons:</span></span>  
  
-   <span data-ttu-id="8d957-105">如果不指定类型声明了变量。</span><span class="sxs-lookup"><span data-stu-id="8d957-105">A variable was declared without specifying a type.</span></span> <span data-ttu-id="8d957-106">如果不指定类型声明的变量，则默认为类型`Object`。</span><span class="sxs-lookup"><span data-stu-id="8d957-106">If a variable is declared without specifying a type, it defaults to type `Object`.</span></span>  
  
     <span data-ttu-id="8d957-107">例如，与声明的变量`Dim x`类型的作用很`Object;`与声明的变量`Dim x As String`类型的作用很`String`。</span><span class="sxs-lookup"><span data-stu-id="8d957-107">For example, a variable declared with `Dim x` would be of type `Object;` a variable declared with `Dim x As String` would be of type `String`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="8d957-108">`Option Strict`语句不允许隐式类型化导致`Object`类型。</span><span class="sxs-lookup"><span data-stu-id="8d957-108">The `Option Strict` statement disallows implicit typing that results in an `Object` type.</span></span> <span data-ttu-id="8d957-109">如果省略该类型时，将发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="8d957-109">If you omit the type, a compile-time error will occur.</span></span> <span data-ttu-id="8d957-110">请参阅[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="8d957-110">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
-   <span data-ttu-id="8d957-111">你尝试引用已设置为一个对象 `Nothing`</span><span class="sxs-lookup"><span data-stu-id="8d957-111">You are attempting to reference an object that has been set to `Nothing`</span></span>  
  
     <span data-ttu-id="8d957-112">.</span><span class="sxs-lookup"><span data-stu-id="8d957-112">.</span></span>  
  
-   <span data-ttu-id="8d957-113">你尝试访问未正确声明一个数组变量的元素。</span><span class="sxs-lookup"><span data-stu-id="8d957-113">You are attempting to access an element of an array variable that wasn't properly declared.</span></span>  
  
     <span data-ttu-id="8d957-114">例如，数组声明为`products() As String`将触发该错误，如果你尝试引用数组的元素`products(3) = "Widget"`。</span><span class="sxs-lookup"><span data-stu-id="8d957-114">For example, an array declared as `products() As String` will trigger the error if you try to reference an element of the array `products(3) = "Widget"`.</span></span> <span data-ttu-id="8d957-115">数组不包含任何元素，并被视为一个对象。</span><span class="sxs-lookup"><span data-stu-id="8d957-115">The array has no elements and is treated as an object.</span></span>  
  
-   <span data-ttu-id="8d957-116">你正尝试访问代码中`With...End With`阻止在初始化块之前。</span><span class="sxs-lookup"><span data-stu-id="8d957-116">You are attempting to access code within a `With...End With` block before the block has been initialized.</span></span>   <span data-ttu-id="8d957-117">A`With...End With`块必须通过执行初始化`With`语句入口点。</span><span class="sxs-lookup"><span data-stu-id="8d957-117">A `With...End With` block must be initialized by executing the `With` statement entry point.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d957-118">在早期版本的 Visual Basic 或 VBA 此错误也已通过将一个值分配给一个变量，而无需使用触发`Set`关键字 (`x = "name"`而不是`Set x = "name"`)。</span><span class="sxs-lookup"><span data-stu-id="8d957-118">In earlier versions of Visual Basic or VBA this error was also triggered by assigning a value to a variable without using the `Set` keyword (`x = "name"` instead of `Set x = "name"`).</span></span> <span data-ttu-id="8d957-119">`Set`关键字不再是在 Visual Basic.Net 中有效。</span><span class="sxs-lookup"><span data-stu-id="8d957-119">The `Set` keyword is no longer valid in Visual Basic .Net.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8d957-120">更正此错误</span><span class="sxs-lookup"><span data-stu-id="8d957-120">To correct this error</span></span>  
  
1.  <span data-ttu-id="8d957-121">设置`Option Strict`到`On`通过将下面的代码添加到文件的开头：</span><span class="sxs-lookup"><span data-stu-id="8d957-121">Set `Option Strict` to `On` by adding the following code to the beginning of the file:</span></span>  
  
```vb  
Option Strict On  
```  

     When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.  
  
2.  <span data-ttu-id="8d957-122">如果你不想要启用`Option Strict`，搜索你指定没有类型的任何变量的代码 (`Dim x`而不是`Dim x As String`) 并将预期的类型添加到声明。</span><span class="sxs-lookup"><span data-stu-id="8d957-122">If you don't want to enable `Option Strict`, search your code for any variables that were specified without a type (`Dim x` instead of `Dim x As String`) and add the intended type to the declaration.</span></span>  
  
3.  <span data-ttu-id="8d957-123">请确保你已设置为对象变量不引用`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="8d957-123">Make sure you aren't referring to  an object variable that has been set to `Nothing`.</span></span>  <span data-ttu-id="8d957-124">搜索关键字代码`Nothing`，并修改你的代码，以便该对象未设置为`Nothing`直到你在引用它。</span><span class="sxs-lookup"><span data-stu-id="8d957-124">Search your code for the keyword `Nothing`, and revise your code so that the object isn't set to `Nothing` until after you have referenced it.</span></span>  
  
4.  <span data-ttu-id="8d957-125">请确保任何数组变量就会标注之前访问它们。</span><span class="sxs-lookup"><span data-stu-id="8d957-125">Make sure that any array  variables are dimensioned before you access them.</span></span> <span data-ttu-id="8d957-126">你可以将分配一个维度首次创建数组时 (`Dim x(5) As String`而不是`Dim x() As String`)，或使用`ReDim`关键字之前首次访问设置数组的维数。</span><span class="sxs-lookup"><span data-stu-id="8d957-126">You can either assign a dimension when you first create the array (`Dim x(5) As String` instead of `Dim x() As String`), or use the `ReDim` keyword to set the dimensions of the array before you first access it.</span></span>  
  
5.  <span data-ttu-id="8d957-127">请确保你`With`块初始化通过执行`With`语句入口点。</span><span class="sxs-lookup"><span data-stu-id="8d957-127">Make sure your `With` block is initialized by executing the `With` statement entry point.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d957-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d957-128">See Also</span></span>  
 [<span data-ttu-id="8d957-129">对象变量声明</span><span class="sxs-lookup"><span data-stu-id="8d957-129">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="8d957-130">ReDim 语句</span><span class="sxs-lookup"><span data-stu-id="8d957-130">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="8d957-131">With...End With 语句</span><span class="sxs-lookup"><span data-stu-id="8d957-131">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
