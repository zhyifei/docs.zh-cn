---
title: 表达式递归调用包含属性 &#39;&lt;propertyname&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 47de3c2d25336962168f01a4c8717274de7c9aad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="expression-recursively-calls-the-containing-property-39ltpropertynamegt39"></a><span data-ttu-id="3dae8-102">表达式递归调用包含属性 &#39;&lt;propertyname&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="3dae8-102">Expression recursively calls the containing property &#39;&lt;propertyname&gt;&#39;</span></span>
<span data-ttu-id="3dae8-103">中的语句`Set`属性定义的过程将值存储到属性的名称。</span><span class="sxs-lookup"><span data-stu-id="3dae8-103">A statement in the `Set` procedure of a property definition stores a value into the name of the property.</span></span>  
  
 <span data-ttu-id="3dae8-104">保存属性的值的建议的方法是定义`Private`变量属性的容器中并使用它在这两`Get`和`Set`过程。</span><span class="sxs-lookup"><span data-stu-id="3dae8-104">The recommended approach to holding the value of a property is to define a `Private` variable in the property's container and use it in both the `Get` and `Set` procedures.</span></span> <span data-ttu-id="3dae8-105">`Set`过程然后应将传入值存储在此`Private`变量。</span><span class="sxs-lookup"><span data-stu-id="3dae8-105">The `Set` procedure should then store the incoming value in this `Private` variable.</span></span>  
  
 <span data-ttu-id="3dae8-106">`Get`过程的行为类似`Function`过程，以便它可以将值分配到属性名称，并将控件返回通过遇到`End Get`语句。</span><span class="sxs-lookup"><span data-stu-id="3dae8-106">The `Get` procedure behaves like a `Function` procedure, so it can assign a value to the property name and return control by encountering the `End Get` statement.</span></span> <span data-ttu-id="3dae8-107">推荐的方法，但是，是包括`Private`变量中的值作为[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="3dae8-107">The recommended approach, however, is to include the `Private` variable as the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="3dae8-108">`Set`过程的行为类似`Sub`过程，不返回值。</span><span class="sxs-lookup"><span data-stu-id="3dae8-108">The `Set` procedure behaves like a `Sub` procedure, which does not return a value.</span></span> <span data-ttu-id="3dae8-109">因此，过程或属性名称已在没有特殊含义`Set`过程中，并且你无法将值存储到其中。</span><span class="sxs-lookup"><span data-stu-id="3dae8-109">Therefore, the procedure or property name has no special meaning within a `Set` procedure, and you cannot store a value into it.</span></span>  
  
 <span data-ttu-id="3dae8-110">下面的示例演示可能导致此错误，跟建议的方法的方案。</span><span class="sxs-lookup"><span data-stu-id="3dae8-110">The following example illustrates the approach that can cause this error, followed by the recommended approach.</span></span>  
  
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
  
 <span data-ttu-id="3dae8-111">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="3dae8-111">By default, this message is a warning.</span></span> <span data-ttu-id="3dae8-112">有关隐藏警告或将警告视为错误的详细信息，请参阅[在 Visual Basic 中的配置警告](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="3dae8-112">For more information about hiding warnings or treating warnings as errors, please see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="3dae8-113">**错误 ID:** BC42026</span><span class="sxs-lookup"><span data-stu-id="3dae8-113">**Error ID:** BC42026</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3dae8-114">更正此错误</span><span class="sxs-lookup"><span data-stu-id="3dae8-114">To correct this error</span></span>  
  
-   <span data-ttu-id="3dae8-115">重写要用建议的方法，如前面的示例中所示的属性定义。</span><span class="sxs-lookup"><span data-stu-id="3dae8-115">Rewrite the property definition to use the recommended approach as illustrated in the preceding example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dae8-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3dae8-116">See Also</span></span>  
 [<span data-ttu-id="3dae8-117">属性过程</span><span class="sxs-lookup"><span data-stu-id="3dae8-117">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [<span data-ttu-id="3dae8-118">Property 语句</span><span class="sxs-lookup"><span data-stu-id="3dae8-118">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="3dae8-119">Set 语句</span><span class="sxs-lookup"><span data-stu-id="3dae8-119">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
