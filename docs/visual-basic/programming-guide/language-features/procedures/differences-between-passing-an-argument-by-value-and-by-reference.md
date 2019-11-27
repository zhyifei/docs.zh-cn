---
title: 通过值传递自变量和通过引用传递自变量之间的差异
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- procedures [Visual Basic], passing arguments
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
ms.openlocfilehash: 84ec3bac2532b2cef72ddda347251bc987801c3b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74341231"
---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a>通过值传递参数和通过引用传递参数之间的差异 (Visual Basic)
将一个或多个自变量传递给过程时，每个参数都对应于调用代码中的基础编程元素。 可以传递此基础元素的值或对其的引用。 这称为*传递机制*。  
  
## <a name="passing-by-value"></a>按值传递  
 通过*值*传递自变量，方法是在过程定义中为相应的参数指定[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)关键字。 使用此传递机制时，Visual Basic 会将基础编程元素的值复制到过程中的局部变量中。 过程代码对调用代码中的基础元素没有任何访问权限。  
  
## <a name="passing-by-reference"></a>按引用传递  
 通过在过程定义中为相应的参数指定[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)关键字，可以通过*引用*传递自变量。 使用此传递机制时，Visual Basic 为过程提供对调用代码中的基础编程元素的直接引用。  
  
## <a name="passing-mechanism-and-element-type"></a>传递机制和元素类型  
 选择的传递机制与基础元素类型的分类不同。 按值或按引用传递是指 Visual Basic 向过程代码提供的内容。 值类型或引用类型是指编程元素在内存中的存储方式。  
  
 不过，传递机制和元素类型是相互关联的。 引用类型的值是指向内存中其他位置的数据的指针。 这意味着，当你按值传递引用类型时，过程代码将具有指向基础元素数据的指针，即使它无法访问基础元素本身。 例如，如果元素是一个数组变量，则过程代码不能访问变量本身，但它可以访问数组成员。  
  
## <a name="ability-to-modify"></a>修改能力  
 将不可更改元素作为参数传递时，此过程将永远不能在调用代码中修改它，无论是传递 `ByVal` 还是 `ByRef`。  
  
 对于可修改元素，下表总结了元素类型和传递机制之间的交互。  
  
|元素类型|传递的 `ByVal`|传递的 `ByRef`|  
|------------------|--------------------|--------------------|  
|值类型（只包含值）|此过程无法更改变量或其任何成员。|该过程可以更改变量及其成员。|  
|引用类型（包含指向类或结构实例的指针）|此过程无法更改变量，但可以更改它所指向的实例的成员。|该过程可以更改变量以及它所指向的实例的成员。|  
  
## <a name="see-also"></a>另请参阅

- [过程](./index.md)
- [过程参数和自变量](./procedure-parameters-and-arguments.md)
- [如何：将自变量传递给过程](./how-to-pass-arguments-to-a-procedure.md)
- [按值和按引用传递自变量](./passing-arguments-by-value-and-by-reference.md)
- [可修改和不可修改自变量之间的差异](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [如何：更改过程自变量的值](./how-to-change-the-value-of-a-procedure-argument.md)
- [如何：防止过程自变量的值被更改](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [如何：强制通过值传递自变量](./how-to-force-an-argument-to-be-passed-by-value.md)
- [按位置和按名称传递自变量](./passing-arguments-by-position-and-by-name.md)
- [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
