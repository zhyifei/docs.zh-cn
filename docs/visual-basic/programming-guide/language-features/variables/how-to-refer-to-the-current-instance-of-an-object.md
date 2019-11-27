---
title: 如何：引用对象的当前实例
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 62b22a54904a45380052d3d81d9415517d4f8d3b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346886"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>如何：引用对象的当前实例 (Visual Basic)
对象的*当前实例*是当前在其中执行代码的实例。  
  
 使用 `Me` 关键字来引用当前的实例。  
  
### <a name="to-refer-to-the-current-instance"></a>引用当前实例  
  
- 使用 `Me` 关键字，通常使用对象变量的名称。  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     尽管 `Me` 的行为类似于对象变量，但不能对其进行声明或向其分配任何内容。 `Me` 始终引用当前实例。  
  
## <a name="see-also"></a>另请参阅

- [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [对象变量赋值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Me、My、MyBase 和 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
