---
title: 对象变量值 (Visual Basic)
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
- object variables [Visual Basic], values
- values [Visual Basic], of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 28307cc477f661c3046e125f297c1519485ad797
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="object-variable-values-visual-basic"></a><span data-ttu-id="65627-102">对象变量值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65627-102">Object Variable Values (Visual Basic)</span></span>
<span data-ttu-id="65627-103">变量[Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)可以指任何类型的数据。</span><span class="sxs-lookup"><span data-stu-id="65627-103">A variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) can refer to data of any type.</span></span> <span data-ttu-id="65627-104">在中存储的值`Object`变量被保存别处在内存中，而变量本身的数据指针。</span><span class="sxs-lookup"><span data-stu-id="65627-104">The value you store in an `Object` variable is kept elsewhere in memory, while the variable itself holds a pointer to the data.</span></span>  
  
## <a name="object-classifier-functions"></a><span data-ttu-id="65627-105">对象分类器函数</span><span class="sxs-lookup"><span data-stu-id="65627-105">Object Classifier Functions</span></span>  
 <span data-ttu-id="65627-106">Visual Basic 提供返回有关新增功能的信息的函数`Object`变量所引用下, 表中所示。</span><span class="sxs-lookup"><span data-stu-id="65627-106">Visual Basic supplies functions that return information about what an `Object` variable refers to, as shown in the following table.</span></span>  
  
|<span data-ttu-id="65627-107">函数</span><span class="sxs-lookup"><span data-stu-id="65627-107">Function</span></span>|<span data-ttu-id="65627-108">如果对象变量引用的则返回 True</span><span class="sxs-lookup"><span data-stu-id="65627-108">Returns True if the Object variable refers to</span></span>|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|<span data-ttu-id="65627-109">一个值，而不是单个值的数组</span><span class="sxs-lookup"><span data-stu-id="65627-109">An array of values, rather than a single value</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|<span data-ttu-id="65627-110">A[日期数据类型](../../../../visual-basic/language-reference/data-types/date-data-type.md)值或可以解释为日期和时间值的字符串</span><span class="sxs-lookup"><span data-stu-id="65627-110">A [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) value, or a string that can be interpreted as a date and time value</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|<span data-ttu-id="65627-111">类型的对象<xref:System.DBNull>，它表示缺失或不存在的数据</span><span class="sxs-lookup"><span data-stu-id="65627-111">An object of type <xref:System.DBNull>, which represents missing or nonexistent data</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|<span data-ttu-id="65627-112">一个异常对象，它派生自 <xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="65627-112">An exception object, which derives from <xref:System.Exception></span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|<span data-ttu-id="65627-113">[执行任何操作](../../../../visual-basic/language-reference/nothing.md)，也就是说，没有任何对象当前分配给变量</span><span class="sxs-lookup"><span data-stu-id="65627-113">[Nothing](../../../../visual-basic/language-reference/nothing.md), that is, no object is currently assigned to the variable</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|<span data-ttu-id="65627-114">一个数字或可以解释为数字的字符串</span><span class="sxs-lookup"><span data-stu-id="65627-114">A number, or a string that can be interpreted as a number</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|<span data-ttu-id="65627-115">引用类型 （如字符串、 数组、 委托或类类型）</span><span class="sxs-lookup"><span data-stu-id="65627-115">A reference type (such as a string, array, delegate, or class type)</span></span>|  
  
 <span data-ttu-id="65627-116">这些函数可用于避免提交向操作或过程的无效值。</span><span class="sxs-lookup"><span data-stu-id="65627-116">You can use these functions to avoid submitting an invalid value to an operation or a procedure.</span></span>  
  
