---
title: "表达式递归调用包含的属性 &quot;&lt;propertyname&gt;&quot; |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42026
- BC42026
dev_langs:
- VB
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
caps.latest.revision: 10
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
ms.openlocfilehash: c7168ab2a2ec5eb0c0d423120b67c10b117c14b2
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="expression-recursively-calls-the-containing-property-39ltpropertynamegt39"></a><span data-ttu-id="a94a5-102">表达式递归调用包含的属性 '&lt;propertyname&gt;</span><span class="sxs-lookup"><span data-stu-id="a94a5-102">Expression recursively calls the containing property &#39;&lt;propertyname&gt;&#39;</span></span>
<span data-ttu-id="a94a5-103">中的语句`Set`属性定义的过程将一个值存储到属性的名称。</span><span class="sxs-lookup"><span data-stu-id="a94a5-103">A statement in the `Set` procedure of a property definition stores a value into the name of the property.</span></span>  
  
 <span data-ttu-id="a94a5-104">包含属性的值的建议的方法是定义`Private`变量属性的容器中并将其同时`Get`和`Set`过程。</span><span class="sxs-lookup"><span data-stu-id="a94a5-104">The recommended approach to holding the value of a property is to define a `Private` variable in the property's container and use it in both the `Get` and `Set` procedures.</span></span> <span data-ttu-id="a94a5-105">`Set`过程然后应将传入的值存储在此`Private`变量。</span><span class="sxs-lookup"><span data-stu-id="a94a5-105">The `Set` procedure should then store the incoming value in this `Private` variable.</span></span>  
  
 <span data-ttu-id="a94a5-106">`Get`过程的行为类似`Function`的过程中，以便可以将值分配给属性名称并将控制权返回在遇到`End Get`语句。</span><span class="sxs-lookup"><span data-stu-id="a94a5-106">The `Get` procedure behaves like a `Function` procedure, so it can assign a value to the property name and return control by encountering the `End Get` statement.</span></span> <span data-ttu-id="a94a5-107">建议的方法，但是，是包括`Private`变量中的值作为[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="a94a5-107">The recommended approach, however, is to include the `Private` variable as the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="a94a5-108">`Set`过程的行为类似`Sub`过程，不返回值。</span><span class="sxs-lookup"><span data-stu-id="a94a5-108">The `Set` procedure behaves like a `Sub` procedure, which does not return a value.</span></span> <span data-ttu-id="a94a5-109">因此，过程或属性名称具有中的没有特殊含义`Set`过程中，并且您不能将一个值存储到其中。</span><span class="sxs-lookup"><span data-stu-id="a94a5-109">Therefore, the procedure or property name has no special meaning within a `Set` procedure, and you cannot store a value into it.</span></span>  
  
 <span data-ttu-id="a94a5-110">下面的示例说明了可能会导致此错误消息，然后建议的方法的方法。</span><span class="sxs-lookup"><span data-stu-id="a94a5-110">The following example illustrates the approach that can cause this error, followed by the recommended approach.</span></span>  
  
```  
Public Class illustrateProperties  
' The code in the following property causes this error.  
    Public Property badProp() As Char  
        Get  
            Dim charValue As Char  
            ' Insert code to update charValue.  
            badProp = charValue  
        End Get  
        Set(ByVal Value As Char)  
            ' The following statement causes this error.  
            badProp = Value  
            ' The value stored in the local variable badProp  
            ' is not used by the Get procedure in this property.  
        End Set  
    End Property  
' The following code uses the recommended approach.  
    Private propValue As Char  
    Public Property goodProp() As Char  
        Get  
            ' Insert code to update propValue.  
            Return propValue  
        End Get  
        Set(ByVal Value As Char)  
            propValue = Value  
        End Set  
    End Property  
End Class  
```  
  
 <span data-ttu-id="a94a5-111">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="a94a5-111">By default, this message is a warning.</span></span> <span data-ttu-id="a94a5-112">有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中配置警告](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="a94a5-112">For more information about hiding warnings or treating warnings as errors, please see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="a94a5-113">**错误 ID:** BC42026</span><span class="sxs-lookup"><span data-stu-id="a94a5-113">**Error ID:** BC42026</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a94a5-114">更正此错误</span><span class="sxs-lookup"><span data-stu-id="a94a5-114">To correct this error</span></span>  
  
-   <span data-ttu-id="a94a5-115">重写属性定义，以便使用建议的方法，如在前面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="a94a5-115">Rewrite the property definition to use the recommended approach as illustrated in the preceding example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a94a5-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a94a5-116">See Also</span></span>  
 <span data-ttu-id="a94a5-117">[属性过程](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="a94a5-117">[Property Procedures](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md) </span></span>  
<span data-ttu-id="a94a5-118"> [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="a94a5-118"> [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="a94a5-119"> [Set 语句](../../../visual-basic/language-reference/statements/set-statement.md)</span><span class="sxs-lookup"><span data-stu-id="a94a5-119"> [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md)</span></span>
