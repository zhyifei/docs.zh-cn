---
title: 通过值传递自变量和通过引用传递自变量之间的差异 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- procedures [Visual Basic], passing arguments
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8f733b4fd50612292c0c4ac7195304d99ae2dbea
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a>通过值传递自变量和通过引用传递自变量之间的差异 (Visual Basic)
当将一个或多个自变量传递给过程时，每个自变量与调用的代码中的基础编程元素相对应。 你可以传递此基础元素的值，或者对它的引用。 这称为*传递机制*。  
  
## <a name="passing-by-value"></a>按值传递  
 传递了参数*按值*通过指定[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)过程定义中的相应参数的关键字。 当你使用此传递机制时，Visual Basic 会将基础的编程元素的值复制到过程中的本地变量。 过程代码中调用代码没有任何对基础元素的访问。  
  
## <a name="passing-by-reference"></a>通过引用传递  
 传递了参数*通过引用*通过指定[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)过程定义中的相应参数的关键字。 当你使用此传递机制时，Visual Basic 使过程基础的编程元素的直接引用中调用代码。  
  
## <a name="passing-mechanism-and-element-type"></a>传递机制和元素类型  
 所选的传递机制不相同的基础的元素类型的分类。 按值或按引用传递引用 Visual Basic 提供到该过程代码。 值类型或引用类型引用的编程元素在内存中的存储方式。  
  
 但是的传递机制和元素类型是相互关联。 一个引用类型的值是指向内存中其他位置的数据的指针。 这意味着当通过值传递引用类型时，过程代码具有一个指向基础元素的数据，即使它不能访问基础元素本身也是如此。 例如，如果该元素是一个数组变量，该过程代码没有访问变量本身，但它可以访问数组成员。  
  
## <a name="ability-to-modify"></a>若要修改的功能  
 时作为参数传递的不可修改的元素，该过程可以永远不能修改它在调用代码中，不论它的传入`ByVal`或`ByRef`。  
  
 一个可修改的元素，为下表汇总了元素类型和的传递机制之间的交互。  
  
|元素类型|传递 `ByVal`|传递 `ByRef`|  
|------------------|--------------------|--------------------|  
|值类型 （包含只有一个值）|过程将无法更改变量或任何其成员。|该过程可以更改变量和其成员。|  
|引用类型 （包含的类或结构的实例的指针）|该过程不能更改变量，但可以更改它所指向的实例的成员。|该过程可以更改变量和它所指向的实例的成员。|  
  
## <a name="see-also"></a>请参阅  
 [过程](./index.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [如何：将自变量传递给过程](./how-to-pass-arguments-to-a-procedure.md)  
 [按值和按引用传递自变量](./passing-arguments-by-value-and-by-reference.md)  
 [可修改和不可修改自变量之间的差异](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [如何：更改过程自变量的值](./how-to-change-the-value-of-a-procedure-argument.md)  
 [如何：防止过程自变量的值被更改](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [如何：强制通过值传递自变量](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [按位置和按名称传递自变量](./passing-arguments-by-position-and-by-name.md)  
 [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
