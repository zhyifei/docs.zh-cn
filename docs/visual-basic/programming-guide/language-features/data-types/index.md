---
title: "Visual Basic 中的数据类型"
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
- data types [Visual Basic], declaring
- typing
- data types [Visual Basic]
- Visual Basic code, data types
- data types [Visual Basic], improving speed with
ms.assetid: 5e1b9aaf-c7ca-4b29-9b22-0e82ed8e85e2
caps.latest.revision: 28
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8b90a5e58d135a3769761ca431fd0c05f79e045f
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="data-types-in-visual-basic"></a><span data-ttu-id="a72eb-102">Visual Basic 中的数据类型</span><span class="sxs-lookup"><span data-stu-id="a72eb-102">Data Types in Visual Basic</span></span>
<span data-ttu-id="a72eb-103">编程元素的*数据类型*是指可以保留的数据种类以及相应类型数据的存储方式。</span><span class="sxs-lookup"><span data-stu-id="a72eb-103">The *data type* of a programming element refers to what kind of data it can hold and how it stores that data.</span></span> <span data-ttu-id="a72eb-104">数据类型适用于所有可以存储到计算机内存中或参与表达式求值的值。</span><span class="sxs-lookup"><span data-stu-id="a72eb-104">Data types apply to all values that can be stored in computer memory or participate in the evaluation of an expression.</span></span> <span data-ttu-id="a72eb-105">每个变量、文本、常量、枚举、属性、过程参数、过程自变量和过程返回值都有对应的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a72eb-105">Every variable, literal, constant, enumeration, property, procedure parameter, procedure argument, and procedure return value has a data type.</span></span>  
  
## <a name="declared-data-types"></a><span data-ttu-id="a72eb-106">已声明的数据类型</span><span class="sxs-lookup"><span data-stu-id="a72eb-106">Declared Data Types</span></span>  
 <span data-ttu-id="a72eb-107">可以使用声明语句定义编程元素，并使用 `As` 子句指定其数据类型。</span><span class="sxs-lookup"><span data-stu-id="a72eb-107">You define a programming element with a declaration statement, and you specify its data type with the `As` clause.</span></span> <span data-ttu-id="a72eb-108">下表列出了用于声明各种元素的语句。</span><span class="sxs-lookup"><span data-stu-id="a72eb-108">The following table shows the statements you use to declare various elements.</span></span>  
  
