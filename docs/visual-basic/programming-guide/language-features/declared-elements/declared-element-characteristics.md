---
title: "已声明元素的特性 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic], lifetime
- access levels, declared elements
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- elements [Visual Basic], programming
- scope [Visual Basic], declared elements
- lifetime [Visual Basic], declared elements
- declared elements [Visual Basic], access level
- data types [Visual Basic], declared elements
- declared elements [Visual Basic], visibility
ms.assetid: 1bc40fb8-b67c-4428-90a4-76b630ae2583
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 26ee27d3a1d085c6ab45ae850dbdac700aa208a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="declared-element-characteristics-visual-basic"></a>已声明元素的特性 (Visual Basic)
A*特征*的已声明元素都是会影响代码如何能与它交互该元素的一个方面。 每个声明的元素具有一个或多个与之关联的以下特征：  
  
-   *数据类型*-元素可以持有的值，并将存储这些值如何。 有关详细信息，请参阅[数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md)。  
  
-   *生存期*— 在此期间，该元素是可供使用的执行时间段。 有关详细信息，请参阅[Visual Basic 中的生存期](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)。  
  
-   *作用域*— 无需限定其名称元素可以引用的所有代码组。 有关详细信息，请参阅[如何： 控制变量的作用域](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)。  
  
-   *访问级别*-代码，使权限的元素。 有关详细信息，请参阅[如何： 控制变量的可用性](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md)。  
  
## <a name="characteristics-of-the-elements"></a>元素的特征  
 下表显示已声明的元素和适用于每个特征。  
  
|元素|数据类型|生存期|作用域<sup>1</sup>|访问级别|  
|-------------|---------------|--------------|------------------------|------------------|  
|变量|是|是|是|是|  
|常量|是|No|是|是|  
|枚举|是|No|是|是|  
|结构|No|No|是|是|  
|属性|是|是|是|是|  
|方法|No|是|是|是|  
|过程 (`Sub`或`Function`)|No|是|是|是|  
|过程参数|是|是|是|No|  
|函数返回值|是|是|是|No|  
|运算符|是|No|是|是|  
|接口|No|No|是|是|  
|类|No|No|是|是|  
|Event|No|No|是|是|  
|委托|No|No|是|是|  
  
 <sup>1</sup>作用域有时称为*可见性*。  
  
## <a name="see-also"></a>另请参阅  
 [已声明的元素](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)  
 [已声明的元素名称](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [对已声明元素的引用](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [在 Visual Basic 中的生存期](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [在 Visual Basic 中的作用域](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [在 Visual Basic 中的访问级别](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [变量声明](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
