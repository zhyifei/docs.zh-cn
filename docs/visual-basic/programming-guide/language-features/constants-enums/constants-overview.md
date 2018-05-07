---
title: 常量概述 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic]
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
ms.openlocfilehash: 2ec43254013df5444048b5197489c55217d5328a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="constants-overview-visual-basic"></a>常量概述 (Visual Basic)
常量是有意义的名称发生的数字或字符串不会更改。 常量存储的名称可以看出，保持不变的应用程序的执行中值。 你可以大幅提高代码的可读性和更加轻松地使用常量的维护。 在包含重新出现的值的代码中使用它们，或这取决于一些很难记住或没有明显意义的数字。  
  
## <a name="how-to-create-and-use-constants"></a>如何创建和使用常量  
 Visual Basic 包含大量的预定义的常量，主要用于打印和显示。 你还可以创建你自己常量具有与`Const`语句，用于创建变量的名称使用相同的规则。 如果`Option Strict`是`On`，您必须显式声明的常量的类型。  
  
 常量的作用域，它是所有代码都可以引用它而无须限定其名称的集，等同于在同一位置中声明的变量。 若要创建一个常数，位于某个特定过程的作用域内，将其声明该过程内。 若要创建一个常数，用于在整个应用程序都可用，将使用其声明`Public`类的声明部分中的关键字。  
  
> [!NOTE]
>  尽管常量某种程度上类似于变量，但无法对其进行修改，或将新值分配给它们，因为你可以对变量。  
  
 在代码中使用的常量可以定义由控件或你使用的组件对象模型或它们可以是用户定义 （即，那些你自己创建的）。  
  
## <a name="compile-time-and-run-time-constants"></a>编译时和运行时常量  
 在编译代码，可以仅计算运行时常量，应用程序运行时的时间计算编译时常量。 编译时常量将在每次运行应用程序，而运行时常量可能会更改每个时间时具有相同的值。 编译时常量所需的情况下，如数组边界、 case 表达式或枚举器初始值设定项。  
  
## <a name="in-this-section"></a>本节内容  
  
|定义|术语|  
|---|---|  
|[如何：声明常量](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|说明如何使用`Const`语句以声明常量，并将其值; 设置为值通过声明一个常数，分配有意义的名称。|  
|[用户定义的常量](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|描述如何创建你自己的常量，包括有关范围的信息以及如何避免循环引用。|  
|[常量和文本数据类型](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|提供有关 Visual Basic 编译器如何初始化常量的信息时`Option Explicit`处于关闭状态。|  
|[如何：将相关的常量值组合在一起](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|演示如何组相关的常量值。|  
  
## <a name="reference"></a>参考  
  
|定义|术语|  
|---|---|  
|[常量和枚举](../../../../visual-basic/language-reference/constants-and-enumerations.md)|列出由 Visual Basic 预定义的常量。|  
|[Const 语句](../../../../visual-basic/language-reference/statements/const-statement.md)|描述`Const`语句和其使用。|  
|[Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|描述`Option Strict`语句和其使用。|  
  
## <a name="see-also"></a>请参阅  
 [枚举概述](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [如何：在 Visual Basic 中初始化数组变量](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
