---
title: "对象变量值 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- object variables, values
- values, of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
caps.latest.revision: 18
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
ms.openlocfilehash: 5f42706a79212ae523b08ee336fdcacb3f761af6
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="object-variable-values-visual-basic"></a><span data-ttu-id="064f6-102">对象变量值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="064f6-102">Object Variable Values (Visual Basic)</span></span>
<span data-ttu-id="064f6-103">变量[Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)可以引用任何类型的数据。</span><span class="sxs-lookup"><span data-stu-id="064f6-103">A variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) can refer to data of any type.</span></span> <span data-ttu-id="064f6-104">在中存储的值`Object`变量被保存别处在内存中，而变量本身保存到数据指针。</span><span class="sxs-lookup"><span data-stu-id="064f6-104">The value you store in an `Object` variable is kept elsewhere in memory, while the variable itself holds a pointer to the data.</span></span>  
  
## <a name="object-classifier-functions"></a><span data-ttu-id="064f6-105">对象分类器函数</span><span class="sxs-lookup"><span data-stu-id="064f6-105">Object Classifier Functions</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="064f6-106">提供的函数可返回有关新增功能的信息`Object`变量所引用下, 表中所示。</span><span class="sxs-lookup"><span data-stu-id="064f6-106"> supplies functions that return information about what an `Object` variable refers to, as shown in the following table.</span></span>  
  
|<span data-ttu-id="064f6-107">函数</span><span class="sxs-lookup"><span data-stu-id="064f6-107">Function</span></span>|<span data-ttu-id="064f6-108">如果对象变量引用的则返回 True</span><span class="sxs-lookup"><span data-stu-id="064f6-108">Returns True if the Object variable refers to</span></span>|  
|--------------|---------------------------------------------------|  
|<span data-ttu-id="064f6-109"><xref:Microsoft.VisualBasic.Information.IsArray%2A></xref:Microsoft.VisualBasic.Information.IsArray%2A></span><span class="sxs-lookup"><span data-stu-id="064f6-109"><xref:Microsoft.VisualBasic.Information.IsArray%2A></span></span>|<span data-ttu-id="064f6-110">一个值，而不是单个值的数组</span><span class="sxs-lookup"><span data-stu-id="064f6-110">An array of values, rather than a single value</span></span>|  
|<span data-ttu-id="064f6-111"><xref:Microsoft.VisualBasic.Information.IsDate%2A></xref:Microsoft.VisualBasic.Information.IsDate%2A></span><span class="sxs-lookup"><span data-stu-id="064f6-111"><xref:Microsoft.VisualBasic.Information.IsDate%2A></span></span>|<span data-ttu-id="064f6-112">一个[Date 数据类型](../../../../visual-basic/language-reference/data-types/date-data-type.md)值或可以解释为日期和时间值的字符串</span><span class="sxs-lookup"><span data-stu-id="064f6-112">A [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) value, or a string that can be interpreted as a date and time value</span></span>|  
|<span data-ttu-id="064f6-113"><xref:Microsoft.VisualBasic.Information.IsDBNull%2A></xref:Microsoft.VisualBasic.Information.IsDBNull%2A></span><span class="sxs-lookup"><span data-stu-id="064f6-113"><xref:Microsoft.VisualBasic.Information.IsDBNull%2A></span></span>|<span data-ttu-id="064f6-114">一个对象类型<xref:System.DBNull>，这表示缺少或不存在的数据</xref:System.DBNull></span><span class="sxs-lookup"><span data-stu-id="064f6-114">An object of type <xref:System.DBNull>, which represents missing or nonexistent data</span></span>|  
|<span data-ttu-id="064f6-115"><xref:Microsoft.VisualBasic.Information.IsError%2A></xref:Microsoft.VisualBasic.Information.IsError%2A></span><span class="sxs-lookup"><span data-stu-id="064f6-115"><xref:Microsoft.VisualBasic.Information.IsError%2A></span></span>|<span data-ttu-id="064f6-116">一个异常对象，它派生自<xref:System.Exception></xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="064f6-116">An exception object, which derives from <xref:System.Exception></span></span>|  
|<span data-ttu-id="064f6-117"><xref:Microsoft.VisualBasic.Information.IsNothing%2A></xref:Microsoft.VisualBasic.Information.IsNothing%2A></span><span class="sxs-lookup"><span data-stu-id="064f6-117"><xref:Microsoft.VisualBasic.Information.IsNothing%2A></span></span>|<span data-ttu-id="064f6-118">[执行任何操作](../../../../visual-basic/language-reference/nothing.md)，也就是说，没有任何对象当前分配给该变量</span><span class="sxs-lookup"><span data-stu-id="064f6-118">[Nothing](../../../../visual-basic/language-reference/nothing.md), that is, no object is currently assigned to the variable</span></span>|  
|<span data-ttu-id="064f6-119"><xref:Microsoft.VisualBasic.Information.IsNumeric%2A></xref:Microsoft.VisualBasic.Information.IsNumeric%2A></span><span class="sxs-lookup"><span data-stu-id="064f6-119"><xref:Microsoft.VisualBasic.Information.IsNumeric%2A></span></span>|<span data-ttu-id="064f6-120">一个数字或可以解释为数字的字符串</span><span class="sxs-lookup"><span data-stu-id="064f6-120">A number, or a string that can be interpreted as a number</span></span>|  
|<span data-ttu-id="064f6-121"><xref:Microsoft.VisualBasic.Information.IsReference%2A></xref:Microsoft.VisualBasic.Information.IsReference%2A></span><span class="sxs-lookup"><span data-stu-id="064f6-121"><xref:Microsoft.VisualBasic.Information.IsReference%2A></span></span>|<span data-ttu-id="064f6-122">引用类型 （如字符串、 数组、 委托或类类型）</span><span class="sxs-lookup"><span data-stu-id="064f6-122">A reference type (such as a string, array, delegate, or class type)</span></span>|  
  
 <span data-ttu-id="064f6-123">可以使用这些函数可以避免提交至某项操作或过程的无效值。</span><span class="sxs-lookup"><span data-stu-id="064f6-123">You can use these functions to avoid submitting an invalid value to an operation or a procedure.</span></span>  
  
