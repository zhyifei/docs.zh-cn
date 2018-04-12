---
title: 默认属性访问之间不明确继承的接口成员 &#39;&lt;defaultpropertyname&gt;&#39; 的接口 &#39;&lt;interfacename1&gt;&#39; 和 &#39;&lt;defaultpropertyname&gt;&#39; 的接口 &#39;&lt;interfacename2&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 23d613668ee2d92484117759dd614ed2cad4bcb2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-39ltdefaultpropertynamegt39-of-interface-39ltinterfacename1gt39-and-39ltdefaultpropertynamegt39-of-interface-39ltinterfacename2gt39"></a><span data-ttu-id="c4282-102">默认属性访问之间不明确继承的接口成员 &#39;&lt;defaultpropertyname&gt;&#39; 的接口 &#39;&lt;interfacename1&gt;&#39; 和 &#39;&lt;defaultpropertyname&gt;&#39; 的接口 &#39;&lt;interfacename2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="c4282-102">Default property access is ambiguous between the inherited interface members &#39;&lt;defaultpropertyname&gt;&#39; of interface &#39;&lt;interfacename1&gt;&#39; and &#39;&lt;defaultpropertyname&gt;&#39; of interface &#39;&lt;interfacename2&gt;&#39;</span></span>
<span data-ttu-id="c4282-103">接口继承自两个接口，其中每个声明具有相同名称的默认属性。</span><span class="sxs-lookup"><span data-stu-id="c4282-103">An interface inherits from two interfaces, each of which declares a default property with the same name.</span></span> <span data-ttu-id="c4282-104">编译器无法解析访问而无需限定此默认属性。</span><span class="sxs-lookup"><span data-stu-id="c4282-104">The compiler cannot resolve an access to this default property without qualification.</span></span> <span data-ttu-id="c4282-105">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="c4282-105">The following example illustrates this.</span></span>  
  
```  
Public Interface Iface1  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface2  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface3  
    Inherits Iface1, Iface2  
End Interface  
Public Class testClass  
    Public Sub accessDefaultProperty()  
        Dim testObj As Iface3  
        Dim testInt As Integer = testObj(1)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="c4282-106">当指定`testObj(1)`，编译器会尝试将它解析为默认属性。</span><span class="sxs-lookup"><span data-stu-id="c4282-106">When you specify `testObj(1)`, the compiler tries to resolve it to the default property.</span></span> <span data-ttu-id="c4282-107">但是，有两个可能的默认属性由于继承的接口，因此，编译器将引发此错误。</span><span class="sxs-lookup"><span data-stu-id="c4282-107">However, there are two possible default properties because of the inherited interfaces, so the compiler signals this error.</span></span>  
  
 <span data-ttu-id="c4282-108">**错误 ID:** BC30686</span><span class="sxs-lookup"><span data-stu-id="c4282-108">**Error ID:** BC30686</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c4282-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="c4282-109">To correct this error</span></span>  
  
-   <span data-ttu-id="c4282-110">避免继承具有相同名称的任何成员。</span><span class="sxs-lookup"><span data-stu-id="c4282-110">Avoid inheriting any members with the same name.</span></span> <span data-ttu-id="c4282-111">在前面的示例中，如果`testObj`不需要的任何成员，即`Iface2`，然后将其声明，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c4282-111">In the preceding example, if `testObj` does not need any of the members of, say, `Iface2`, then declare it as follows:</span></span>  
  
    ```  
    Dim testObj As Iface1  
    ```  
  
     <span data-ttu-id="c4282-112">- 或 -</span><span class="sxs-lookup"><span data-stu-id="c4282-112">-or-</span></span>  
  
-   <span data-ttu-id="c4282-113">在类中实现继承的接口。</span><span class="sxs-lookup"><span data-stu-id="c4282-113">Implement the inheriting interface in a class.</span></span> <span data-ttu-id="c4282-114">然后你可以实现每个具有不同名称的继承属性。</span><span class="sxs-lookup"><span data-stu-id="c4282-114">Then you can implement each of the inherited properties with different names.</span></span> <span data-ttu-id="c4282-115">但是，仅有一种可以实现的类的默认属性。</span><span class="sxs-lookup"><span data-stu-id="c4282-115">However, only one of them can be the default property of the implementing class.</span></span> <span data-ttu-id="c4282-116">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="c4282-116">The following example illustrates this.</span></span>  
  
    ```  
    Public Class useIface3  
        Implements Iface3  
        Default Public Property prop1(ByVal arg As Integer) As Integer Implements Iface1.prop  
            ' Insert code to define Get and Set procedures for prop1.  
        End Property  
        Public Property prop2(ByVal arg As Integer) As Integer Implements Iface2.prop  
            ' Insert code to define Get and Set procedures for prop2.  
        End Property  
    End Class  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c4282-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4282-117">See Also</span></span>  
 [<span data-ttu-id="c4282-118">接口</span><span class="sxs-lookup"><span data-stu-id="c4282-118">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
