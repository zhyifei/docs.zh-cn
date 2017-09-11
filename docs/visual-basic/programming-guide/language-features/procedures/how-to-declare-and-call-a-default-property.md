---
title: "如何︰ 声明和调用默认属性在 Visual Basic |Microsoft 文档"
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
- defaults, properties
- properties [Visual Basic], default
- procedures, defining
- default properties, in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
caps.latest.revision: 23
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
ms.openlocfilehash: 7cfd476def67ccf46e524da7943680f9e34b6a26
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="40f42-102">如何：在 Visual Basic 中声明和调用默认属性</span><span class="sxs-lookup"><span data-stu-id="40f42-102">How to: Declare and Call a Default Property in Visual Basic</span></span>
<span data-ttu-id="40f42-103">一个*默认属性*是一个类或结构的属性，您的代码可以访问而无需指定它。</span><span class="sxs-lookup"><span data-stu-id="40f42-103">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="40f42-104">当一个类或结构，但不是属性，调用代码名称，上下文允许访问某一属性[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]解析对该类或结构的默认属性的访问权限，如果存在。</span><span class="sxs-lookup"><span data-stu-id="40f42-104">When calling code names a class or structure but not a property, and the context allows access to a property, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="40f42-105">类或结构最多可以有一个默认属性。</span><span class="sxs-lookup"><span data-stu-id="40f42-105">A class or structure can have at most one default property.</span></span> <span data-ttu-id="40f42-106">但是，您可以重载的默认属性并且具有多个版本。</span><span class="sxs-lookup"><span data-stu-id="40f42-106">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="40f42-107">有关详细信息，请参阅[默认](../../../../visual-basic/language-reference/modifiers/default.md)。</span><span class="sxs-lookup"><span data-stu-id="40f42-107">For more information, see [Default](../../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="40f42-108">若要声明的默认属性</span><span class="sxs-lookup"><span data-stu-id="40f42-108">To declare a default property</span></span>  
  
1.  <span data-ttu-id="40f42-109">以正常方式声明属性。</span><span class="sxs-lookup"><span data-stu-id="40f42-109">Declare the property in the normal way.</span></span> <span data-ttu-id="40f42-110">请不要指定`Shared`或`Private`关键字。</span><span class="sxs-lookup"><span data-stu-id="40f42-110">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2.  <span data-ttu-id="40f42-111">包括`Default`属性声明中的关键字。</span><span class="sxs-lookup"><span data-stu-id="40f42-111">Include the `Default` keyword in the property declaration.</span></span>  
  
3.  <span data-ttu-id="40f42-112">指定的属性至少一个参数。</span><span class="sxs-lookup"><span data-stu-id="40f42-112">Specify at least one parameter for the property.</span></span> <span data-ttu-id="40f42-113">不能定义不带至少一个参数的默认属性。</span><span class="sxs-lookup"><span data-stu-id="40f42-113">You cannot define a default property that does not take at least one argument.</span></span>  
  
     <span data-ttu-id="40f42-114">[!code-vb[VbVbcnProcedures #&17;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="40f42-114">[!code-vb[VbVbcnProcedures#17](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]</span></span>  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="40f42-115">若要调用默认属性</span><span class="sxs-lookup"><span data-stu-id="40f42-115">To call a default property</span></span>  
  
1.  <span data-ttu-id="40f42-116">声明包含的类或结构类型的变量。</span><span class="sxs-lookup"><span data-stu-id="40f42-116">Declare a variable of the containing class or structure type.</span></span>  
  
     <span data-ttu-id="40f42-117">[!code-vb[VbVbcnProcedures #&16;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="40f42-117">[!code-vb[VbVbcnProcedures#16](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]</span></span>  
  
2.  <span data-ttu-id="40f42-118">使用的表达式中单独的变量名通常要包括的属性名称。</span><span class="sxs-lookup"><span data-stu-id="40f42-118">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     <span data-ttu-id="40f42-119">[!code-vb[VbVbcnProcedures #&21;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="40f42-119">[!code-vb[VbVbcnProcedures#21](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]</span></span>  
  
3.  <span data-ttu-id="40f42-120">变量名后面加上括号中的参数列表。</span><span class="sxs-lookup"><span data-stu-id="40f42-120">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="40f42-121">默认属性必须采用至少一个参数。</span><span class="sxs-lookup"><span data-stu-id="40f42-121">A default property must take at least one argument.</span></span>  
  
     <span data-ttu-id="40f42-122">[!code-vb[VbVbcnProcedures #&20;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="40f42-122">[!code-vb[VbVbcnProcedures#20](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]</span></span>  
  
4.  <span data-ttu-id="40f42-123">若要检索其默认属性值，使用变量名称，用参数列表，在表达式中前面或后面等号 (`=`) 登录在赋值语句。</span><span class="sxs-lookup"><span data-stu-id="40f42-123">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="40f42-124">[!code-vb[VbVbcnProcedures #&15;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="40f42-124">[!code-vb[VbVbcnProcedures#15](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]</span></span>  
  
5.  <span data-ttu-id="40f42-125">若要设置默认属性值，用参数列表，在赋值语句左侧使用的变量的名称。</span><span class="sxs-lookup"><span data-stu-id="40f42-125">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="40f42-126">[!code-vb[VbVbcnProcedures #&14;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="40f42-126">[!code-vb[VbVbcnProcedures#14](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]</span></span>  
  
6.  <span data-ttu-id="40f42-127">像那样访问任何其他属性，始终可以指定默认属性名以及变量名。</span><span class="sxs-lookup"><span data-stu-id="40f42-127">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     <span data-ttu-id="40f42-128">[!code-vb[VbVbcnProcedures #&19;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="40f42-128">[!code-vb[VbVbcnProcedures#19](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="40f42-129">示例</span><span class="sxs-lookup"><span data-stu-id="40f42-129">Example</span></span>  
 <span data-ttu-id="40f42-130">下面的示例声明的类上的默认属性。</span><span class="sxs-lookup"><span data-stu-id="40f42-130">The following example declares a default property on a class.</span></span>  
  
 <span data-ttu-id="40f42-131">[!code-vb[VbVbcnProcedures #&12;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="40f42-131">[!code-vb[VbVbcnProcedures#12](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="40f42-132">示例</span><span class="sxs-lookup"><span data-stu-id="40f42-132">Example</span></span>  
 <span data-ttu-id="40f42-133">下面的示例演示如何调用默认属性`myProperty`类上`class1`。</span><span class="sxs-lookup"><span data-stu-id="40f42-133">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="40f42-134">三个赋值语句将值存储在`myProperty`，和<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>调用读取这些值。</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A></span><span class="sxs-lookup"><span data-stu-id="40f42-134">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 <span data-ttu-id="40f42-135">[!code-vb[VbVbcnProcedures #&13;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="40f42-135">[!code-vb[VbVbcnProcedures#13](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]</span></span>  
  
 <span data-ttu-id="40f42-136">默认属性的最常见用法是<xref:Microsoft.VisualBasic.Collection.Item%2A>各种集合类的属性。</xref:Microsoft.VisualBasic.Collection.Item%2A></span><span class="sxs-lookup"><span data-stu-id="40f42-136">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="40f42-137">可靠编程</span><span class="sxs-lookup"><span data-stu-id="40f42-137">Robust Programming</span></span>  
 <span data-ttu-id="40f42-138">默认属性可能会导致稍微减少源代码的字符，但它们会使您的代码更难以阅读。</span><span class="sxs-lookup"><span data-stu-id="40f42-138">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="40f42-139">如果建立对类或结构名称的引用时，调用代码不熟悉类或结构，它无法确定该引用访问的类或结构本身或默认属性。</span><span class="sxs-lookup"><span data-stu-id="40f42-139">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="40f42-140">这可以导致编译器错误或细微的运行时逻辑错误。</span><span class="sxs-lookup"><span data-stu-id="40f42-140">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="40f42-141">某种程度上可以减少默认属性错误的机会，应始终使用[Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)设置编译器类型将检查`On`。</span><span class="sxs-lookup"><span data-stu-id="40f42-141">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="40f42-142">如果您打算使用预定义的类或结构在代码中，您必须确定它是否具有默认属性，以及如果是这样，其名称是什么。</span><span class="sxs-lookup"><span data-stu-id="40f42-142">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="40f42-143">由于这些缺点，应考虑不定义默认属性。</span><span class="sxs-lookup"><span data-stu-id="40f42-143">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="40f42-144">有关代码的可读性，您应该还考虑始终显式引用的所有属性，包括默认属性。</span><span class="sxs-lookup"><span data-stu-id="40f42-144">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40f42-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40f42-145">See Also</span></span>  
 <span data-ttu-id="40f42-146">[属性过程](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="40f42-146">[Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="40f42-147"> [过程参数和变量](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="40f42-147"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="40f42-148"> [Property 语句](../../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="40f42-148"> [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="40f42-149"> [默认值](../../../../visual-basic/language-reference/modifiers/default.md) </span><span class="sxs-lookup"><span data-stu-id="40f42-149"> [Default](../../../../visual-basic/language-reference/modifiers/default.md) </span></span>  
<span data-ttu-id="40f42-150"> [在 Visual Basic 中属性和变量之间的差异](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="40f42-150"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="40f42-151"> [如何︰ 创建属性](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="40f42-151"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="40f42-152"> [如何︰ 声明具有混合的访问级别的属性](./how-to-declare-a-property-with-mixed-access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="40f42-152"> [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md) </span></span>  
<span data-ttu-id="40f42-153"> [如何︰ 调用 Property 过程](./how-to-call-a-property-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="40f42-153"> [How to: Call a Property Procedure](./how-to-call-a-property-procedure.md) </span></span>  
<span data-ttu-id="40f42-154"> [如何︰ 在属性中放置值](./how-to-put-a-value-in-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="40f42-154"> [How to: Put a Value in a Property](./how-to-put-a-value-in-a-property.md) </span></span>  
<span data-ttu-id="40f42-155"> [如何：从属性获取值](./how-to-get-a-value-from-a-property.md)</span><span class="sxs-lookup"><span data-stu-id="40f42-155"> [How to: Get a Value from a Property](./how-to-get-a-value-from-a-property.md)</span></span>