## <a name="typeof-operator"></a><span data-ttu-id="064f6-124">TypeOf 运算符</span><span class="sxs-lookup"><span data-stu-id="064f6-124">TypeOf Operator</span></span>  
 <span data-ttu-id="064f6-125">您还可以使用[TypeOf 运算符](../../../../visual-basic/language-reference/operators/typeof-operator.md)来确定对象变量当前是指特定的数据类型。</span><span class="sxs-lookup"><span data-stu-id="064f6-125">You can also use the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to determine whether an object variable currently refers to a specific data type.</span></span> <span data-ttu-id="064f6-126">The `TypeOf`...`Is`表达式计算结果为`True`如果操作数的运行时类型派生自或实现指定的类型。</span><span class="sxs-lookup"><span data-stu-id="064f6-126">The `TypeOf`...`Is` expression evaluates to `True` if the run-time type of the operand is derived from or implements the specified type.</span></span>  
  
 <span data-ttu-id="064f6-127">下面的示例使用`TypeOf`值和引用类型引用的对象变量上。</span><span class="sxs-lookup"><span data-stu-id="064f6-127">The following example uses `TypeOf` on object variables referring to value and reference types.</span></span>  
  
```  
' The following statement puts a value type (Integer) in an Object variable.  
Dim num As Object = 10  
' The following statement puts a reference type (Form) in an Object variable.  
Dim frm As Object = New Form()  
If TypeOf num Is Long Then Debug.WriteLine("num is Long")  
If TypeOf num Is Integer Then Debug.WriteLine("num is Integer")  
If TypeOf num Is Short Then Debug.WriteLine("num is Short")  
If TypeOf num Is Object Then Debug.WriteLine("num is Object")  
If TypeOf frm Is Form Then Debug.WriteLine("frm is Form")  
If TypeOf frm Is Label Then Debug.WriteLine("frm is Label")  
If TypeOf frm Is Object Then Debug.WriteLine("frm is Object")  
```  
  
 <span data-ttu-id="064f6-128">前面的示例将以下行**调试**窗口︰</span><span class="sxs-lookup"><span data-stu-id="064f6-128">The preceding example writes the following lines to the **Debug** window:</span></span>  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 <span data-ttu-id="064f6-129">对象变量`num`类型的数据是指`Integer`，和`frm`指的是类<xref:System.Windows.Forms.Form>。</xref:System.Windows.Forms.Form>的对象</span><span class="sxs-lookup"><span data-stu-id="064f6-129">The object variable `num` refers to data of type `Integer`, and `frm` refers to an object of class <xref:System.Windows.Forms.Form>.</span></span>  
  
