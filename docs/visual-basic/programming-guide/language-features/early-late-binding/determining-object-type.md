---
title: "确定对象类型 (Visual Basic 中) |Microsoft 文档"
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
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables, testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
caps.latest.revision: 13
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
ms.openlocfilehash: fec7a275029dde469425b651d5b1220cb21ddbf6
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="determining-object-type-visual-basic"></a><span data-ttu-id="d26c5-102">确定对象类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d26c5-102">Determining Object Type (Visual Basic)</span></span>
<span data-ttu-id="d26c5-103">一般对象变量 (即，变量声明为`Object`) 可以包含来自任何类对象。</span><span class="sxs-lookup"><span data-stu-id="d26c5-103">Generic object variables (that is, variables you declare as `Object`) can hold objects from any class.</span></span> <span data-ttu-id="d26c5-104">使用类型的变量时`Object`，您可能需要采取不同的操作，在基于对象的类; 例如，某些对象可能不支持特定属性或方法。</span><span class="sxs-lookup"><span data-stu-id="d26c5-104">When using variables of type `Object`, you may need to take different actions based on the class of the object; for example, some objects might not support a particular property or method.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="d26c5-105">提供了以下两种方法可以确定哪种类型的对象存储在一个对象变量︰`TypeName`函数和`TypeOf...Is`运算符。</span><span class="sxs-lookup"><span data-stu-id="d26c5-105"> provides two means of determining which type of object is stored in an object variable: the `TypeName` function and the `TypeOf...Is` operator.</span></span>  
  
