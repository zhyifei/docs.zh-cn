---
title: "有效使用数据类型 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function, preferred to Asc
- data types [Visual Basic], using efficiently
- optimization, data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function, preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ca8d5885aea12a3f1f9cb35f08bf63c1a89e7ebc
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="c3fbe-102">有效使用数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3fbe-102">Efficient Use of Data Types (Visual Basic)</span></span>
<span data-ttu-id="c3fbe-103">未声明的变量和数据类型未声明的变量分配`Object`数据类型。</span><span class="sxs-lookup"><span data-stu-id="c3fbe-103">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="c3fbe-104">这使得更易于编写的程序速度快，但这样会导致执行速度更慢。</span><span class="sxs-lookup"><span data-stu-id="c3fbe-104">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>  
  
## <a name="strong-typing"></a><span data-ttu-id="c3fbe-105">强类型</span><span class="sxs-lookup"><span data-stu-id="c3fbe-105">Strong Typing</span></span>  
 <span data-ttu-id="c3fbe-106">指定为所有变量的数据类型被称为*强类型化*。</span><span class="sxs-lookup"><span data-stu-id="c3fbe-106">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="c3fbe-107">使用强类型化有几个优点︰</span><span class="sxs-lookup"><span data-stu-id="c3fbe-107">Using strong typing has several advantages:</span></span>  
  
-   <span data-ttu-id="c3fbe-108">它使您的变量的 IntelliSense 支持。</span><span class="sxs-lookup"><span data-stu-id="c3fbe-108">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="c3fbe-109">这样，您可以在代码中键入时看到它们的属性和其他成员。</span><span class="sxs-lookup"><span data-stu-id="c3fbe-109">This allows you to see their properties and other members as you type in the code.</span></span>  
  
-   <span data-ttu-id="c3fbe-110">它可利用的编译器类型检查。</span><span class="sxs-lookup"><span data-stu-id="c3fbe-110">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="c3fbe-111">这将捕获在运行时由于如溢出错误而失败的语句。</span><span class="sxs-lookup"><span data-stu-id="c3fbe-111">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="c3fbe-112">不支持它们的对象，它还捕获对方法的调用。</span><span class="sxs-lookup"><span data-stu-id="c3fbe-112">It also catches calls to methods on objects that do not support them.</span></span>  
  
-   <span data-ttu-id="c3fbe-113">这会导致更快地执行代码。</span><span class="sxs-lookup"><span data-stu-id="c3fbe-113">It results in faster execution of your code.</span></span>  
  
## <a name="most-efficient-data-types"></a><span data-ttu-id="c3fbe-114">最高效的数据类型</span><span class="sxs-lookup"><span data-stu-id="c3fbe-114">Most Efficient Data Types</span></span>  
 <span data-ttu-id="c3fbe-115">对于永远不会包含秒的小数部分的变量，整数数据类型将比非整型更加有效。</span><span class="sxs-lookup"><span data-stu-id="c3fbe-115">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="c3fbe-116">在[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]，`Integer`和`UInteger`是最有效的数值类型。</span><span class="sxs-lookup"><span data-stu-id="c3fbe-116">In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], `Integer` and `UInteger` are the most efficient numeric types.</span></span>  
  
 <span data-ttu-id="c3fbe-117">对于分数，`Double`是最有效的数据类型，因为当前平台上的处理器执行以双精度浮点运算。</span><span class="sxs-lookup"><span data-stu-id="c3fbe-117">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="c3fbe-118">但是，操作与`Double`与整数类型，如速度快`Integer`。</span><span class="sxs-lookup"><span data-stu-id="c3fbe-118">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>  
  
## <a name="specifying-data-type"></a><span data-ttu-id="c3fbe-119">指定数据类型</span><span class="sxs-lookup"><span data-stu-id="c3fbe-119">Specifying Data Type</span></span>  
 <span data-ttu-id="c3fbe-120">使用[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)来声明某个特定类型的变量。</span><span class="sxs-lookup"><span data-stu-id="c3fbe-120">Use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="c3fbe-121">同时可以通过指定其访问级别[公共](../../../../visual-basic/language-reference/modifiers/public.md)，[受保护](../../../../visual-basic/language-reference/modifiers/protected.md)，[朋友](../../../../visual-basic/language-reference/modifiers/friend.md)，或[专用](../../../../visual-basic/language-reference/modifiers/private.md)关键字，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="c3fbe-121">You can simultaneously specify its access level by using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, as in the following example.</span></span>  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a><span data-ttu-id="c3fbe-122">字符转换</span><span class="sxs-lookup"><span data-stu-id="c3fbe-122">Character Conversion</span></span>  
 <span data-ttu-id="c3fbe-123">`AscW`和`ChrW`函数以 unicode 格式进行操作。</span><span class="sxs-lookup"><span data-stu-id="c3fbe-123">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="c3fbe-124">您应使用这些优先`Asc`和`Chr`，它必须在执行和跳出执行 Unicode 转换。</span><span class="sxs-lookup"><span data-stu-id="c3fbe-124">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3fbe-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3fbe-125">See Also</span></span>  
 <span data-ttu-id="c3fbe-126"><xref:Microsoft.VisualBasic.Strings.Asc%2A></xref:Microsoft.VisualBasic.Strings.Asc%2A></span><span class="sxs-lookup"><span data-stu-id="c3fbe-126"><xref:Microsoft.VisualBasic.Strings.Asc%2A></span></span>   
 <span data-ttu-id="c3fbe-127"><xref:Microsoft.VisualBasic.Strings.AscW%2A></xref:Microsoft.VisualBasic.Strings.AscW%2A></span><span class="sxs-lookup"><span data-stu-id="c3fbe-127"><xref:Microsoft.VisualBasic.Strings.AscW%2A></span></span>   
 <span data-ttu-id="c3fbe-128"><xref:Microsoft.VisualBasic.Strings.Chr%2A></xref:Microsoft.VisualBasic.Strings.Chr%2A></span><span class="sxs-lookup"><span data-stu-id="c3fbe-128"><xref:Microsoft.VisualBasic.Strings.Chr%2A></span></span>   
 <span data-ttu-id="c3fbe-129"><xref:Microsoft.VisualBasic.Strings.ChrW%2A></xref:Microsoft.VisualBasic.Strings.ChrW%2A></span><span class="sxs-lookup"><span data-stu-id="c3fbe-129"><xref:Microsoft.VisualBasic.Strings.ChrW%2A></span></span>   
<span data-ttu-id="c3fbe-130"> [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="c3fbe-130"> [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="c3fbe-131"> [数值数据类型](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="c3fbe-131"> [Numeric Data Types](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md) </span></span>  
<span data-ttu-id="c3fbe-132"> [变量声明](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="c3fbe-132"> [Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="c3fbe-133"> [使用 IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense)</span><span class="sxs-lookup"><span data-stu-id="c3fbe-133"> [Using IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense)</span></span>
