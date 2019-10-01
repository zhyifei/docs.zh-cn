---
title: “<membername>”不能通过 <typename>“<containertype>”在项目外部公开类型“<containertypename>”
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: ca67e74d7790352bd1842cb8a59fe1525af6e18c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700898"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a>"\<membername >" 无法通过 \<containertype > "\<containertypename >" 在项目外部公开类型 "\<typename >"
变量、过程参数或函数返回在其容器外部公开，但它被声明为不得在容器外部公开的类型。  
  
 以下框架代码显示了生成此错误的情况。  
  
```vb  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 声明为 `Protected`、`Friend`、`Protected Friend` 或 @no__t 3 的类型旨在在其声明上下文之外进行有限的访问。 将其用作受限访问的变量的数据类型将会降低此目的。 在上面的主干代码中，`exposedVar` @no__t 为-1，并将 `privateClass` 公开给不应访问它的代码。  
  
 **错误 ID：** BC30909  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 更改变量、过程参数或函数返回的访问级别，使其至少与数据类型的访问级别具有相同的限制。  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
