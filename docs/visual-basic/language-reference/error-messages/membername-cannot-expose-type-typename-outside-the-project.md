---
title: "&#39;&lt;membername&gt;&#39; 不能公开类型 &#39;&lt;typename&gt;&#39; 通过在项目外部&lt;containertype&gt; &#39;&lt;containertypename&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords: BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fd64c815286a5ffec111bcf1f68674a8e3558403
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="39ltmembernamegt39-cannot-expose-type-39lttypenamegt39-outside-the-project-through-ltcontainertypegt-39ltcontainertypenamegt39"></a>&#39;&lt;membername&gt;&#39; 不能公开类型 &#39;&lt;typename&gt;&#39; 通过在项目外部&lt;containertype&gt; &#39;&lt;containertypename&gt;&#39;
变量、 过程参数或函数返回暴露于其容器之外，但它被声明为必须不公开容器之外的类型。  
  
 下面的主干代码演示生成此错误的情况。  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 声明的类型`Protected`， `Friend`， `Protected Friend`，或`Private`旨在其声明上下文外的访问受到限制。 使用的数据，将无法具有受限制更少访问的变量的类型实现此目的。 在上面的主干代码`exposedVar`是`Public`和将公开`privateClass`到不应有权访问它的代码。  
  
 **错误 ID:** BC30909  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   变量、 过程参数或函数的访问级别的更改返回让至少为其数据类型的访问级别限制性最高。  
  
## <a name="see-also"></a>另请参阅  
 [在 Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
