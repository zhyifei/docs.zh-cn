---
title: 在 Visual Studio 中调试表达式树
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: ff56a10b6c25f3165066edb727829cc460f3e96c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344728"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Debugging Expression Trees in Visual Studio (Visual Basic)
可以在调试应用程序时分析表达式树的结构和内容。 要快速了解表达式树结构，可以使用 `DebugView` 属性，该属性[使用特殊语法](debugview-syntax.md)表示表达式树。 （请注意，`DebugView` 仅在调试模式下可用。）  

![Screenshot of the DebugView of expression tree.](media/debugging-expression-trees-in-visual-studio/debugview-visual-basic.png)

由于 `DebugView` 是一个字符串，因此可以使用[内置文本可视化工具](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer)在多行中进行查看，方法是从 `DebugView` 标签旁边的放大镜图标中选择“文本可视化工具”。

 ![Screenshot of Text Visualizer applied to results of DebugView.](media/debugging-expression-trees-in-visual-studio/string-visualizer-vb.png)

或者，可以为表达式树安装和使用[自定义可视化工具](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)，例如：

- [可读表达式](https://github.com/agileobjects/ReadableExpressions)（[MIT 许可证](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md)，可在 [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers) 中获得）将表达式树呈现为 C# 代码：

  ![可读表达式可视化工具的屏幕截图。](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- [Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects; and can render the expression tree using Visual Basic code:

  ![Screenshot of the ExpressionToString visualizer.](media/debugging-expression-trees-in-visual-studio/expression-to-string-visualizer-vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>打开表达式树的可视化工具  
  
1. 单击“数据提示”、“监视”窗口、“自动”窗口或“本地”窗口中表达式树旁边显示的放大镜图标。  
  
    显示可用的可视化工具列表： 

    ![Screenshot of the user opening visualizers from Visual Studio.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers-vb.png)

2. 单击要使用的可视化工具。  

## <a name="see-also"></a>请参阅

- [表达式树 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [在 Visual Studio 中进行调试](/visualstudio/debugger/debugger-feature-tour)
- [创建自定义可视化工具](/visualstudio/debugger/create-custom-visualizers-of-data)
- [`DebugView` 语法](debugview-syntax.md)
