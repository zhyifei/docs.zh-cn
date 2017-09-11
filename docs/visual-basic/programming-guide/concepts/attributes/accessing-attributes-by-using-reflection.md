---
title: "使用反射 (Visual Basic 中) 访问属性 |Microsoft 文档"
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
ms.assetid: c56e41da-5433-464f-a7bf-2a722e78bc9f
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
ms.openlocfilehash: ac1e017ae13fc1291fd41e5747171160a9d70238
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="accessing-attributes-by-using-reflection-visual-basic"></a><span data-ttu-id="2fe24-102">使用反射 (Visual Basic 中) 访问特性</span><span class="sxs-lookup"><span data-stu-id="2fe24-102">Accessing Attributes by Using Reflection (Visual Basic)</span></span>
<span data-ttu-id="2fe24-103">如果没有某种方法检索该信息并对其进行操作的价值很小的将事实，您可以定义自定义属性并将其放置在您的源代码。</span><span class="sxs-lookup"><span data-stu-id="2fe24-103">The fact that you can define custom attributes and place them in your source code would be of little value without some way of retrieving that information and acting on it.</span></span> <span data-ttu-id="2fe24-104">通过使用反射，您可以检索的定义是以自定义特性的信息。</span><span class="sxs-lookup"><span data-stu-id="2fe24-104">By using reflection, you can retrieve the information that was defined with custom attributes.</span></span> <span data-ttu-id="2fe24-105">主要方法是`GetCustomAttributes`，它返回数组的对象的 source 代码特性的运行时等效项。</span><span class="sxs-lookup"><span data-stu-id="2fe24-105">The key method is `GetCustomAttributes`, which returns an array of objects that are the run-time equivalents of the source code attributes.</span></span> <span data-ttu-id="2fe24-106">此方法具有多个重载的版本。</span><span class="sxs-lookup"><span data-stu-id="2fe24-106">This method has several overloaded versions.</span></span> <span data-ttu-id="2fe24-107">有关详细信息，请参阅<xref:System.Attribute>。</xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="2fe24-107">For more information, see <xref:System.Attribute>.</span></span>  
  
 <span data-ttu-id="2fe24-108">属性规范，如︰</span><span class="sxs-lookup"><span data-stu-id="2fe24-108">An attribute specification such as:</span></span>  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 <span data-ttu-id="2fe24-109">是在概念上等效于此︰</span><span class="sxs-lookup"><span data-stu-id="2fe24-109">is conceptually equivalent to this:</span></span>  
  
```vb  
Dim anonymousAuthorObject As Author = New Author("P. Ackerman")  
anonymousAuthorObject.version = 1.1  
```  
  
 <span data-ttu-id="2fe24-110">但是，直到不执行的代码`SampleClass`的特性查询。</span><span class="sxs-lookup"><span data-stu-id="2fe24-110">However, the code is not executed until `SampleClass` is queried for attributes.</span></span> <span data-ttu-id="2fe24-111">调用`GetCustomAttributes`上`SampleClass`导致`Author`对象构造并初始化为更高版本。</span><span class="sxs-lookup"><span data-stu-id="2fe24-111">Calling `GetCustomAttributes` on `SampleClass` causes an `Author` object to be constructed and initialized as above.</span></span> <span data-ttu-id="2fe24-112">如果类具有其他属性，其他属性对象以类似方式构造。</span><span class="sxs-lookup"><span data-stu-id="2fe24-112">If the class has other attributes, other attribute objects are constructed similarly.</span></span> <span data-ttu-id="2fe24-113">`GetCustomAttributes`然后返回`Author`对象和数组中的任何其他属性对象。</span><span class="sxs-lookup"><span data-stu-id="2fe24-113">`GetCustomAttributes` then returns the `Author` object and any other attribute objects in an array.</span></span> <span data-ttu-id="2fe24-114">然后，可以循环遍历此数组，确定哪些属性所应用基于每个数组元素的类型，并从属性对象提取信息。</span><span class="sxs-lookup"><span data-stu-id="2fe24-114">You can then iterate over this array, determine what attributes were applied based on the type of each array element, and extract information from the attribute objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fe24-115">示例</span><span class="sxs-lookup"><span data-stu-id="2fe24-115">Example</span></span>  
 <span data-ttu-id="2fe24-116">下面是一个完整的示例。</span><span class="sxs-lookup"><span data-stu-id="2fe24-116">Here is a complete example.</span></span> <span data-ttu-id="2fe24-117">定义自定义属性、 将其应用于多个实体，并通过反射进行检索。</span><span class="sxs-lookup"><span data-stu-id="2fe24-117">A custom attribute is defined, applied to several entities, and retrieved via reflection.</span></span>  
  
```vb  
' Multiuse attribute  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct,   
                       AllowMultiple:=True)>   
Public Class Author  
    Inherits System.Attribute  
    Private name As String  
    Public version As Double  
    Sub New(ByVal authorName As String)  
        name = authorName  
  
        ' Default value  
        version = 1.0  
    End Sub  
  
    Function GetName() As String  
        Return name  
    End Function          
End Class  
  
' Class with the Author attribute  
<Author("P. Ackerman")>   
Public Class FirstClass  
End Class  
  
' Class without the Author attribute  
Public Class SecondClass  
End Class  
  
' Class with multiple Author attributes.  
<Author("P. Ackerman"), Author("R. Koch", Version:=2.0)>   
Public Class ThirdClass  
End Class  
  
Class TestAuthorAttribute  
    Sub Main()  
        PrintAuthorInfo(GetType(FirstClass))  
        PrintAuthorInfo(GetType(SecondClass))  
        PrintAuthorInfo(GetType(ThirdClass))  
    End Sub  
  
    Private Shared Sub PrintAuthorInfo(ByVal t As System.Type)  
        System.Console.WriteLine("Author information for {0}", t)  
  
        ' Using reflection  
        Dim attrs() As System.Attribute = System.Attribute.GetCustomAttributes(t)  
  
        ' Displaying output  
        For Each attr In attrs  
            Dim a As Author = CType(attr, Author)  
            System.Console.WriteLine("   {0}, version {1:f}", a.GetName(), a.version)  
        Next              
    End Sub  
  
    ' Output:  
    '   Author information for FirstClass  
    '     P. Ackerman, version 1.00  
    ' Author information for SecondClass  
    ' Author information for ThirdClass  
    '  R. Koch, version 2.00  
    '  P. Ackerman, version 1.00  
  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="2fe24-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2fe24-118">See Also</span></span>  
 <span data-ttu-id="2fe24-119"><xref:System.Reflection></xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="2fe24-119"><xref:System.Reflection></span></span>   
 <span data-ttu-id="2fe24-120"><xref:System.Attribute></xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="2fe24-120"><xref:System.Attribute></span></span>   
<span data-ttu-id="2fe24-121"> [Visual Basic 编程指南](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2fe24-121"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="2fe24-122"> [检索存储在特性中的信息](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c) </span><span class="sxs-lookup"><span data-stu-id="2fe24-122"> [Retrieving Information Stored in Attributes](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c) </span></span>  
<span data-ttu-id="2fe24-123"> [反射 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="2fe24-123"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
<span data-ttu-id="2fe24-124"> [特性 (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span><span class="sxs-lookup"><span data-stu-id="2fe24-124"> [Attributes (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span></span>  
<span data-ttu-id="2fe24-125"> [创建自定义特性 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="2fe24-125"> [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)</span></span>
