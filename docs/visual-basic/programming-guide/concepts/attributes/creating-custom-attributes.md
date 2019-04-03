---
title: 创建自定义特性 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
ms.openlocfilehash: 90e8e9b9a3fa8e0b488f41d035b017d6113213b5
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814349"
---
# <a name="creating-custom-attributes-visual-basic"></a><span data-ttu-id="4cb2a-102">创建自定义特性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4cb2a-102">Creating Custom Attributes (Visual Basic)</span></span>
<span data-ttu-id="4cb2a-103">可通过定义特性类创建自己的自定义特性，特性类是直接或间接派生自 <xref:System.Attribute> 的类，可快速轻松地识别元数据中的特性定义。</span><span class="sxs-lookup"><span data-stu-id="4cb2a-103">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="4cb2a-104">假设希望使用编写类型的程序员的姓名来标记该类型。</span><span class="sxs-lookup"><span data-stu-id="4cb2a-104">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="4cb2a-105">可能需要定义一个自定义 `Author` 特性类：</span><span class="sxs-lookup"><span data-stu-id="4cb2a-105">You might define a custom `Author` attribute class:</span></span>  
  
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
  
 <span data-ttu-id="4cb2a-106">类名是该特性的名称，即 `Author`。</span><span class="sxs-lookup"><span data-stu-id="4cb2a-106">The class name is the attribute's name, `Author`.</span></span> <span data-ttu-id="4cb2a-107">由于该类派生自 `System.Attribute`，因此它是一个自定义特性类。</span><span class="sxs-lookup"><span data-stu-id="4cb2a-107">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="4cb2a-108">构造函数的参数是自定义特性的位置参数。</span><span class="sxs-lookup"><span data-stu-id="4cb2a-108">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="4cb2a-109">在此示例中，`name` 是位置参数。</span><span class="sxs-lookup"><span data-stu-id="4cb2a-109">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="4cb2a-110">所有公共读写字段或属性都是命名参数。</span><span class="sxs-lookup"><span data-stu-id="4cb2a-110">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="4cb2a-111">在本例中，`version` 是唯一的命名参数。</span><span class="sxs-lookup"><span data-stu-id="4cb2a-111">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="4cb2a-112">请注意，使用 `AttributeUsage` 特性可使 `Author` 特性仅对类和 `Structure` 声明有效。</span><span class="sxs-lookup"><span data-stu-id="4cb2a-112">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `Structure` declarations.</span></span>  
  
 <span data-ttu-id="4cb2a-113">可按如下方式使用这一新特性：</span><span class="sxs-lookup"><span data-stu-id="4cb2a-113">You could use this new attribute as follows:</span></span>  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 <span data-ttu-id="4cb2a-114">`AttributeUsage` 有一个命名参数 `AllowMultiple`，通过此命名参数可一次或多次使用自定义特性。</span><span class="sxs-lookup"><span data-stu-id="4cb2a-114">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="4cb2a-115">下面的代码示例创建了一个多用特性。</span><span class="sxs-lookup"><span data-stu-id="4cb2a-115">In the following code example, a multiuse attribute is created.</span></span>  
  
```vb  
' multiuse attribute  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct,   
                       AllowMultiple:=True)>   
Public Class Author  
    Inherits System.Attribute  
```  
  
 <span data-ttu-id="4cb2a-116">在下面的代码示例中，某个类应用了同一类型的多个特性。</span><span class="sxs-lookup"><span data-stu-id="4cb2a-116">In the following code example, multiple attributes of the same type are applied to a class.</span></span>  
  
```vb  
<Author("P. Ackerman", Version:=1.1),   
Author("R. Koch", Version:=1.2)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
    ' R. Koch's code goes here...  
End Class  
```  
  
> [!NOTE]
>  <span data-ttu-id="4cb2a-117">如果特性类包含属性，则该属性必须为读写属性。</span><span class="sxs-lookup"><span data-stu-id="4cb2a-117">If your attribute class contains a property, that property must be read-write.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb2a-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="4cb2a-118">See also</span></span>

- <xref:System.Reflection>
- [<span data-ttu-id="4cb2a-119">Visual Basic 编程指南</span><span class="sxs-lookup"><span data-stu-id="4cb2a-119">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="4cb2a-120">编写自定义特性</span><span class="sxs-lookup"><span data-stu-id="4cb2a-120">Writing Custom Attributes</span></span>](../../../../standard/attributes/writing-custom-attributes.md)
- [<span data-ttu-id="4cb2a-121">反射 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4cb2a-121">Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/reflection.md)
- [<span data-ttu-id="4cb2a-122">属性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4cb2a-122">Attributes (Visual Basic)</span></span>](../../../../visual-basic/language-reference/attributes.md)
- [<span data-ttu-id="4cb2a-123">使用反射访问特性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4cb2a-123">Accessing Attributes by Using Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
- [<span data-ttu-id="4cb2a-124">AttributeUsage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4cb2a-124">AttributeUsage (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
