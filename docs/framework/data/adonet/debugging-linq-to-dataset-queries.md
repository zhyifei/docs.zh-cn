---
title: "调试 LINQ to DataSet 查询"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f4c54015-8ce2-4c5c-8d18-7038144cc66d
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 08c66309d4c789acc0f2ddf6159a11c5fb963e80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-linq-to-dataset-queries"></a>调试 LINQ to DataSet 查询
[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 支持 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 代码的调试。 但是，有一些差异调试[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]代码和非-[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]托管代码。 大多数调试功能都适用于[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]语句，其中包括单步执行、 设置断点，以及查看调试器窗口中显示的结果。 而且，延迟查询执行一些在调试时应考虑的副作用[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]代码，并有一些限制使用编辑并继续。 本主题讨论调试方面的问题，该调试对于与非 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 托管代码对比的 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 来说是唯一的。  
  
## <a name="viewing-results"></a>查看结果  
 你可以查看的结果[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]通过使用数据提示、 监视窗口和快速监视对话框中的语句。 使用源窗口，可以将指针暂时停留在源窗口中的查询上，这样数据提示就会出现。 可以复制 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 变量，然后将其粘贴到“监视”窗口或“快速监视”对话框。 在 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 中，创建或声明查询时并不计算查询，而只在执行查询时才计算。 这称为*延迟执行*。 因此，查询变量直到计算时才有值。 有关详细信息，请参阅[LINQ to DataSet 中的查询](../../../../docs/framework/data/adonet/queries-in-linq-to-dataset.md)。  
  
 调试程序必须计算查询才能显示查询结果。 当您在调试程序中查看 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 查询结果时，将进行此隐式计算，应考虑到这存在一些副作用。 查询的每次计算都需要时间。 展开结果节点需要时间。 对于某些查询，重复计算可能引起明显的性能损失。 计算查询也会有副作用，这些副作用会更改数据值或程序的状态。 不是所有查询都具有副作用。 若要确定查询是否可以安全计算而没有副作用，必须了解实现查询的代码。 有关详细信息，请参阅[副作用与表达式](http://msdn.microsoft.com/library/e1f8a6ea-9e19-481d-b6bd-df120ad3bf4e)。  
  
## <a name="edit-and-continue"></a>编辑并继续  
 编辑并继续不支持更改[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]查询。 如果添加、 删除或更改[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]语句中的调试会话期间，会出现一个对话框，告诉你编辑并继续不支持该更改。 此时，可以撤消更改，或停止调试会话并对编辑的代码重新启动新会话。  
  
 此外，编辑并继续不支持更改类型或使用中的变量的值[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]语句。 同样，可以撤消更改，或停止并重新启动调试会话。  
  
 在 Visual C# 中 Visual Studio 中，你不能使用编辑并继续中包含的方法的任何代码[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]查询。  
  
 在 Visual Studio 中 Visual Basic 中，你可以使用编辑并继续对非[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]甚至中包含的方法代码[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]查询。 可以在 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 语句之前添加或移除代码，即使这些更改会影响 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 查询的行号。 Visual Basic 调试体验非[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]代码保持不变之前,[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]引入了。 但是，您无法更改、添加或移除 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 查询，除非停止调试才能应用这些更改。  
  
## <a name="see-also"></a>请参阅  
 [调试托管代码](/visualstudio/debugger/debugging-managed-code)  
 [编程指南](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