|<span data-ttu-id="a72eb-109">编程元素</span><span class="sxs-lookup"><span data-stu-id="a72eb-109">Programming element</span></span>|<span data-ttu-id="a72eb-110">数据类型声明</span><span class="sxs-lookup"><span data-stu-id="a72eb-110">Data type declaration</span></span>|  
|-------------------------|---------------------------|  
|<span data-ttu-id="a72eb-111">变量</span><span class="sxs-lookup"><span data-stu-id="a72eb-111">Variable</span></span>|<span data-ttu-id="a72eb-112">使用 [Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="a72eb-112">In a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)</span></span><br /><br /> <span data-ttu-id="a72eb-113">`Dim`   `amount As Double`</span><span class="sxs-lookup"><span data-stu-id="a72eb-113">`Dim`   `amount As Double`</span></span><br /><br /> <span data-ttu-id="a72eb-114">`Static`   `yourName As String`</span><span class="sxs-lookup"><span data-stu-id="a72eb-114">`Static`   `yourName As String`</span></span><br /><br /> <span data-ttu-id="a72eb-115">`Public`   `billsPaid As Decimal = 0`</span><span class="sxs-lookup"><span data-stu-id="a72eb-115">`Public`   `billsPaid As Decimal = 0`</span></span>|  
|<span data-ttu-id="a72eb-116">Literal</span><span class="sxs-lookup"><span data-stu-id="a72eb-116">Literal</span></span>|<span data-ttu-id="a72eb-117">含文本类型字符；请参阅[类型字符](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)中的“文本类型字符”</span><span class="sxs-lookup"><span data-stu-id="a72eb-117">With a literal type character; see "Literal Type Characters" in [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span></span><br /><br /> <span data-ttu-id="a72eb-118">`Dim searchChar As Char = "."`  `C`</span><span class="sxs-lookup"><span data-stu-id="a72eb-118">`Dim searchChar As Char = "."`  `C`</span></span>|  
|<span data-ttu-id="a72eb-119">常量</span><span class="sxs-lookup"><span data-stu-id="a72eb-119">Constant</span></span>|<span data-ttu-id="a72eb-120">使用 [Const 语句](../../../../visual-basic/language-reference/statements/const-statement.md)</span><span class="sxs-lookup"><span data-stu-id="a72eb-120">In a [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md)</span></span><br /><br /> <span data-ttu-id="a72eb-121">`Const`   `modulus As Single = 4.17825F`</span><span class="sxs-lookup"><span data-stu-id="a72eb-121">`Const`   `modulus As Single = 4.17825F`</span></span>|  
|<span data-ttu-id="a72eb-122">枚举</span><span class="sxs-lookup"><span data-stu-id="a72eb-122">Enumeration</span></span>|<span data-ttu-id="a72eb-123">使用 [Enum 语句](../../../../visual-basic/language-reference/statements/enum-statement.md)</span><span class="sxs-lookup"><span data-stu-id="a72eb-123">In an [Enum Statement](../../../../visual-basic/language-reference/statements/enum-statement.md)</span></span><br /><br /> <span data-ttu-id="a72eb-124">`Public`   `Enum`   `colors`</span><span class="sxs-lookup"><span data-stu-id="a72eb-124">`Public`   `Enum`   `colors`</span></span>|  
|<span data-ttu-id="a72eb-125">属性</span><span class="sxs-lookup"><span data-stu-id="a72eb-125">Property</span></span>|<span data-ttu-id="a72eb-126">使用 [Property 语句](../../../../visual-basic/language-reference/statements/property-statement.md)</span><span class="sxs-lookup"><span data-stu-id="a72eb-126">In a [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)</span></span><br /><br /> <span data-ttu-id="a72eb-127">`Property`   `region() As String`</span><span class="sxs-lookup"><span data-stu-id="a72eb-127">`Property`   `region() As String`</span></span>|  
|<span data-ttu-id="a72eb-128">过程参数</span><span class="sxs-lookup"><span data-stu-id="a72eb-128">Procedure parameter</span></span>|<span data-ttu-id="a72eb-129">使用 [Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md)、[Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)或 [Operator 语句](../../../../visual-basic/language-reference/statements/operator-statement.md)</span><span class="sxs-lookup"><span data-stu-id="a72eb-129">In a [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md), [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md), or [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)</span></span><br /><br /> <span data-ttu-id="a72eb-130">`Sub addSale(ByVal`   `amount`   `As Double)`</span><span class="sxs-lookup"><span data-stu-id="a72eb-130">`Sub addSale(ByVal`   `amount`   `As Double)`</span></span>|  
|<span data-ttu-id="a72eb-131">过程自变量</span><span class="sxs-lookup"><span data-stu-id="a72eb-131">Procedure argument</span></span>|<span data-ttu-id="a72eb-132">在调用的代码中；每个自变量都是一个已声明的编程元素或包含已声明元素的表达式</span><span class="sxs-lookup"><span data-stu-id="a72eb-132">In the calling code; each argument is a programming element that has already been declared, or an expression containing declared elements</span></span><br /><br /> <span data-ttu-id="a72eb-133">`subString = Left(`  `inputString`  `,`   `5`  `)`</span><span class="sxs-lookup"><span data-stu-id="a72eb-133">`subString = Left(`  `inputString`  `,`   `5`  `)`</span></span>|  
|<span data-ttu-id="a72eb-134">过程返回值</span><span class="sxs-lookup"><span data-stu-id="a72eb-134">Procedure return value</span></span>|<span data-ttu-id="a72eb-135">使用 [Function 语句](../../../../visual-basic/language-reference/statements/function-statement.md)或 [Operator 语句](../../../../visual-basic/language-reference/statements/operator-statement.md)</span><span class="sxs-lookup"><span data-stu-id="a72eb-135">In a [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) or [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)</span></span><br /><br /> <span data-ttu-id="a72eb-136">`Function convert(ByVal b As Byte)`   `As String`</span><span class="sxs-lookup"><span data-stu-id="a72eb-136">`Function convert(ByVal b As Byte)`   `As String`</span></span>|  
  
 <span data-ttu-id="a72eb-137">有关 Visual Basic 数据类型的列表，请参阅[数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md)。</span><span class="sxs-lookup"><span data-stu-id="a72eb-137">For a list of Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a72eb-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a72eb-138">See Also</span></span>  
 <span data-ttu-id="a72eb-139">[类型字符](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span><span class="sxs-lookup"><span data-stu-id="a72eb-139">[Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span></span>  
 <span data-ttu-id="a72eb-140">[基本数据类型](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="a72eb-140">[Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
 <span data-ttu-id="a72eb-141">[复合数据类型](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="a72eb-141">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span></span>  
 <span data-ttu-id="a72eb-142">[Visual Basic 中的泛型类型](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="a72eb-142">[Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span></span>  
 <span data-ttu-id="a72eb-143">[值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="a72eb-143">[Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
 <span data-ttu-id="a72eb-144">[Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="a72eb-144">[Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
 <span data-ttu-id="a72eb-145">[结构](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span><span class="sxs-lookup"><span data-stu-id="a72eb-145">[Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span></span>  
 <span data-ttu-id="a72eb-146">[元组](tuples.md)   </span><span class="sxs-lookup"><span data-stu-id="a72eb-146">[Tuples](tuples.md)   </span></span>  
 <span data-ttu-id="a72eb-147">[数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="a72eb-147">[Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
 <span data-ttu-id="a72eb-148">[数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="a72eb-148">[Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
 [<span data-ttu-id="a72eb-149">有效使用数据类型</span><span class="sxs-lookup"><span data-stu-id="a72eb-149">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

