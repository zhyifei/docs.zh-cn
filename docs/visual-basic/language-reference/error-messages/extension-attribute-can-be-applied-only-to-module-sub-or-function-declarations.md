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
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a>&#39;扩展 &#39;属性可以仅可应用到 &#39;模块 &#39;，&#39;Sub &#39;，或 &#39;函数 &#39;声明
扩展 Visual Basic 中的数据类型的唯一方法是定义在标准模块内的扩展方法。 扩展方法可以是`Sub`过程或`Function`过程。 所有扩展方法必须具有扩展属性中，都标记`<Extension()>`，从<xref:System.Runtime.CompilerServices?displayProperty=nameWithType>命名空间。 （可选） 可能在相同的方式标记为包含的扩展方法的模块。 其他扩展属性的使用方式均有效。  
  
 **错误 ID:** BC36550  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   删除扩展属性。  
  
-   与的外层模块中定义的方法重新设计你的扩展。  
  
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
  
## <a name="see-also"></a>另请参阅  
 [属性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [扩展方法](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
 [Module 语句](../../../visual-basic/language-reference/statements/module-statement.md)
