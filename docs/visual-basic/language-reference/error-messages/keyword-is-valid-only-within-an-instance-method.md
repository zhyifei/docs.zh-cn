---
title: “<keyword>”只在实例方法中有效
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: af3bc95e2db88577c7c53e4b58fb60aed8a83453
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267634"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a>\<关键字 > 只在实例方法中有效
`Me`， `MyClass`，和`MyBase`关键字是指特定类实例。 不能使用它们在共享内`Function`或`Sub`过程。  
  
 **错误 ID:** BC30043  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   从过程中删除关键字或删除`Shared`过程声明中的关键字。  
  
## <a name="see-also"></a>请参阅
- [对象变量赋值](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Me、My、MyBase 和 MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [继承的基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
