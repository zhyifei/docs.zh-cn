---
title: '&#39;扩展&#39;属性可以仅可应用到&#39;模块&#39;， &#39;Sub&#39;，或&#39;函数&#39;声明'
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: fabd602f31a362fe33954253d565e86a065e0a83
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718229"
---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a>&#39;扩展&#39;属性可以仅可应用到&#39;模块&#39;， &#39;Sub&#39;，或&#39;函数&#39;声明
扩展 Visual Basic 中的数据类型的唯一方法是定义在标准模块内的扩展方法。 扩展方法会很`Sub`过程或`Function`过程。 必须使用扩展属性中，标记所有扩展方法`<Extension()>`，从<xref:System.Runtime.CompilerServices?displayProperty=nameWithType>命名空间。 （可选） 包含扩展方法的模块可能标记相同的方式。 扩展属性的任何其他使用不都有效。  
  
 **错误 ID:** BC36550  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   删除扩展属性。  
  
-   将扩展重新设计的外层模块中定义的方法。  
  
## <a name="example"></a>示例  
 下面的示例定义`Print`方法`String`数据类型。  
  
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
  
## <a name="see-also"></a>请参阅
- [属性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [扩展方法](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [Module 语句](../../../visual-basic/language-reference/statements/module-statement.md)
