---
title: Visual Studio (Visual Basic 中) 中调试表达式树
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 9aead09e0e9469f13e2d6befbad444d3c7fecabd
ms.sourcegitcommit: 96543603ae29bc05cecccb8667974d058af63b4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "66196029"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Visual Studio (Visual Basic 中) 中调试表达式树
可以在调试应用程序时分析表达式树的结构和内容。 若要获取表达式树结构的快速概述，可以使用`DebugView`属性，用于表示表达式树[使用特殊语法](debugview-syntax.md)。 （请注意，`DebugView` 仅在调试模式下可用。）  

![Visual Studio 调试器中的表达式树 DebugView](media/debugging-expression-trees-in-visual-studio/debugview_vb.png)

由于 `DebugView` 是一个字符串，因此可以使用[内置文本可视化工具](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer)在多行中进行查看，方法是从 `DebugView` 标签旁边的放大镜图标中选择“文本可视化工具”。

 ![文本可视化工具应用于“DebugView”的结果](media/debugging-expression-trees-in-visual-studio/string_visualizer_vb.png)

或者，你可以安装并使用[自定义可视化工具](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)表达式树，如：

* [可读表达式](https://github.com/agileobjects/ReadableExpressions)（[MIT 许可证](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md)，可在 [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers) 中获得）将表达式树呈现为 C# 代码：

  ![可读表达式可视化工具](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* [表达式树可视化工具](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees)([MIT 许可证](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE))，并提供的表达式树、 其属性和相关的对象; 图形视图还可以呈现 Visual Basic 代码的表达式目录树：

  ![ExpressionToString 可视化工具](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer_vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>打开表达式树的可视化工具  
  
1. 单击“数据提示”、“监视”窗口、“自动”窗口或“本地”窗口中表达式树旁边显示的放大镜图标。  
  
     显示可用的可视化工具列表： 

      ![从 Visual Studio 打开可视化工具](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers_vb.png)

2. 单击要使用的可视化工具。  

## <a name="see-also"></a>请参阅

- [表达式树 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [在 Visual Studio 中进行调试](/visualstudio/debugger/debugging-in-visual-studio)
- [创建自定义可视化工具](/visualstudio/debugger/create-custom-visualizers-of-data)
- [`DebugView` 语法](debugview-syntax.md)
