---
title: '&#39;扩展&#39;属性可以仅可应用到&#39;模块&#39;，&#39;子&#39;，或&#39;函数&#39;声明'
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: d7f8829cb879d612711ac6bcc6bf4aa065fbe323
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a><span data-ttu-id="13fbc-102">&#39;扩展&#39;属性可以仅可应用到&#39;模块&#39;，&#39;子&#39;，或&#39;函数&#39;声明</span><span class="sxs-lookup"><span data-stu-id="13fbc-102">&#39;Extension&#39; attribute can be applied only to &#39;Module&#39;, &#39;Sub&#39;, or &#39;Function&#39; declarations</span></span>
<span data-ttu-id="13fbc-103">扩展 Visual Basic 中的数据类型的唯一方法是定义在标准模块内的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="13fbc-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="13fbc-104">扩展方法可以是`Sub`过程或`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="13fbc-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="13fbc-105">所有扩展方法必须具有扩展属性中，都标记`<Extension()>`，从<xref:System.Runtime.CompilerServices?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="13fbc-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="13fbc-106">（可选） 可能在相同的方式标记为包含的扩展方法的模块。</span><span class="sxs-lookup"><span data-stu-id="13fbc-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="13fbc-107">其他扩展属性的使用方式均有效。</span><span class="sxs-lookup"><span data-stu-id="13fbc-107">No other use of the extension attribute is valid.</span></span>  
  
 <span data-ttu-id="13fbc-108">**错误 ID:** BC36550</span><span class="sxs-lookup"><span data-stu-id="13fbc-108">**Error ID:** BC36550</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="13fbc-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="13fbc-109">To correct this error</span></span>  
  
-   <span data-ttu-id="13fbc-110">删除扩展属性。</span><span class="sxs-lookup"><span data-stu-id="13fbc-110">Remove the extension attribute.</span></span>  
  
-   <span data-ttu-id="13fbc-111">与的外层模块中定义的方法重新设计你的扩展。</span><span class="sxs-lookup"><span data-stu-id="13fbc-111">Redesign your extension as a method, defined in an enclosing module.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13fbc-112">示例</span><span class="sxs-lookup"><span data-stu-id="13fbc-112">Example</span></span>  
 <span data-ttu-id="13fbc-113">下面的示例定义`Print`方法`String`数据类型。</span><span class="sxs-lookup"><span data-stu-id="13fbc-113">The following example defines a `Print` method for the `String` data type.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="13fbc-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="13fbc-114">See Also</span></span>  
 [<span data-ttu-id="13fbc-115">属性概述</span><span class="sxs-lookup"><span data-stu-id="13fbc-115">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="13fbc-116">扩展方法</span><span class="sxs-lookup"><span data-stu-id="13fbc-116">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
 [<span data-ttu-id="13fbc-117">Module 语句</span><span class="sxs-lookup"><span data-stu-id="13fbc-117">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
