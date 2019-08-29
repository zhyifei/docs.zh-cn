---
title: 常量概述 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic]
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
ms.openlocfilehash: 0c866f3d03d26bd882d5a6596d40d1dc639da011
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934780"
---
# <a name="constants-overview-visual-basic"></a>常量概述 (Visual Basic)
常量是有意义的名称, 用来代替不会更改的数字或字符串。 顾名思义, 常数存储值在应用程序的整个执行过程中保持不变。 您可以通过使用常量极大地提高代码的可读性并使其更易于维护。 在包含重新出现的值的代码中使用它们, 或依赖于某些难以记住或没有明显含义的数字的值。  
  
## <a name="how-to-create-and-use-constants"></a>如何创建和使用常量  
 Visual Basic 包含许多预定义的常量, 主要用于打印和显示。 还可以使用`Const`语句创建自己的常量, 使用与创建变量名称相同的准则。 如果`Option Strict` 为`On`, 则必须显式声明常量类型。  
  
 常量的作用域, 它是在不限定其名称的情况下可引用它的所有代码的集合, 与在同一位置声明的变量的作用域相同。 若要创建一个存在于特定过程范围内的常量, 请在该过程中将其声明为。 若要创建可在整个应用程序中使用的常数, 请在`Public`类的声明部分使用关键字进行声明。  
  
> [!NOTE]
> 尽管常量有点类似于变量, 但您不能对其进行修改, 也不能为变量赋值。  
  
 您在代码中使用的常量可以由您所使用的控件或组件的对象模型定义, 也可以是用户定义的 (也就是说, 您自己创建的)。  
  
## <a name="compile-time-and-run-time-constants"></a>编译时和运行时常量  
 编译时常量是在编译代码时计算的, 而运行时常量只能在应用程序运行时进行计算。 每次应用程序运行时, 编译时常量都将具有相同的值, 而每次运行时常量可能会更改。 对于数组界限、case 表达式或枚举器初始值设定项等事例, 编译时常量是必需的。  
  
## <a name="in-this-section"></a>本节内容  
  
|定义|术语|  
|---|---|  
|[如何：声明常量](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|说明如何使用`Const`语句声明常量并设置其值; 通过声明常量, 可为该值指定有意义的名称。|  
|[用户定义的常量](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|介绍如何创建自己的常量, 包括有关范围的信息以及如何避免循环引用。|  
|[常量和文本数据类型](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|提供有关 Visual Basic 编译器如何在关闭时`Option Explicit`初始化常量的信息。|  
|[如何：将相关的常量值组合在一起](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|演示如何对相关的常量值进行分组。|  
  
## <a name="reference"></a>参考  
  
|定义|术语|  
|---|---|  
|[常量和枚举](../../../../visual-basic/language-reference/constants-and-enumerations.md)|列出由 Visual Basic 预定义的常量。|  
|[Const 语句](../../../../visual-basic/language-reference/statements/const-statement.md)|`Const`描述语句及其用法。|  
|[Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|`Option Strict`描述语句及其用法。|  
  
## <a name="see-also"></a>请参阅

- [枚举概述](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [如何：在 Visual Basic 中初始化数组变量](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
