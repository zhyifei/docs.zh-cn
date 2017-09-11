---
title: "创建自定义特性 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fbfc3f84f6287d233d475f01869dab63b937a521
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="creating-custom-attributes-visual-basic"></a><span data-ttu-id="12f8f-102">创建自定义特性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12f8f-102">Creating Custom Attributes (Visual Basic)</span></span>
<span data-ttu-id="12f8f-103">可以通过定义属性类，派生的类直接或间接从创建您自己的自定义属性<xref:System.Attribute>，这样标识属性定义在元数据中快速而轻松地。</xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="12f8f-103">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="12f8f-104">假设您希望为同名的编写类型的程序员的标记类型。</span><span class="sxs-lookup"><span data-stu-id="12f8f-104">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="12f8f-105">您可能会定义一个自定义`Author`特性类︰</span><span class="sxs-lookup"><span data-stu-id="12f8f-105">You might define a custom `Author` attribute class:</span></span>  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct)>   
Public Class Author  
    Inherits System.Attribute  
    Private name As String  
    Public version As Double  
    Sub New(ByVal authorName As String)  
        name = authorName  
        version = 1.0  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="12f8f-106">类名是属性的名称， `Author`。</span><span class="sxs-lookup"><span data-stu-id="12f8f-106">The class name is the attribute's name, `Author`.</span></span> <span data-ttu-id="12f8f-107">派生自`System.Attribute`，因此它是一个自定义特性类。</span><span class="sxs-lookup"><span data-stu-id="12f8f-107">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="12f8f-108">构造函数的参数是自定义特性的位置参数。</span><span class="sxs-lookup"><span data-stu-id="12f8f-108">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="12f8f-109">在此示例中，`name`是位置参数。</span><span class="sxs-lookup"><span data-stu-id="12f8f-109">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="12f8f-110">所有公共读 / 写字段或属性都被命名参数。</span><span class="sxs-lookup"><span data-stu-id="12f8f-110">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="12f8f-111">在这种情况下，`version`唯一的命名参数。</span><span class="sxs-lookup"><span data-stu-id="12f8f-111">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="12f8f-112">请注意，使用`AttributeUsage`特性，以使`Author`属性仅对类有效和`Structure`声明。</span><span class="sxs-lookup"><span data-stu-id="12f8f-112">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `Structure` declarations.</span></span>  
  
 <span data-ttu-id="12f8f-113">可以使用这一新属性，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="12f8f-113">You could use this new attribute as follows:</span></span>  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 <span data-ttu-id="12f8f-114">`AttributeUsage`有一个命名的参数， `AllowMultiple`，使用它可以使自定义特性单用途或使用多次。</span><span class="sxs-lookup"><span data-stu-id="12f8f-114">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="12f8f-115">在下面的代码示例创建多次使用的特性。</span><span class="sxs-lookup"><span data-stu-id="12f8f-115">In the following code example, a multiuse attribute is created.</span></span>  
  
```vb  
' multiuse attribute  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct,   
                       AllowMultiple:=True)>   
Public Class Author  
    Inherits System.Attribute  
```  
  
 <span data-ttu-id="12f8f-116">在下面的代码示例中，多个相同类型的属性应用于类中。</span><span class="sxs-lookup"><span data-stu-id="12f8f-116">In the following code example, multiple attributes of the same type are applied to a class.</span></span>  
  
```vb  
<Author("P. Ackerman", Version:=1.1),   
Author("R. Koch", Version:=1.2)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
    ' R. Koch's code goes here...  
End Class  
```  
  
> [!NOTE]
>  <span data-ttu-id="12f8f-117">如果属性类包含一个属性，该属性必须为读写。</span><span class="sxs-lookup"><span data-stu-id="12f8f-117">If your attribute class contains a property, that property must be read-write.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12f8f-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12f8f-118">See Also</span></span>  
 <span data-ttu-id="12f8f-119"><xref:System.Reflection></xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="12f8f-119"><xref:System.Reflection></span></span>   
<span data-ttu-id="12f8f-120"> [Visual Basic 编程指南](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="12f8f-120"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="12f8f-121"> [编写自定义特性](http://msdn.microsoft.com/library/97216f69-bde8-49fd-ac40-f18c500ef5dc) </span><span class="sxs-lookup"><span data-stu-id="12f8f-121"> [Writing Custom Attributes](http://msdn.microsoft.com/library/97216f69-bde8-49fd-ac40-f18c500ef5dc) </span></span>  
<span data-ttu-id="12f8f-122"> [反射 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="12f8f-122"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
<span data-ttu-id="12f8f-123"> [特性 (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span><span class="sxs-lookup"><span data-stu-id="12f8f-123"> [Attributes (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span></span>  
<span data-ttu-id="12f8f-124"> [使用反射 (Visual Basic 中) 访问特性](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) </span><span class="sxs-lookup"><span data-stu-id="12f8f-124"> [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) </span></span>  
<span data-ttu-id="12f8f-125"> [AttributeUsage (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)</span><span class="sxs-lookup"><span data-stu-id="12f8f-125"> [AttributeUsage (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)</span></span>
