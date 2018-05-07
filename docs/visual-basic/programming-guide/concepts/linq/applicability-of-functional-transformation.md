---
title: 功能转换 (Visual Basic) 的适用性
ms.date: 07/20/2015
ms.assetid: 3b74e134-e19b-44bc-8d06-e26c48305040
ms.openlocfilehash: bdb487ce0de986a1dba36908352a8270cfde2700
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="applicability-of-functional-transformation-visual-basic"></a>功能转换 (Visual Basic) 的适用性
纯函数转换适用于多种情况。  
  
 函数转换方法最适合查询和操作结构化数据，因此它非常适合 LINQ 技术。 但函数转换比使用 LINQ 具有更广泛的适用性。 任何侧重于将数据从一种形式转换为另一种形式的进程都可以考虑作为函数转换的候选项。  
  
 此方法适用于乍看可能不是候选项的许多问题。 在独立或与 LINQ 一起使用时，应考虑对以下方面使用函数转换：  
  
-   基于 XML 的文档。 使用任何 XML 方言的格式良好的数据均可以通过函数转换容易地操作。 有关详细信息，请参阅[功能 XML 转换 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/functional-transformation-of-xml.md)。  
  
-   其他结构化文件格式。 从 Windows.ini 文件到纯文本文档，多数文件都有适于本身进行分析和转换的结构。  
  
-   数据流协议。 将数据编码为通信协议和从通信协议解码数据通常可以由简单的函数转换来表示。  
  
-   RDBMS 和 OODBMS 数据。 关系数据库和面向对象的数据库和 XML 一样，是广泛使用的结构化数据源。  
  
-   数学、统计和科学解决方案。 这些字段适用于操作大型数据集，以帮助用户处理可视化、评估或实际解决重要问题。  
  
 中所述[重构到纯函数 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md)，使用纯函数是函数编程的示例。 除了直接好处外，使用纯函数还可对从函数转换角度考虑问题提供宝贵的经验。 这种方法也可能对程序和类设计产生重要影响。 当问题本身适于数据转换解决方案（如上所述）时更是如此。  
  
 虽然受函数转换透视影响的设计不在本教程的范围内，但在以进程为中心作为操作者和以对象为中心作为操作者之间，他们更倾向于前者，生成的解决方案倾向于以一系列大规模转换而不是单独的对象状态更改的形式实现。  
  
 再次强调，请记住 Visual Basic 支持命令性和功能的方法，因此你的应用程序的最佳设计可能需要合并使用这两个元素。  
  
## <a name="see-also"></a>请参阅  
 [介绍纯函数转换 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)  
 [XML 的功能转换 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-transformation-of-xml.md)  
 [重构到纯函数 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md)
