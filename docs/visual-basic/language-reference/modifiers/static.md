---
title: 静态
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: f020756466888f51298abb423997906ddc7caff7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350762"
---
# <a name="static-visual-basic"></a>Static (Visual Basic)
指定一个或多个已声明的局部变量将继续存在，并在其声明过程终止后保留其最新值。  
  
## <a name="remarks"></a>备注  
 通常，过程停止后，过程中的局部变量将立即停止存在。 静态变量将继续存在并保留其最新值。 当你的代码下一次调用该过程时，不会重新初始化该变量，并且它仍保留你分配给它的最新值。 静态变量在定义它的类或模块的生存期内继续存在。  
  
## <a name="rules"></a>规则  
  
- **声明上下文。** 只能对本地变量使用 `Static`。 这意味着，`Static` 变量的声明上下文必须是过程中的过程或块，而不能是源文件、命名空间、类、结构或模块。  
  
     不能在结构过程中使用 `Static`。  
  
- 不能推断 `Static` 局部变量的数据类型。 有关详细信息，请参阅[局部类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。  
  
- **组合修饰符。** 不能在同一声明中同时指定 `Static` 与 `ReadOnly`、`Shadows`或 `Shared`。  
  
## <a name="behavior"></a>行为  
 如果在 `Shared` 过程中声明静态变量，则整个应用程序只有一个静态变量副本可供使用。 使用类名称调用 `Shared` 过程，而不是指向类的实例的变量。  
  
 如果在不 `Shared`的过程中声明静态变量，则该类的每个实例只能有一个变量副本。 使用指向类的特定实例的变量调用非共享过程。  
  
## <a name="example"></a>示例  
 以下示例演示了 `Static` 的用法。  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 `Static` 变量 `totalSales` 初始化为0次。 每次输入 `updateSales`时，`totalSales` 仍然具有为其计算的最新值。  
  
 `Static` 修饰符可用于以下上下文：  
  
 [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>另请参阅

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [生存期（Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [变量声明](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [结构](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [局部类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