## <a name="object-arrays"></a><span data-ttu-id="064f6-130">对象数组</span><span class="sxs-lookup"><span data-stu-id="064f6-130">Object Arrays</span></span>  
 <span data-ttu-id="064f6-131">您可以声明和使用的数组`Object`变量。</span><span class="sxs-lookup"><span data-stu-id="064f6-131">You can declare and use an array of `Object` variables.</span></span> <span data-ttu-id="064f6-132">当您需要处理各种数据类型和对象类时，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="064f6-132">This is useful when you need to handle a variety of data types and object classes.</span></span> <span data-ttu-id="064f6-133">为数组中的所有元素必须都具有相同的声明的数据类型。</span><span class="sxs-lookup"><span data-stu-id="064f6-133">All the elements in an array must have the same declared data type.</span></span> <span data-ttu-id="064f6-134">声明此数据类型为`Object`可以用于存储对象和类实例及其他数组中的数据类型。</span><span class="sxs-lookup"><span data-stu-id="064f6-134">Declaring this data type as `Object` allows you to store objects and class instances alongside other data types in the array.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="064f6-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="064f6-135">See Also</span></span>  
 <span data-ttu-id="064f6-136">[对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span><span class="sxs-lookup"><span data-stu-id="064f6-136">[Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span></span>  
<span data-ttu-id="064f6-137"> [对象变量声明](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="064f6-137"> [Object Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span></span>  
<span data-ttu-id="064f6-138"> [对象变量赋值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md) </span><span class="sxs-lookup"><span data-stu-id="064f6-138"> [Object Variable Assignment](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md) </span></span>  
<span data-ttu-id="064f6-139"> [如何︰ 引用对象的当前实例](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md) </span><span class="sxs-lookup"><span data-stu-id="064f6-139"> [How to: Refer to the Current Instance of an Object](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md) </span></span>  
<span data-ttu-id="064f6-140"> [如何︰ 确定对象变量引用的类型](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md) </span><span class="sxs-lookup"><span data-stu-id="064f6-140"> [How to: Determine What Type an Object Variable Refers To](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md) </span></span>  
<span data-ttu-id="064f6-141"> [如何︰ 确定两个对象是否相关](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md) </span><span class="sxs-lookup"><span data-stu-id="064f6-141"> [How to: Determine Whether Two Objects Are Related](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md) </span></span>  
<span data-ttu-id="064f6-142"> [如何︰ 确定两个对象是否相同](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md) </span><span class="sxs-lookup"><span data-stu-id="064f6-142"> [How to: Determine Whether Two Objects Are Identical](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md) </span></span>  
<span data-ttu-id="064f6-143"> [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)</span><span class="sxs-lookup"><span data-stu-id="064f6-143"> [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md)</span></span>
