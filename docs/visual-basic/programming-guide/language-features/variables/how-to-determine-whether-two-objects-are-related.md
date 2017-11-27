---
title: "如何：确定两个对象是否相关 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7824742459fca355c0043ad8ed20a26330402c05
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a><span data-ttu-id="2434d-102">如何：确定两个对象是否相关 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2434d-102">How to: Determine Whether Two Objects Are Related (Visual Basic)</span></span>
<span data-ttu-id="2434d-103">你可以比较两个对象以确定关系，如果有，从中创建的类之间。</span><span class="sxs-lookup"><span data-stu-id="2434d-103">You can compare two objects to determine the relationship, if any, between the classes from which they are created.</span></span> <span data-ttu-id="2434d-104"><xref:System.Type.IsInstanceOfType%2A>方法<xref:System.Type?displayProperty=nameWithType>类返回`True`如果指定的类继承自当前类中，或如果当前类型是接口，支持由指定的类。</span><span class="sxs-lookup"><span data-stu-id="2434d-104">The <xref:System.Type.IsInstanceOfType%2A> method of the <xref:System.Type?displayProperty=nameWithType> class returns `True` if the specified class inherits from the current class, or if the current type is an interface supported by the specified class.</span></span>  
  
### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a><span data-ttu-id="2434d-105">若要确定是否一个对象继承自另一个对象的类或接口</span><span class="sxs-lookup"><span data-stu-id="2434d-105">To determine if one object inherits from another object's class or interface</span></span>  
  
1.  <span data-ttu-id="2434d-106">在你认为的对象可能是基类型，则调用<xref:System.Object.GetType%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="2434d-106">On the object you think might be of the base type, invoke the <xref:System.Object.GetType%2A> method.</span></span>  
  
2.  <span data-ttu-id="2434d-107">上<xref:System.Type?displayProperty=nameWithType>返回对象<xref:System.Object.GetType%2A>，调用<xref:System.Type.IsInstanceOfType%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="2434d-107">On the <xref:System.Type?displayProperty=nameWithType> object returned by <xref:System.Object.GetType%2A>, invoke the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>  
  
3.  <span data-ttu-id="2434d-108">中的自变量列表<xref:System.Type.IsInstanceOfType%2A>，指定的派生类型可能是你认为的对象。</span><span class="sxs-lookup"><span data-stu-id="2434d-108">In the argument list for <xref:System.Type.IsInstanceOfType%2A>, specify the object you think might be of the derived type.</span></span>  
  
     <span data-ttu-id="2434d-109"><xref:System.Type.IsInstanceOfType%2A>返回`True`如果其自变量类型都继承自<xref:System.Type?displayProperty=nameWithType>对象类型。</span><span class="sxs-lookup"><span data-stu-id="2434d-109"><xref:System.Type.IsInstanceOfType%2A> returns `True` if its argument type inherits from the <xref:System.Type?displayProperty=nameWithType> object type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2434d-110">示例</span><span class="sxs-lookup"><span data-stu-id="2434d-110">Example</span></span>  
 <span data-ttu-id="2434d-111">下面的示例确定一个对象是否表示从另一个对象的类派生的类。</span><span class="sxs-lookup"><span data-stu-id="2434d-111">The following example determines whether one object represents a class derived from another object's class.</span></span>  
  
```  
Public Class baseClass  
End Class  
Public Class derivedClass : Inherits baseClass  
End Class  
Public Class testTheseClasses  
    Public Sub seeIfRelated()  
        Dim baseObj As Object = New baseClass()  
        Dim derivedObj As Object = New derivedClass()  
        Dim related As Boolean  
        related = baseObj.GetType().IsInstanceOfType(derivedObj)  
        MsgBox(CStr(related))  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="2434d-112">请注意对的调用中的两个对象变量的意外的位置<xref:System.Type.IsInstanceOfType%2A>。</span><span class="sxs-lookup"><span data-stu-id="2434d-112">Note the unexpected placement of the two object variables in the call to <xref:System.Type.IsInstanceOfType%2A>.</span></span> <span data-ttu-id="2434d-113">假定的基类型用于生成<xref:System.Type?displayProperty=nameWithType>类，并且假定的派生的类型的自变量作为传递<xref:System.Type.IsInstanceOfType%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="2434d-113">The supposed base type is used to generate the <xref:System.Type?displayProperty=nameWithType> class, and the supposed derived type is passed as an argument to the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2434d-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2434d-114">See Also</span></span>  
 <xref:System.Object.GetType%2A>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Type.IsInstanceOfType%2A>  
 [<span data-ttu-id="2434d-115">Object 数据类型</span><span class="sxs-lookup"><span data-stu-id="2434d-115">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="2434d-116">对象变量</span><span class="sxs-lookup"><span data-stu-id="2434d-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="2434d-117">对象变量值</span><span class="sxs-lookup"><span data-stu-id="2434d-117">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="2434d-118">如何：确定两个对象是否相同</span><span class="sxs-lookup"><span data-stu-id="2434d-118">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
