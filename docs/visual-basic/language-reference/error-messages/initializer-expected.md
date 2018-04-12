---
title: 应为初始值设定项
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 46ff91ec240212571f7ec9f26e82d9d128263545
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
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
  
## <a name="see-also"></a>另请参阅  
 [对象初始值设定项：命名类型和匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [如何：使用对象初始值设定项声明对象](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
