---
title: 有效使用数据类型 (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: e0cb67b4b26bf59b074bf5964f253c007fdbe719
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54736164"
---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="b3f37-102">有效使用数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3f37-102">Efficient Use of Data Types (Visual Basic)</span></span>
<span data-ttu-id="b3f37-103">未声明的变量和数据类型未声明的变量分配`Object`数据类型。</span><span class="sxs-lookup"><span data-stu-id="b3f37-103">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="b3f37-104">这使得可以轻松编写程序快速，但它可能会导致它们执行速度更慢。</span><span class="sxs-lookup"><span data-stu-id="b3f37-104">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>  
  
## <a name="strong-typing"></a><span data-ttu-id="b3f37-105">强类型化</span><span class="sxs-lookup"><span data-stu-id="b3f37-105">Strong Typing</span></span>  
 <span data-ttu-id="b3f37-106">指定所有变量的数据类型被称为*强类型化*。</span><span class="sxs-lookup"><span data-stu-id="b3f37-106">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="b3f37-107">使用强类型化具有以下优点：</span><span class="sxs-lookup"><span data-stu-id="b3f37-107">Using strong typing has several advantages:</span></span>  
  
-   <span data-ttu-id="b3f37-108">这样，您的变量的 IntelliSense 支持。</span><span class="sxs-lookup"><span data-stu-id="b3f37-108">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="b3f37-109">这样可以查看其属性和其他成员，当你键入的代码。</span><span class="sxs-lookup"><span data-stu-id="b3f37-109">This allows you to see their properties and other members as you type in the code.</span></span>  
  
-   <span data-ttu-id="b3f37-110">它可利用的编译器类型检查。</span><span class="sxs-lookup"><span data-stu-id="b3f37-110">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="b3f37-111">这将捕获在运行时因等溢出错误而失败的语句。</span><span class="sxs-lookup"><span data-stu-id="b3f37-111">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="b3f37-112">不支持它们的对象，它还捕获对方法的调用。</span><span class="sxs-lookup"><span data-stu-id="b3f37-112">It also catches calls to methods on objects that do not support them.</span></span>  
  
-   <span data-ttu-id="b3f37-113">这会导致代码更快地执行。</span><span class="sxs-lookup"><span data-stu-id="b3f37-113">It results in faster execution of your code.</span></span>  
  
## <a name="most-efficient-data-types"></a><span data-ttu-id="b3f37-114">最有效的数据类型</span><span class="sxs-lookup"><span data-stu-id="b3f37-114">Most Efficient Data Types</span></span>  
 <span data-ttu-id="b3f37-115">从不包含小数的变量，整数数据类型是比非整型类型效率更高。</span><span class="sxs-lookup"><span data-stu-id="b3f37-115">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="b3f37-116">在 Visual Basic 中，`Integer`和`UInteger`是最有效的数值类型。</span><span class="sxs-lookup"><span data-stu-id="b3f37-116">In Visual Basic, `Integer` and `UInteger` are the most efficient numeric types.</span></span>  
  
 <span data-ttu-id="b3f37-117">对于分数，`Double`是最有效的数据类型，因为当前平台上的处理器执行以双精度浮点运算。</span><span class="sxs-lookup"><span data-stu-id="b3f37-117">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="b3f37-118">但是，与 operations`Double`不是与整型类型，如一样快`Integer`。</span><span class="sxs-lookup"><span data-stu-id="b3f37-118">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>  
  
## <a name="specifying-data-type"></a><span data-ttu-id="b3f37-119">指定数据类型</span><span class="sxs-lookup"><span data-stu-id="b3f37-119">Specifying Data Type</span></span>  
 <span data-ttu-id="b3f37-120">使用[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)声明特定类型的变量。</span><span class="sxs-lookup"><span data-stu-id="b3f37-120">Use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="b3f37-121">同时可以通过指定其访问级别[公共](../../../../visual-basic/language-reference/modifiers/public.md)，[受保护](../../../../visual-basic/language-reference/modifiers/protected.md)，[友元](../../../../visual-basic/language-reference/modifiers/friend.md)，或者[专用](../../../../visual-basic/language-reference/modifiers/private.md)关键字，如下所示下面的示例。</span><span class="sxs-lookup"><span data-stu-id="b3f37-121">You can simultaneously specify its access level by using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, as in the following example.</span></span>  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a><span data-ttu-id="b3f37-122">字符转换</span><span class="sxs-lookup"><span data-stu-id="b3f37-122">Character Conversion</span></span>  
 <span data-ttu-id="b3f37-123">`AscW`和`ChrW`函数以 unicode 格式进行操作。</span><span class="sxs-lookup"><span data-stu-id="b3f37-123">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="b3f37-124">应使用它们优先于`Asc`和`Chr`，其必须在执行和跳出执行 Unicode 转换。</span><span class="sxs-lookup"><span data-stu-id="b3f37-124">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3f37-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="b3f37-125">See also</span></span>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [<span data-ttu-id="b3f37-126">数据类型</span><span class="sxs-lookup"><span data-stu-id="b3f37-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="b3f37-127">数值数据类型</span><span class="sxs-lookup"><span data-stu-id="b3f37-127">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [<span data-ttu-id="b3f37-128">变量声明</span><span class="sxs-lookup"><span data-stu-id="b3f37-128">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="b3f37-129">使用 IntelliSense</span><span class="sxs-lookup"><span data-stu-id="b3f37-129">Using IntelliSense</span></span>](/visualstudio/ide/using-intellisense)
