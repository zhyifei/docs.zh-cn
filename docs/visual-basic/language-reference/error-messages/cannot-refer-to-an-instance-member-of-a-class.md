---
title: 没有类的显式实例，就无法从共享方法或共享成员初始值设定项中引用该类的实例成员
ms.date: 07/20/2015
f1_keywords:
- vbc30369
- bc30369
helpviewer_keywords:
- Shared
- BC30369
ms.assetid: 39d9466b-c1f3-4406-91a5-3d6c52d23a3d
ms.openlocfilehash: a2a5ab99ff68e6dce783a2fd986ee6e8c15ae858
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701164"
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a>没有类的显式实例，就无法从共享方法或共享成员初始值设定项中引用该类的实例成员
您尝试从共享过程中引用类的非共享成员。 下面的示例演示了这种情况。  
  
```vb  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 在前面的示例中，赋值语句 `x = 10` 将生成此错误消息。 这是因为共享过程尝试访问实例变量。  
  
 变量 `x` 是实例成员，因为它未声明为[Shared](../../../visual-basic/language-reference/modifiers/shared.md)。 类 @no__t 的每个实例都包含其自身 `x` 的单独变量。 当一个实例设置或更改 `x` 的值时，它不会影响任何其他实例中 `x` 的值。  
  
 但是，在 `sample` 类的所有实例中，步骤 `setX` @no__t。 这意味着它不与类的任何一个实例关联，而是独立于单个实例进行操作。 由于它与特定实例没有连接，因此 `setX` 无法访问实例变量。 它只能在 `Shared` 变量上运行。 @No__t 设置或更改共享变量的值时，该新值可供类的所有实例使用。  
  
 **错误 ID：** BC30369  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 确定是要在类的所有实例之间共享成员还是为每个实例保留单个成员。  
  
2. 如果希望在所有实例之间共享成员的单个副本，请将 @no__t 关键字添加到成员声明。 在过程声明中保留 `Shared` 关键字。  
  
3. 如果希望每个实例都有自己的成员的单独副本，请不要为成员声明指定 `Shared`。 删除过程声明中的 @no__t 0 关键字。  
  
## <a name="see-also"></a>请参阅

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
