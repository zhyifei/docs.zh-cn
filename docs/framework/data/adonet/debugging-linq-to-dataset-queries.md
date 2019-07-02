---
title: 调试 LINQ to DataSet 查询
ms.date: 03/30/2017
ms.assetid: f4c54015-8ce2-4c5c-8d18-7038144cc66d
ms.openlocfilehash: 38eda9f352c4a8d8590e5e57b48c694eadd0397b
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "67503984"
---
# <a name="debugging-linq-to-dataset-queries"></a>调试 LINQ to DataSet 查询

Visual Studio 支持调试 LINQ 到数据集代码。 但是，有之间对数据集代码和非 LINQ to DataSet 托管代码调试 LINQ 的一些差异。 大多数调试功能都使用 LINQ 对数据集的语句，其中包括单步执行、 设置断点，以及查看调试器窗口中显示的结果。 但是，延迟的执行查询中有一些调试 LINQ 到数据集的代码时应考虑的副作用，并且有一些限制使用编辑并继续。 本主题讨论调试方面的问题，是唯一的 LINQ to DataSet 与非 LINQ to DataSet 托管代码。  
  
## <a name="viewing-results"></a>查看结果  
 通过使用数据提示、 监视窗口和快速监视对话框中，可以查看 LINQ to DataSet 语句的结果。 使用源窗口，可以将指针暂时停留在源窗口中的查询上，这样数据提示就会出现。 可以将 LINQ 复制到数据集变量并将其粘贴到监视窗口或快速监视对话框。 在 LINQ to DataSet，当创建或声明，但只在执行查询时，则不计算查询。 这称为*延迟执行*。 因此，查询变量直到计算时才有值。 有关详细信息，请参阅[LINQ to DataSet 中的查询](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md)。  
  
 调试程序必须计算查询才能显示查询结果。 此隐式计算发生在调试器中查看 LINQ to DataSet 查询结果，如果它具有一些应考虑的效果。 查询的每次计算都需要时间。 展开结果节点需要时间。 对于某些查询，重复计算可能引起明显的性能损失。 计算查询也会有副作用，这些副作用会更改数据值或程序的状态。 不是所有查询都具有副作用。 若要确定查询是否可以安全计算不会产生副作用，必须了解实现查询的代码。 有关详细信息，请参阅[副作用和表达式](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/a7a250bs(v=vs.120))。  
  
## <a name="edit-and-continue"></a>编辑并继续  
 编辑并继续不支持对 LINQ to DataSet 查询的更改。 如果添加、 删除，或更改 LINQ 为调试会话期间的数据集语句，则会出现对话框，告诉你编辑并继续不支持该更改。 此时，可以撤消更改，或停止调试会话并对编辑的代码重新启动新会话。  
  
 此外，编辑并继续不支持更改类型或 LINQ to DataSet 语句中使用的变量的值。 同样，可以撤消更改，或停止并重新启动调试会话。  
  
 视觉对象中C#在 Visual Studio 中，您不能使用编辑并继续包含 LINQ to DataSet 查询的方法中的任何代码上。  
  
 在 Visual Studio 中 Visual Basic 中，您可以对非 LINQ to DataSet 代码，即使在包含 LINQ to DataSet 查询的方法上使用编辑并继续。 您可以添加或删除之前的 LINQ to DataSet 语句的代码，即使这些更改会影响 LINQ to DataSet 查询的行号。 LINQ to DataSet 引入之前 Visual Basic 调试体验非 LINQ to DataSet 代码保持不变。 不能更改、 添加或删除 LINQ to DataSet 查询，但是，除非停止调试才能应用所做的更改。  
  
## <a name="see-also"></a>请参阅

- [调试托管代码](/visualstudio/debugger/debugging-managed-code)
- [编程指南](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
