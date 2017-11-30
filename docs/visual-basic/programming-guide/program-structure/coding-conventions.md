---
title: "Visual Basic 编码约定"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
caps.latest.revision: "48"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: afea862fb8783da3e69fd9828e0ded67fb81b00e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="visual-basic-coding-conventions"></a>Visual Basic 编码约定
Microsoft 开发示例和文档，请遵循本主题中的准则。 如果您按照相同的编码约定，你可能会获得以下好处：  
  
-   你的代码将具有一致的外观，以确保读取器可以更好地专注于内容而非布局。  
  
-   读者了解你的代码更快速因为它们可能会使基于之前的经验的假设。  
  
-   你可以复制、 更改，并更轻松地维护代码。  
  
-   可帮助确保你的代码适用于 Visual Basic 演示"最佳做法"。  
  
## <a name="naming-conventions"></a>命名约定  
  
-   有关命名准则的信息，请参阅[命名准则](../../../standard/design-guidelines/naming-guidelines.md)主题。  
  
-   不使用"我的"我的"作为变量名称的一部分。 本练习中创建与混淆`My`对象。  
  
-   无需更改的自动生成的代码以使它们适合准则中的对象的名称。  
  
## <a name="layout-conventions"></a>布局约定  
  
-   插入为空格，选项卡，然后使用智能缩进具有四个空间缩进量。  
  
-   使用**错落有致 （重新格式化） 的代码**重新格式化你在代码编辑器中的代码。 有关详细信息，请参阅[选项，文本编辑器，基本 (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic)。  
  
-   使用每行只有一条语句。 不要使用 Visual Basic 行分隔符字符 （:）。  
  
-   避免使用该语言允许它支持隐式行继续标志显式行延续字符"_"。  
  
-   使用每行只有一个声明。  
  
-   如果**错落有致 （重新格式化） 的代码**不格式连续行自动、 手动缩进一个制表位的延续行。 但是，始终向左对齐列表中的项。  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   添加方法和属性定义之间的至少一个空白行。  
  
## <a name="commenting-conventions"></a>注释约定  
  
-   将注释放在单独的行而不是在某个代码行的末尾。  
  
-   开始注释文本以大写字母，并以句点结束注释文本。  
  
-   插入注释分隔符 （'） 和注释文本之间的一个空格。  
  
     [!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]  
  
-   不环绕与格式化的星号块的注释。  
  
## <a name="program-structure"></a>程序结构  
  
-   当你使用`Main`方法，默认构造用于新控制台应用程序，并使用`My`命令行自变量。  
  
     [!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]  
  
## <a name="language-guidelines"></a>语言准则  
  
### <a name="string-data-type"></a>String 数据类型  
  
-   若要连接字符串，使用与号 (&)。  
  
     [!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]  
  
-   若要将追加在循环中的字符串，请使用<xref:System.Text.StringBuilder>对象。  
  
     [!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a>事件处理程序中的宽松的委托  
 不显式计的自变量 （对象和 EventArgs） 到事件处理程序。 如果你未使用事件自变量传递给事件 （例如，为对象，e 作为 EventArgs 的发送方），使用宽松的委托，并省略在代码中的事件自变量：  
  
 [!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]  
  
### <a name="unsigned-data-type"></a>无符号数据类型  
  
-   使用`Integer`而不是无符号类型，除非它们是所必需。  
  
### <a name="arrays"></a>数组  
  
-   初始化数组在声明行上的时，请使用短的语法。 例如，使用以下语法。  
  
     [!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]  
  
     不要使用以下语法。  
  
     [!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]  
  
-   把数组指示符的类型，而不在该变量。 例如，使用以下语法：  
  
     [!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]  
  
     不要使用以下语法：  
  
     [!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]  
  
-   在声明并初始化数组的基本数据类型时，请使用 {} 语法。 例如，使用以下语法：  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     不要使用以下语法：  
  
     [!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]  
  
### <a name="use-the-with-keyword"></a>使用 With 关键字  
 当你进行一系列调用对一个对象时，请考虑使用`With`关键字：  
  
 [!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a>可以使用 Try...Catch 和 Using 语句时使用异常处理  
 不要使用`On Error Goto`。  
  
### <a name="use-the-isnot-keyword"></a>使用 IsNot 关键字  
 使用`IsNot`关键字而不是`Not...Is Nothing`。  
  
### <a name="new-keyword"></a>New 关键字  
  
-   使用短实例化。 例如，使用以下语法：  
  
     [!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]  
  
     前面的行是等效于此：  
  
     [!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]  
  
-   新对象而不是无参数构造函数中使用对象初始值设定项：  
  
     [!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]  
  
### <a name="event-handling"></a>事件处理  
  
-   使用`Handles`而非`AddHandler`:  
  
     [!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]  
  
-   使用`AddressOf`，和执行不显式实例化委托：  
  
     [!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]  
  
-   在定义事件时，使用短的语法，并让编译器定义的委托：  
  
     [!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]  
  
-   不验证事件是否是`Nothing`(null)，然后才能调用`RaiseEvent`方法。 `RaiseEvent`检查`Nothing`它引发事件之前。  
  
### <a name="using-shared-members"></a>使用共享的成员  
 调用`Shared`使用的类名称，不是从一个实例变量的成员。  
  
### <a name="use-xml-literals"></a>使用 XML 文本  
 XML 文本简化在使用 XML （例如，负载、 查询和转换） 时遇到的最常见任务。 当用 XML 开发时，请遵循以下准则：  
  
-   使用 XML 文本来创建 XML 文档和片段，而不是直接调用 XML Api。  
  
-   导入在要充分利用 XML 文本的性能优化的文件或项目级别的 XML 命名空间。  
  
-   XML 轴属性用于访问元素和 XML 文档中的属性。  
  
-   使用嵌入式的表达式包含值，从现有值，而不使用 API 调用，如创建 XML`Add`方法：  
  
     [!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]  
  
### <a name="linq-queries"></a>LINQ 查询  
  
-   使用有意义的名称对查询变量：  
  
     [!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]  
  
-   提供的查询，以确保匿名类型的属性名称都正确大写使用 Pascal 中的元素的名称的大小写：  
  
     [!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]  
  
-   如果结果中的属性名称模棱两可，请对属性重命名。 例如，如果你的查询返回客户名称和一个订单 ID，将其重命名而不是将它们保留为`Name`和`ID`结果中：  
  
     [!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]  
  
-   查询变量和范围变量的声明中使用类型推断功能：  
  
     [!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]  
  
-   对齐下的查询子句`From`语句：  
  
     [!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]  
  
-   使用`Where`子句之前其他查询子句，以便更高版本的查询子句作用于筛选的数据集：  
  
     [!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]  
  
-   使用`Join`子句显式定义联接操作而不是使用`Where`子句隐式定义联接操作：  
  
     [!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [安全编码准则](../../../standard/security/secure-coding-guidelines.md)
