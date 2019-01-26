---
title: Visual Basic 编码约定
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: f2b1676ae959c5426af3021bbd340980115c5da6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724877"
---
# <a name="visual-basic-coding-conventions"></a>Visual Basic 编码约定
Microsoft 开发的示例和文档，请按照本主题中的准则。 如果您遵循相同的编码约定，您可能会获得以下优势：  
  
-   你的代码将具有一致的外观，以便读者可以更好地专注于内容而非布局。  
  
-   读取器了解您的代码更快速因为它们可以使基于以前的经验的假设。  
  
-   可以复制、 更改，并更轻松地维护代码。  
  
-   可帮助确保您的代码演示 Visual Basic 的"最佳实践"。  
  
## <a name="naming-conventions"></a>命名约定  
  
-   有关命名指南的信息，请参阅[命名准则](../../../standard/design-guidelines/naming-guidelines.md)主题。  
  
-   不使用"My"我的"作为变量名称的一部分。 此做法会与混淆`My`对象。  
  
-   无需更改自动生成的代码，使它们符合指南中的对象名称。  
  
## <a name="layout-conventions"></a>布局约定  
  
-   插入制表符作为空格，并使用智能缩进四空格缩进。  
  
-   使用**整齐排列代码 （重新格式化） 的**格式重新设置你的代码在代码编辑器中。 有关详细信息，请参阅[选项，文本编辑器，基本 (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic)。  
  
-   使用每行只有一条语句。 不要使用 Visual Basic 行分隔符 （:）。  
  
-   避免使用隐式行继续符为支持显式行继续符"_"，无论该语言允许它在何处。  
  
-   使用每行只有一个声明。  
  
-   如果**整齐排列代码 （重新格式化） 的**不格式化继续行自动、 手动缩进一个制表位的延续任务行。 但是，始终左对齐列表中的项。  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   添加方法和属性定义之间的至少一个空白行。  
  
## <a name="commenting-conventions"></a>注释约定  
  
-   将注释放在单独的行而不是代码行末尾处。  
  
-   开始注释文本以大写字母，并使用句点结束注释文本。  
  
-   插入注释分隔符 （'） 和注释文本之间的一个空格。  
  
     [!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]  
  
-   环绕在注释格式化的星号块。  
  
## <a name="program-structure"></a>程序结构  
  
-   当你使用`Main`方法，使用默认构造进行新控制台应用程序，并使用`My`对命令行参数。  
  
     [!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]  
  
## <a name="language-guidelines"></a>语言准则  
  
### <a name="string-data-type"></a>String 数据类型  
  
-   若要连接字符串，请使用与号 (&)。  
  
     [!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]  
  
-   若要追加在循环中的字符串，请使用<xref:System.Text.StringBuilder>对象。  
  
     [!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a>事件处理程序中的宽松的委托  
 不显式符合条件的参数 （对象和 EventArgs） 到事件处理程序。 如果不使用传递给事件 （例如，发送方为对象，e 为 EventArgs） 的事件参数，使用宽松的委托，并将在代码中的事件参数：  
  
 [!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]  
  
### <a name="unsigned-data-type"></a>无符号数据类型  
  
-   使用`Integer`而不是无符号类型，将在必要时除外。  
  
### <a name="arrays"></a>数组  
  
-   在初始化数组声明行上的时，请使用短语法。 例如，使用以下语法。  
  
     [!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]  
  
     不要使用以下语法。  
  
     [!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]  
  
-   将数组指定符置于类型上而不是变量上。 例如，使用以下语法：  
  
     [!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]  
  
     不要使用以下语法：  
  
     [!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]  
  
-   当声明和初始化基本数据类型的数组时，请使用 {} 语法。 例如，使用以下语法：  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     不要使用以下语法：  
  
     [!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]  
  
### <a name="use-the-with-keyword"></a>使用 With 关键字  
 当你进行一系列调用到一个对象时，请考虑使用`With`关键字：  
  
 [!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a>可以使用 Try...Catch 和 Using 语句时使用异常处理  
 请勿使用 `On Error Goto`。  
  
### <a name="use-the-isnot-keyword"></a>使用 IsNot 关键字  
 使用`IsNot`关键字而不是`Not...Is Nothing`。  
  
### <a name="new-keyword"></a>新的关键字  
  
-   使用短实例化。 例如，使用以下语法：  
  
     [!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]  
  
     前面的行是等效于此：  
  
     [!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]  
  
-   使用对象初始值设定项的新对象而不是无参数构造函数：  
  
     [!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]  
  
### <a name="event-handling"></a>事件处理  
  
-   使用`Handles`而非`AddHandler`:  
  
     [!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]  
  
-   使用`AddressOf`，并执行不显式实例化委托：  
  
     [!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]  
  
-   在定义事件时，使用短语法并让编译器定义此委托：  
  
     [!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]  
  
-   不要验证事件是否是`Nothing`(null)，然后再调用`RaiseEvent`方法。 `RaiseEvent` 检查`Nothing`引发事件之前。  
  
### <a name="using-shared-members"></a>使用共享的成员  
 调用`Shared`使用类名称，不能从一个实例变量的成员。  
  
### <a name="use-xml-literals"></a>使用 XML 文本  
 XML 文本简化了在使用 XML （例如，加载、 查询和转换） 时遇到的最常见任务。 当使用 XML 进行开发时，请遵循以下准则：  
  
-   使用 XML 文本创建 XML 文档和片段，而不直接调用 XML Api。  
  
-   导入 XML 命名空间在文件或项目级别，以充分利用 XML 文本的性能优化。  
  
-   使用 XML 轴属性访问元素和 XML 文档中的属性。  
  
-   使用嵌入的表达式包括值并创建从现有值而不是使用 API 调用，如 XML`Add`方法：  
  
     [!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]  
  
### <a name="linq-queries"></a>LINQ 查询  
  
-   对查询变量使用有意义的名称：  
  
     [!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]  
  
-   为确保匿名类型的属性名称正确大写使用 Pascal 的查询中的元素提供名称大小写：  
  
     [!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]  
  
-   如果结果中的属性名称模棱两可，请对属性重命名。 例如，如果您的查询返回一个客户名称和一个订单 ID，重命名它们而不是它们保留为`Name`和`ID`结果中：  
  
     [!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]  
  
-   查询变量和范围变量的声明中使用类型推断功能：  
  
     [!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]  
  
-   对齐下的查询子句`From`语句：  
  
     [!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]  
  
-   使用`Where`子句之前其他查询子句，以便更高版本的查询子句作用于筛选的数据集：  
  
     [!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]  
  
-   使用`Join`子句显式定义的联接操作，而不是使用`Where`子句隐式定义联接操作：  
  
     [!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]  
  
## <a name="see-also"></a>请参阅
- [安全编码准则](../../../standard/security/secure-coding-guidelines.md)
