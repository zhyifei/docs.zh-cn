---
title: Visual Basic 命名约定
ms.date: 07/20/2015
helpviewer_keywords:
- names [Visual Basic], Visual Basic rules
- naming conventions
- naming conventions [Visual Basic], Visual Basic
- Visual Basic code, naming conventions
- conventions [Visual Basic], Visual Basic coding
- names [Visual Basic], naming conventions
- naming conventions [Visual Basic], classes
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
ms.openlocfilehash: cb7e9f2a577e95e09fde885df1a78aea4e7fa466
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651913"
---
# <a name="visual-basic-naming-conventions"></a>Visual Basic 命名约定
在 Visual Basic 应用程序中命名某个元素时，该名称的第一个字符必须是字母字符或下划线。 但请注意，名称以下划线开头不符合[语言独立性和独立于语言的组件](../../../standard/language-independence-and-language-independent-components.md)(CLS)。  
  
 以下建议适用于命名。  
  
-   开始一个大写字母，名称中的每个单独单词如`FindLastRecord`和`RedrawMyForm`。  
  
-   开始使用谓词的函数和方法名称如`InitNameArray`或`CloseDialog`。  
  
-   开始类、 结构、 模块和属性名以名词，如`EmployeeName`或`CarAccessory`。  
  
-   开始接口名称加上前缀"I"，如跟名词或名词短语， `IComponent`，或如描述接口的行为的形容词`IPersistable`。 不要使用下划线，并请慎用缩写词，因为缩写可能会导致混淆。  
  
-   描述类型的事件跟名词开始事件处理程序名称"`EventHandler`"后缀，如下所示:"`MouseEventHandler`"。  
  
-   中的事件自变量类的名称，包括"`EventArgs`"后缀。  
  
-   如果"before"或"after"事件的概念，请以现在时或过去时，使用后缀，如在"`ControlAdd`"或"`ControlAdded`"。  
  
-   有关长或者过于频繁使用的术语，使用缩写要保留名称长度合理，例如，"HTML"，而不是"超文本标记语言"。 一般情况下，大于 32 个字符的变量名称很难在设置为较低分辨率的显示器上阅读。 此外，请确保你的缩写是在整个应用程序保持一致。 在"HTML"和"超文本标记语言"之间的项目中随机切换可能会导致混乱。  
  
-   避免使用内部范围内与外部作用域中的名称相同的名称。 如果访问此错误的变量，则会导致错误。 如果变量与具有相同名称的关键字之间发生冲突，你必须确定关键字符号它前面加上适当的类型库。 例如，如果你有调用变量`Date`，你可以使用内部函数`Date`只是在调用函数<xref:System.DateTime.Date%2A?displayProperty=nameWithType>。  
  
## <a name="see-also"></a>请参阅  
 [代码中用作元素名称的关键字](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 [Me、My、MyBase 和 MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [已声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [程序结构和代码约定](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Visual Basic 语言参考](../../../visual-basic/language-reference/index.md)
