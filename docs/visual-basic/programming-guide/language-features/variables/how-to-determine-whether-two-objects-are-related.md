---
title: 如何：确定两个对象是否相关
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: b3f5fc017166ba9cf28359db5de850c81b73bd69
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348632"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a><span data-ttu-id="1d61e-102">如何：确定两个对象是否相关 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1d61e-102">How to: Determine Whether Two Objects Are Related (Visual Basic)</span></span>

<span data-ttu-id="1d61e-103">您可以比较两个对象，以确定从中创建它们的类之间的关系（如果有）。</span><span class="sxs-lookup"><span data-stu-id="1d61e-103">You can compare two objects to determine the relationship, if any, between the classes from which they are created.</span></span> <span data-ttu-id="1d61e-104">如果指定的类从当前类继承，或者当前类型是指定类支持的接口，则 <xref:System.Type?displayProperty=nameWithType> 类的 <xref:System.Type.IsInstanceOfType%2A> 方法返回 `True`。</span><span class="sxs-lookup"><span data-stu-id="1d61e-104">The <xref:System.Type.IsInstanceOfType%2A> method of the <xref:System.Type?displayProperty=nameWithType> class returns `True` if the specified class inherits from the current class, or if the current type is an interface supported by the specified class.</span></span>

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a><span data-ttu-id="1d61e-105">确定一个对象是否继承自另一个对象的类或接口</span><span class="sxs-lookup"><span data-stu-id="1d61e-105">To determine if one object inherits from another object's class or interface</span></span>

1. <span data-ttu-id="1d61e-106">在您认为可能是基类型的对象上，调用 <xref:System.Object.GetType%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="1d61e-106">On the object you think might be of the base type, invoke the <xref:System.Object.GetType%2A> method.</span></span>

2. <span data-ttu-id="1d61e-107">在 <xref:System.Object.GetType%2A>返回的 <xref:System.Type?displayProperty=nameWithType> 对象上，调用 <xref:System.Type.IsInstanceOfType%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="1d61e-107">On the <xref:System.Type?displayProperty=nameWithType> object returned by <xref:System.Object.GetType%2A>, invoke the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

3. <span data-ttu-id="1d61e-108">在 <xref:System.Type.IsInstanceOfType%2A>的参数列表中，指定你认为可能是派生类型的对象。</span><span class="sxs-lookup"><span data-stu-id="1d61e-108">In the argument list for <xref:System.Type.IsInstanceOfType%2A>, specify the object you think might be of the derived type.</span></span>

    <span data-ttu-id="1d61e-109">如果 `True` 参数类型从 <xref:System.Type?displayProperty=nameWithType> 对象类型继承，则 <xref:System.Type.IsInstanceOfType%2A> 返回。</span><span class="sxs-lookup"><span data-stu-id="1d61e-109"><xref:System.Type.IsInstanceOfType%2A> returns `True` if its argument type inherits from the <xref:System.Type?displayProperty=nameWithType> object type.</span></span>

## <a name="example"></a><span data-ttu-id="1d61e-110">示例</span><span class="sxs-lookup"><span data-stu-id="1d61e-110">Example</span></span>
 <span data-ttu-id="1d61e-111">下面的示例确定一个对象是否表示一个派生自另一个对象的类的类。</span><span class="sxs-lookup"><span data-stu-id="1d61e-111">The following example determines whether one object represents a class derived from another object's class.</span></span>

```vb
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

<span data-ttu-id="1d61e-112">请注意，在调用 <xref:System.Type.IsInstanceOfType%2A>时，两个对象变量的意外位置。</span><span class="sxs-lookup"><span data-stu-id="1d61e-112">Note the unexpected placement of the two object variables in the call to <xref:System.Type.IsInstanceOfType%2A>.</span></span> <span data-ttu-id="1d61e-113">假定的基类型用于生成 <xref:System.Type?displayProperty=nameWithType> 类，假设的派生类型作为参数传递给 <xref:System.Type.IsInstanceOfType%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="1d61e-113">The supposed base type is used to generate the <xref:System.Type?displayProperty=nameWithType> class, and the supposed derived type is passed as an argument to the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d61e-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d61e-114">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [<span data-ttu-id="1d61e-115">Object 数据类型</span><span class="sxs-lookup"><span data-stu-id="1d61e-115">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="1d61e-116">对象变量</span><span class="sxs-lookup"><span data-stu-id="1d61e-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="1d61e-117">对象变量值</span><span class="sxs-lookup"><span data-stu-id="1d61e-117">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="1d61e-118">如何：确定两个对象是否相同</span><span class="sxs-lookup"><span data-stu-id="1d61e-118">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