## <a name="typeof-operator"></a><span data-ttu-id="65627-117">TypeOf 运算符</span><span class="sxs-lookup"><span data-stu-id="65627-117">TypeOf Operator</span></span>  
 <span data-ttu-id="65627-118">你还可以使用[TypeOf 运算符](../../../../visual-basic/language-reference/operators/typeof-operator.md)来确定是否为特定数据类型中当前引用的对象变量。</span><span class="sxs-lookup"><span data-stu-id="65627-118">You can also use the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to determine whether an object variable currently refers to a specific data type.</span></span> <span data-ttu-id="65627-119">`TypeOf`...`Is`表达式计算结果为`True`如果操作数的运行时类型派生自或实现指定的类型。</span><span class="sxs-lookup"><span data-stu-id="65627-119">The `TypeOf`...`Is` expression evaluates to `True` if the run-time type of the operand is derived from or implements the specified type.</span></span>  
  
 <span data-ttu-id="65627-120">下面的示例使用`TypeOf`引用值和引用类型的对象变量上。</span><span class="sxs-lookup"><span data-stu-id="65627-120">The following example uses `TypeOf` on object variables referring to value and reference types.</span></span>  
  
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
  
 <span data-ttu-id="65627-121">前面的示例将以下行**调试**窗口：</span><span class="sxs-lookup"><span data-stu-id="65627-121">The preceding example writes the following lines to the **Debug** window:</span></span>  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 <span data-ttu-id="65627-122">对象变量`num`类型的数据是指`Integer`，和`frm`类的对象是指<xref:System.Windows.Forms.Form>。</span><span class="sxs-lookup"><span data-stu-id="65627-122">The object variable `num` refers to data of type `Integer`, and `frm` refers to an object of class <xref:System.Windows.Forms.Form>.</span></span>  
  
## <a name="object-arrays"></a><span data-ttu-id="65627-123">对象数组</span><span class="sxs-lookup"><span data-stu-id="65627-123">Object Arrays</span></span>  
 <span data-ttu-id="65627-124">你可以声明并使用的数组`Object`变量。</span><span class="sxs-lookup"><span data-stu-id="65627-124">You can declare and use an array of `Object` variables.</span></span> <span data-ttu-id="65627-125">当你需要处理各种数据类型和对象类时，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="65627-125">This is useful when you need to handle a variety of data types and object classes.</span></span> <span data-ttu-id="65627-126">数组中的所有元素必须都具有相同的声明的数据类型。</span><span class="sxs-lookup"><span data-stu-id="65627-126">All the elements in an array must have the same declared data type.</span></span> <span data-ttu-id="65627-127">声明此数据类型作为`Object`可用于存储对象和类以及数组中的其他数据类型的实例。</span><span class="sxs-lookup"><span data-stu-id="65627-127">Declaring this data type as `Object` allows you to store objects and class instances alongside other data types in the array.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65627-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="65627-128">See Also</span></span>  
 [<span data-ttu-id="65627-129">对象变量</span><span class="sxs-lookup"><span data-stu-id="65627-129">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="65627-130">对象变量声明</span><span class="sxs-lookup"><span data-stu-id="65627-130">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="65627-131">对象变量赋值</span><span class="sxs-lookup"><span data-stu-id="65627-131">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="65627-132">如何：引用对象的当前实例</span><span class="sxs-lookup"><span data-stu-id="65627-132">How to: Refer to the Current Instance of an Object</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)  
 [<span data-ttu-id="65627-133">如何：确定对象变量引用的类型</span><span class="sxs-lookup"><span data-stu-id="65627-133">How to: Determine What Type an Object Variable Refers To</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)  
 [<span data-ttu-id="65627-134">如何：确定两个对象是否相关</span><span class="sxs-lookup"><span data-stu-id="65627-134">How to: Determine Whether Two Objects Are Related</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [<span data-ttu-id="65627-135">如何：确定两个对象是否相同</span><span class="sxs-lookup"><span data-stu-id="65627-135">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)  
 [<span data-ttu-id="65627-136">数据类型</span><span class="sxs-lookup"><span data-stu-id="65627-136">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
