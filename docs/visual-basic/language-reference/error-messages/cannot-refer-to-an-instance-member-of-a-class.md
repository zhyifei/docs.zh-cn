---
title: "没有类的显式实例，就无法从共享方法或共享成员初始值设定项中引用该类的实例成员"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30369
- bc30369
helpviewer_keywords:
- Shared
- BC30369
ms.assetid: 39d9466b-c1f3-4406-91a5-3d6c52d23a3d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6a15d36c0b3a4d6b1657d583de0dc61621da960d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a>没有类的显式实例，就无法从共享方法或共享成员初始值设定项中引用该类的实例成员
您试图从共享的过程中的类的非共享成员，请参阅。 下面的示例演示这种情况。  
  
```  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 在前面的示例中，赋值语句`x = 10`生成此错误消息。 这是因为共享的过程尝试访问实例变量。  
  
 变量`x`是一个实例成员，因为它未声明为[共享](../../../visual-basic/language-reference/modifiers/shared.md)。 每个类实例`sample`包含其自己单独的变量`x`。 一个实例时设置或更改的值`x`，它不会影响的值`x`在任何其他实例中。  
  
 但是，该过程`setX`是`Shared`在类的所有实例间`sample`。 这意味着它所关联的任何一个类的实例，但独立于单个实例而不是进行操作。 因为它与一个特定实例，没有连接`setX`不能访问实例变量。 它必须仅在运行`Shared`变量。 当`setX`设置或更改共享的变量，新值可供类的所有实例的值。  
  
 **错误 ID:** BC30369  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  决定要在类的所有实例间共享或保留单独为每个实例的成员。  
  
2.  如果你想要在所有实例间共享的成员的单个副本，添加`Shared`向该成员声明的关键字。 保留`Shared`过程声明中的关键字。  
  
3.  如果你想要具有其自己的成员的单独副本每个实例，未指定`Shared`成员声明。 删除`Shared`从过程声明的关键字。  
  
## <a name="see-also"></a>另请参阅  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
