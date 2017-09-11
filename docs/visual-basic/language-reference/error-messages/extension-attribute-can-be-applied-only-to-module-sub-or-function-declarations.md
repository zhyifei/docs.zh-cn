---
title: "Extension 特性可以只能应用于 Module、 Sub 或 Function 声明。 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36550
- vbc36550
dev_langs:
- VB
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: e88241180fe1320bfd1db90a38a9a7560ae3dead
ms.contentlocale: zh-cn
ms.lasthandoff: 05/23/2017

---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a><span data-ttu-id="ced2a-102">Extension 特性可以只能应用于 Module、 Sub 或 Function 声明。</span><span class="sxs-lookup"><span data-stu-id="ced2a-102">&#39;Extension&#39; attribute can be applied only to &#39;Module&#39;, &#39;Sub&#39;, or &#39;Function&#39; declarations</span></span>
<span data-ttu-id="ced2a-103">若要扩展在 Visual Basic 中的数据类型的唯一方法是定义标准模块内的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="ced2a-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="ced2a-104">扩展方法可以是`Sub`过程或`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="ced2a-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="ced2a-105">所有扩展方法都必须都标记为扩展属性`<Extension()>`，从<xref:System.Runtime.CompilerServices?displayProperty=fullName>命名空间。</xref:System.Runtime.CompilerServices?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="ced2a-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="ced2a-106">（可选） 包含扩展方法的模块可能标记为相同的方式。</span><span class="sxs-lookup"><span data-stu-id="ced2a-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="ced2a-107">其他扩展属性的使用方式均有效。</span><span class="sxs-lookup"><span data-stu-id="ced2a-107">No other use of the extension attribute is valid.</span></span>  
  
 <span data-ttu-id="ced2a-108">**错误 ID:** BC36550</span><span class="sxs-lookup"><span data-stu-id="ced2a-108">**Error ID:** BC36550</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ced2a-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="ced2a-109">To correct this error</span></span>  
  
-   <span data-ttu-id="ced2a-110">删除扩展属性。</span><span class="sxs-lookup"><span data-stu-id="ced2a-110">Remove the extension attribute.</span></span>  
  
-   <span data-ttu-id="ced2a-111">与封闭模块中定义的方法重新设计您的扩展。</span><span class="sxs-lookup"><span data-stu-id="ced2a-111">Redesign your extension as a method, defined in an enclosing module.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ced2a-112">示例</span><span class="sxs-lookup"><span data-stu-id="ced2a-112">Example</span></span>  
 <span data-ttu-id="ced2a-113">下面的示例定义`Print`方法`String`数据类型。</span><span class="sxs-lookup"><span data-stu-id="ced2a-113">The following example defines a `Print` method for the `String` data type.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ced2a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ced2a-114">See Also</span></span>  
 <span data-ttu-id="ced2a-115">[属性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span><span class="sxs-lookup"><span data-stu-id="ced2a-115">[Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span></span>  
<span data-ttu-id="ced2a-116"> [扩展方法](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md) </span><span class="sxs-lookup"><span data-stu-id="ced2a-116"> [Extension Methods](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md) </span></span>  
<span data-ttu-id="ced2a-117"> [Module 语句](../../../visual-basic/language-reference/statements/module-statement.md)</span><span class="sxs-lookup"><span data-stu-id="ced2a-117"> [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)</span></span>

