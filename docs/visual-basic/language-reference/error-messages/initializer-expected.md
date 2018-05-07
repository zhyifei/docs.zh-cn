---
title: 应为初始值设定项
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: 9d786fd1e929129c420b7bec62efd0bd445d85eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="initializer-expected"></a>应为初始值设定项
您试图使用在其中初始化列表为空，下面的示例中所示的对象初始值设定项声明类的实例。  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 下面的示例中所示，必须在初始值设定项列表中，初始化至少一个字段或属性。  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 **错误 ID:** BC30996  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  初始化至少一个字段或属性初始值设定项，或者不使用对象初始值设定项。  
  
## <a name="see-also"></a>请参阅  
 [对象初始值设定项：命名类型和匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [如何：使用对象初始值设定项声明对象](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
