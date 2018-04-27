---
title: Visual Basic 程序的结构
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- conditional compilation [Visual Basic], Visual Basic
- program structure [Visual Basic], Visual Basic
- procedures [Visual Basic], structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5def0de1e22af39eb16489a2d4d27bdbd1853f2b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="structure-of-a-visual-basic-program"></a>Visual Basic 程序的结构
Visual Basic 程序是从标准构建基块构建。 A*解决方案*由一个或多个项目组成。 A*项目*又可以包含一个或多个程序集。 每个*程序集*从一个或多个源代码文件编译。 A*源文件*提供定义和实现的类、 结构、 模块和接口，最终包含了所有代码。  
  
 Visual Basic 程序的这些构建基块的详细信息，请参阅[解决方案和项目](/visualstudio/ide/solutions-and-projects-in-visual-studio)和[程序集和全局程序集缓存](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)。  
  
## <a name="file-level-programming-elements"></a>文件级别的编程元素  
 当您启动项目或文件，并打开代码编辑器中时，你将看到一些代码已存在并按正确的顺序。 你编写任何代码应遵循以下顺序：  
  
1.  `Option` 语句  
  
2.  `Imports` 语句  
  
3.  `Namespace` 语句和命名空间级别元素  
  
 如果按不同的顺序输入语句，则会导致编译错误。  
  
 程序还可以包含条件编译语句。 你可以分散放置条件编译的上述顺序的语句之间的源文件中。  
  
### <a name="option-statements"></a>选项语句  
 `Option` 语句建立为后续的代码，以防止语法和逻辑错误的基本规则。 [Option Explicit 语句](../../../visual-basic/language-reference/statements/option-explicit-statement.md)可确保所有变量声明并拼写是否正确，这减少了调试的时间。 [Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)有助于之间不同的数据类型的变量，在处理时可能发生的逻辑错误和数据丢失降到最低。 [选项比较语句](../../../visual-basic/language-reference/statements/option-compare-statement.md)指定字符串的方式比较到对方，基于其`Binary`或`Text`值。  
  
### <a name="imports-statements"></a>Imports 语句  
 可以包括[Imports 语句 （.NET Namespace 和类型）](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)导入在项目外部定义的名称。 `Imports`语句允许你的代码来指代类和其他类型定义中的导入的命名空间，而无需限定它们。 你可以使用任意多个`Imports`作为适当的语句。 有关详细信息，请参阅[引用和 Imports 语句](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)。  
  
### <a name="namespace-statements"></a>Namespace 语句  
 命名空间可帮助组织和分类以便于分组和访问编程元素。 你使用[Namespace 语句](../../../visual-basic/language-reference/statements/namespace-statement.md)进行分类内特定命名空间的以下语句。 有关详细信息，请参阅 [Visual Basic 中的命名空间](../../../visual-basic/programming-guide/program-structure/namespaces.md)。  
  
### <a name="conditional-compilation-statements"></a>条件编译语句  
 条件编译语句可以出现在源文件的几乎任意位置。 它们会导致你的代码以包括或排除在编译时根据某些条件的部分。 你可以将它们用于调试你的应用程序，因为在调试仅限模式中运行的条件代码。 有关详细信息，请参阅[条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)。  
  
## <a name="namespace-level-programming-elements"></a>Namespace 级编程元素  
 类、 结构和模块包含源文件中的所有代码。 它们是*命名空间级别*元素，可在某个命名空间或文件级别的源的文件出现。 它们具有所有其他编程元素的声明。 接口，这样定义元素签名，但不提供实现，也出现在模块级别。 模块级别的元素的详细信息，请参阅以下资源：  
  
-   [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
-   [Module 语句](../../../visual-basic/language-reference/statements/module-statement.md)  
  
-   [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 命名空间级别的数据元素是枚举和委托。  
  
## <a name="module-level-programming-elements"></a>模块级别的编程元素  
 过程、 运算符、 属性和事件是仅有编程元素可以包含可执行代码 （在运行时执行操作的语句）。 它们是*模块级别*的程序元素。 过程级别元素的详细信息，请参阅以下资源：  
  
-   [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
-   [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 在模块级别的数据元素是变量、 常量、 枚举和委托。  
  
## <a name="procedure-level-programming-elements"></a>过程级别的编程元素  
 大多数内容的*过程级别*元素都是可执行语句，它们构成程序的运行时代码。 所有可执行代码必须在某个过程 (`Function`， `Sub`， `Operator`， `Get`， `Set`， `AddHandler`， `RemoveHandler`， `RaiseEvent`)。 有关详细信息，请参阅[语句](../../../visual-basic/programming-guide/language-features/statements.md)。  
  
 在过程级别的数据元素仅限于本地变量和常量。  
  
## <a name="the-main-procedure"></a>主要过程  
 `Main`过程是用于运行时已加载你的应用程序的第一个代码。 `Main` 用作起始点和应用程序的总体控制。 有四种变化形式`Main`:  
  
-   `Sub Main()`  
  
-   `Sub Main(ByVal cmdArgs() As String)`  
  
-   `Function Main() As Integer`  
  
-   `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 此过程的最常见类型是`Sub Main()`。 有关详细信息，请参阅[Visual Basic 中的 Main 过程](../../../visual-basic/programming-guide/program-structure/main-procedure.md)。  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 中的 main 过程](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 [Visual Basic 命名约定](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [Visual Basic 限制](../../../visual-basic/programming-guide/program-structure/limitations.md)
