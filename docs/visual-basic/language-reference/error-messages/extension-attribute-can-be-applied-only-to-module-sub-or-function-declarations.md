---
title: "&#39;扩展 &#39;属性可以仅可应用到 &#39;模块 &#39;，&#39;Sub &#39;，或 &#39;函数 &#39;声明"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords: BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9d77933c52484eb934501107d1ddad15f0eca826
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a><span data-ttu-id="90272-102">&#39;扩展 &#39;属性可以仅可应用到 &#39;模块 &#39;，&#39;Sub &#39;，或 &#39;函数 &#39;声明</span><span class="sxs-lookup"><span data-stu-id="90272-102">&#39;Extension&#39; attribute can be applied only to &#39;Module&#39;, &#39;Sub&#39;, or &#39;Function&#39; declarations</span></span>
<span data-ttu-id="90272-103">扩展 Visual Basic 中的数据类型的唯一方法是定义在标准模块内的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="90272-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="90272-104">扩展方法可以是`Sub`过程或`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="90272-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="90272-105">所有扩展方法必须具有扩展属性中，都标记`<Extension()>`，从<xref:System.Runtime.CompilerServices?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="90272-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="90272-106">（可选） 可能在相同的方式标记为包含的扩展方法的模块。</span><span class="sxs-lookup"><span data-stu-id="90272-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="90272-107">其他扩展属性的使用方式均有效。</span><span class="sxs-lookup"><span data-stu-id="90272-107">No other use of the extension attribute is valid.</span></span>  
  
 <span data-ttu-id="90272-108">**错误 ID:** BC36550</span><span class="sxs-lookup"><span data-stu-id="90272-108">**Error ID:** BC36550</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="90272-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="90272-109">To correct this error</span></span>  
  
-   <span data-ttu-id="90272-110">删除扩展属性。</span><span class="sxs-lookup"><span data-stu-id="90272-110">Remove the extension attribute.</span></span>  
  
-   <span data-ttu-id="90272-111">与的外层模块中定义的方法重新设计你的扩展。</span><span class="sxs-lookup"><span data-stu-id="90272-111">Redesign your extension as a method, defined in an enclosing module.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90272-112">示例</span><span class="sxs-lookup"><span data-stu-id="90272-112">Example</span></span>  
 <span data-ttu-id="90272-113">下面的示例定义`Print`方法`String`数据类型。</span><span class="sxs-lookup"><span data-stu-id="90272-113">The following example defines a `Print` method for the `String` data type.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="90272-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90272-114">See Also</span></span>  
 [<span data-ttu-id="90272-115">属性概述</span><span class="sxs-lookup"><span data-stu-id="90272-115">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="90272-116">扩展方法</span><span class="sxs-lookup"><span data-stu-id="90272-116">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
 [<span data-ttu-id="90272-117">Module 语句</span><span class="sxs-lookup"><span data-stu-id="90272-117">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
