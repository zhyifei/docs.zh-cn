---
title: '&#39;&lt;关键字&gt;&#39;只在实例方法中有效'
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: a464a059aa2d13e3472b9770960384b6be398092
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595937"
---
# <a name="39ltkeywordgt39-is-valid-only-within-an-instance-method"></a>&#39;&lt;关键字&gt;&#39;只在实例方法中有效
`Me`， `MyClass`，和`MyBase`关键字是指特定类实例。 不能使用它们在共享内`Function`或`Sub`过程。  
  
 **错误 ID:** BC30043  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   从过程中删除关键字或删除`Shared`过程声明中的关键字。  
  
## <a name="see-also"></a>请参阅
- [对象变量赋值](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Me、My、MyBase 和 MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [继承的基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
