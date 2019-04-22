---
title: “Extension”特性只能应用于“Module”、“Sub”或“Function”声明。
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: a4561359e4d7cb0f6ebe44a5deb09b3374556ed8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58826179"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a><span data-ttu-id="3c952-102">“Extension”特性只能应用于“Module”、“Sub”或“Function”声明。</span><span class="sxs-lookup"><span data-stu-id="3c952-102">'Extension' attribute can be applied only to 'Module', 'Sub', or 'Function' declarations</span></span>
<span data-ttu-id="3c952-103">扩展 Visual Basic 中的数据类型的唯一方法是定义在标准模块内的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="3c952-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="3c952-104">扩展方法会很`Sub`过程或`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="3c952-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="3c952-105">必须使用扩展属性中，标记所有扩展方法`<Extension()>`，从<xref:System.Runtime.CompilerServices?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="3c952-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="3c952-106">（可选） 包含扩展方法的模块可能标记相同的方式。</span><span class="sxs-lookup"><span data-stu-id="3c952-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="3c952-107">扩展属性的任何其他使用不都有效。</span><span class="sxs-lookup"><span data-stu-id="3c952-107">No other use of the extension attribute is valid.</span></span>  
  
 <span data-ttu-id="3c952-108">**错误 ID:** BC36550</span><span class="sxs-lookup"><span data-stu-id="3c952-108">**Error ID:** BC36550</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3c952-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="3c952-109">To correct this error</span></span>  
  
-   <span data-ttu-id="3c952-110">删除扩展属性。</span><span class="sxs-lookup"><span data-stu-id="3c952-110">Remove the extension attribute.</span></span>  
  
-   <span data-ttu-id="3c952-111">将扩展重新设计的外层模块中定义的方法。</span><span class="sxs-lookup"><span data-stu-id="3c952-111">Redesign your extension as a method, defined in an enclosing module.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c952-112">示例</span><span class="sxs-lookup"><span data-stu-id="3c952-112">Example</span></span>  
 <span data-ttu-id="3c952-113">下面的示例定义`Print`方法`String`数据类型。</span><span class="sxs-lookup"><span data-stu-id="3c952-113">The following example defines a `Print` method for the `String` data type.</span></span>  
  
```  
Imports StringUtility  
Imports System.Runtime.CompilerServices  
Namespace StringUtility  
    <Extension()>   
    Module StringExtensions  
        <Extension()>   
        Public Sub Print (ByVal str As String)  
            Console.WriteLine(str)  
        End Sub  
    End Module  
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c952-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c952-114">See also</span></span>

- [<span data-ttu-id="3c952-115">属性概述</span><span class="sxs-lookup"><span data-stu-id="3c952-115">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="3c952-116">扩展方法</span><span class="sxs-lookup"><span data-stu-id="3c952-116">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="3c952-117">Module 语句</span><span class="sxs-lookup"><span data-stu-id="3c952-117">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