## <a name="typename-and-typeofis"></a><span data-ttu-id="d26c5-106">TypeName 和 TypeOf...是</span><span class="sxs-lookup"><span data-stu-id="d26c5-106">TypeName and TypeOf…Is</span></span>  
 <span data-ttu-id="d26c5-107">`TypeName`函数将返回一个字符串，而是最佳选择，当您需要时存储或显示类对象的名称，如下面的代码段中所示︰</span><span class="sxs-lookup"><span data-stu-id="d26c5-107">The `TypeName` function returns a string and is the best choice when you need to store or display the class name of an object, as shown in the following code fragment:</span></span>  
  
 <span data-ttu-id="d26c5-108">[!code-vb[VbVbalrOOP #&92;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="d26c5-108">[!code-vb[VbVbalrOOP#92](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]</span></span>  
  
 <span data-ttu-id="d26c5-109">`TypeOf...Is`运算符是用于测试的对象类型的最佳选择，因为它是比等效的字符串比较使用更快`TypeName`。</span><span class="sxs-lookup"><span data-stu-id="d26c5-109">The `TypeOf...Is` operator is the best choice for testing an object's type, because it is much faster than an equivalent string comparison using `TypeName`.</span></span> <span data-ttu-id="d26c5-110">下面的代码片段使用`TypeOf...Is`内`If...Then...Else`语句︰</span><span class="sxs-lookup"><span data-stu-id="d26c5-110">The following code fragment uses `TypeOf...Is` within an `If...Then...Else` statement:</span></span>  
  
 <span data-ttu-id="d26c5-111">[!code-vb[VbVbalrOOP #&93;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="d26c5-111">[!code-vb[VbVbalrOOP#93](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]</span></span>  
  
 <span data-ttu-id="d26c5-112">需要注意的一点就到期。</span><span class="sxs-lookup"><span data-stu-id="d26c5-112">A word of caution is due here.</span></span> <span data-ttu-id="d26c5-113">`TypeOf...Is`运算符将返回`True`如果属于特定类型或派生自某个特定类型的对象。</span><span class="sxs-lookup"><span data-stu-id="d26c5-113">The `TypeOf...Is` operator returns `True` if an object is of a specific type, or is derived from a specific type.</span></span> <span data-ttu-id="d26c5-114">几乎所有操作都与[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]涉及到对象，其中包括一些通常不被视为对象，如字符串和整数的元素。</span><span class="sxs-lookup"><span data-stu-id="d26c5-114">Almost everything you do with [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] involves objects, which include some elements not normally thought of as objects, such as strings and integers.</span></span> <span data-ttu-id="d26c5-115">这些对象派生自和继承从<xref:System.Object>。</xref:System.Object>方法</span><span class="sxs-lookup"><span data-stu-id="d26c5-115">These objects are derived from and inherit methods from <xref:System.Object>.</span></span> <span data-ttu-id="d26c5-116">当传递`Integer`和计算与`Object`、`TypeOf...Is`运算符将返回`True`。</span><span class="sxs-lookup"><span data-stu-id="d26c5-116">When passed an `Integer` and evaluated with `Object`, the `TypeOf...Is` operator returns `True`.</span></span> <span data-ttu-id="d26c5-117">下面的示例报告参数`InParam`既是`Object`和`Integer`:</span><span class="sxs-lookup"><span data-stu-id="d26c5-117">The following example reports that the parameter `InParam` is both an `Object` and an `Integer`:</span></span>  
  
 <span data-ttu-id="d26c5-118">[!code-vb[VbVbalrOOP #&94;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="d26c5-118">[!code-vb[VbVbalrOOP#94](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]</span></span>  
  
 <span data-ttu-id="d26c5-119">下面的示例使用这两个`TypeOf...Is`和`TypeName`来确定对象中传递给它的类型`Ctrl`参数。</span><span class="sxs-lookup"><span data-stu-id="d26c5-119">The following example uses both `TypeOf...Is` and `TypeName` to determine the type of object passed to it in the `Ctrl` argument.</span></span> <span data-ttu-id="d26c5-120">`TestObject`过程调用`ShowType`使用三种不同的控件。</span><span class="sxs-lookup"><span data-stu-id="d26c5-120">The `TestObject` procedure calls `ShowType` with three different kinds of controls.</span></span>  
  
#### <a name="to-run-the-example"></a><span data-ttu-id="d26c5-121">运行示例</span><span class="sxs-lookup"><span data-stu-id="d26c5-121">To run the example</span></span>  
  
1.  <span data-ttu-id="d26c5-122">创建新的 Windows 应用程序项目并添加<xref:System.Windows.Forms.Button>控件，<xref:System.Windows.Forms.CheckBox>控件，和一个<xref:System.Windows.Forms.RadioButton>到窗体的控件。</xref:System.Windows.Forms.RadioButton> </xref:System.Windows.Forms.CheckBox> </xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="d26c5-122">Create a new Windows Application project and add a <xref:System.Windows.Forms.Button> control, a <xref:System.Windows.Forms.CheckBox> control, and a <xref:System.Windows.Forms.RadioButton> control to the form.</span></span>  
  
2.  <span data-ttu-id="d26c5-123">从你的窗体上的按钮，调用`TestObject`过程。</span><span class="sxs-lookup"><span data-stu-id="d26c5-123">From the button on your form, call the `TestObject` procedure.</span></span>  
  
3.  <span data-ttu-id="d26c5-124">将以下代码添加到你的窗体︰</span><span class="sxs-lookup"><span data-stu-id="d26c5-124">Add the following code to your form:</span></span>  
  
     <span data-ttu-id="d26c5-125">[!code-vb[VbVbalrOOP #&95;](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="d26c5-125">[!code-vb[VbVbalrOOP#95](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d26c5-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d26c5-126">See Also</span></span>  
 <span data-ttu-id="d26c5-127"><xref:Microsoft.VisualBasic.Information.TypeName%2A></xref:Microsoft.VisualBasic.Information.TypeName%2A></span><span class="sxs-lookup"><span data-stu-id="d26c5-127"><xref:Microsoft.VisualBasic.Information.TypeName%2A></span></span>   
<span data-ttu-id="d26c5-128"> [使用字符串名调用属性或方法](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md) </span><span class="sxs-lookup"><span data-stu-id="d26c5-128"> [Calling a Property or Method Using a String Name](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md) </span></span>  
<span data-ttu-id="d26c5-129"> [Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="d26c5-129"> [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span></span>  
<span data-ttu-id="d26c5-130"> [如果...然后...Else 语句](../../../../visual-basic/language-reference/statements/if-then-else-statement.md) </span><span class="sxs-lookup"><span data-stu-id="d26c5-130"> [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md) </span></span>  
<span data-ttu-id="d26c5-131"> [String 数据类型](../../../../visual-basic/language-reference/data-types/string-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="d26c5-131"> [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) </span></span>  
<span data-ttu-id="d26c5-132"> [Integer 数据类型](../../../../visual-basic/language-reference/data-types/integer-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="d26c5-132"> [Integer Data Type](../../../../visual-basic/language-reference/data-types/integer-data-type.md)</span></span>
