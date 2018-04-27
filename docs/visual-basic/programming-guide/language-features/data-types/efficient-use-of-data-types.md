---
title: 有效使用数据类型 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function [Visual Basic], preferred to Asc
- data types [Visual Basic], using efficiently
- optimization [Visual Basic], data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function [Visual Basic], preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4cac585cdc3072d595d2446e1937678f9ab03335
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="0ab4a-102">有效使用数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ab4a-102">Efficient Use of Data Types (Visual Basic)</span></span>
<span data-ttu-id="0ab4a-103">未声明的变量和数据类型未声明的变量分配`Object`数据类型。</span><span class="sxs-lookup"><span data-stu-id="0ab4a-103">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="0ab4a-104">这使得可以轻松快速，编写程序，但它可能会导致它们执行速度更慢。</span><span class="sxs-lookup"><span data-stu-id="0ab4a-104">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>  
  
## <a name="strong-typing"></a><span data-ttu-id="0ab4a-105">强类型</span><span class="sxs-lookup"><span data-stu-id="0ab4a-105">Strong Typing</span></span>  
 <span data-ttu-id="0ab4a-106">指定的所有变量的数据类型被称为*强类型化*。</span><span class="sxs-lookup"><span data-stu-id="0ab4a-106">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="0ab4a-107">使用强类型有多种优点：</span><span class="sxs-lookup"><span data-stu-id="0ab4a-107">Using strong typing has several advantages:</span></span>  
  
-   <span data-ttu-id="0ab4a-108">它使你的变量的 IntelliSense 支持。</span><span class="sxs-lookup"><span data-stu-id="0ab4a-108">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="0ab4a-109">这样，你可以查看其属性和其他成员，作为你的代码中的类型。</span><span class="sxs-lookup"><span data-stu-id="0ab4a-109">This allows you to see their properties and other members as you type in the code.</span></span>  
  
-   <span data-ttu-id="0ab4a-110">它可利用的编译器类型检查。</span><span class="sxs-lookup"><span data-stu-id="0ab4a-110">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="0ab4a-111">这将捕获在运行时由于如溢出错误而导致失败的语句。</span><span class="sxs-lookup"><span data-stu-id="0ab4a-111">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="0ab4a-112">它还不支持这些选项的对象上捕获对方法的调用。</span><span class="sxs-lookup"><span data-stu-id="0ab4a-112">It also catches calls to methods on objects that do not support them.</span></span>  
  
-   <span data-ttu-id="0ab4a-113">这会导致你的代码的执行速度更快。</span><span class="sxs-lookup"><span data-stu-id="0ab4a-113">It results in faster execution of your code.</span></span>  
  
## <a name="most-efficient-data-types"></a><span data-ttu-id="0ab4a-114">最有效的数据类型</span><span class="sxs-lookup"><span data-stu-id="0ab4a-114">Most Efficient Data Types</span></span>  
 <span data-ttu-id="0ab4a-115">从不包含小数的变量，整数数据类型是比非整型类型效率更高。</span><span class="sxs-lookup"><span data-stu-id="0ab4a-115">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="0ab4a-116">在 Visual Basic 中，`Integer`和`UInteger`是最有效的数值类型。</span><span class="sxs-lookup"><span data-stu-id="0ab4a-116">In Visual Basic, `Integer` and `UInteger` are the most efficient numeric types.</span></span>  
  
 <span data-ttu-id="0ab4a-117">对于分数，`Double`是最有效的数据类型，因为在当前平台上的处理器执行以双精度浮点运算。</span><span class="sxs-lookup"><span data-stu-id="0ab4a-117">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="0ab4a-118">但是，与操作`Double`速度与整数类型，例如`Integer`。</span><span class="sxs-lookup"><span data-stu-id="0ab4a-118">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>  
  
## <a name="specifying-data-type"></a><span data-ttu-id="0ab4a-119">指定数据类型</span><span class="sxs-lookup"><span data-stu-id="0ab4a-119">Specifying Data Type</span></span>  
 <span data-ttu-id="0ab4a-120">使用[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)来声明特定类型的变量。</span><span class="sxs-lookup"><span data-stu-id="0ab4a-120">Use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="0ab4a-121">同时可以通过指定其访问级别[公共](../../../../visual-basic/language-reference/modifiers/public.md)，[受保护](../../../../visual-basic/language-reference/modifiers/protected.md)，[友元](../../../../visual-basic/language-reference/modifiers/friend.md)，或[私有](../../../../visual-basic/language-reference/modifiers/private.md)关键字，如下所示下面的示例。</span><span class="sxs-lookup"><span data-stu-id="0ab4a-121">You can simultaneously specify its access level by using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, as in the following example.</span></span>  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a><span data-ttu-id="0ab4a-122">字符转换</span><span class="sxs-lookup"><span data-stu-id="0ab4a-122">Character Conversion</span></span>  
 <span data-ttu-id="0ab4a-123">`AscW`和`ChrW`在 Unicode 函数操作。</span><span class="sxs-lookup"><span data-stu-id="0ab4a-123">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="0ab4a-124">你应使用它们优先`Asc`和`Chr`，执行和跳出执行 Unicode，必须将其转换。</span><span class="sxs-lookup"><span data-stu-id="0ab4a-124">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ab4a-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ab4a-125">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 [<span data-ttu-id="0ab4a-126">数据类型</span><span class="sxs-lookup"><span data-stu-id="0ab4a-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="0ab4a-127">数值数据类型</span><span class="sxs-lookup"><span data-stu-id="0ab4a-127">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [<span data-ttu-id="0ab4a-128">变量声明</span><span class="sxs-lookup"><span data-stu-id="0ab4a-128">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="0ab4a-129">使用 IntelliSense</span><span class="sxs-lookup"><span data-stu-id="0ab4a-129">Using IntelliSense</span></span>](/visualstudio/ide/using-intellisense)
