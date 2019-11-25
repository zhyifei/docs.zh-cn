---
title: 功能转换的适用性
ms.date: 07/20/2015
ms.assetid: 3b74e134-e19b-44bc-8d06-e26c48305040
ms.openlocfilehash: 292201f4964142126d428939807cb20f354a7d2f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345771"
---
# <a name="applicability-of-functional-transformation-visual-basic"></a>Applicability of Functional Transformation (Visual Basic)
纯函数转换适用于多种情况。  
  
 函数转换方法最适合查询和操作结构化数据，因此它非常适合 LINQ 技术。 但函数转换比使用 LINQ 具有更广泛的适用性。 任何侧重于将数据从一种形式转换为另一种形式的进程都可以考虑作为函数转换的候选项。  
  
 此方法适用于乍看可能不是候选项的许多问题。 在独立或与 LINQ 一起使用时，应考虑对以下方面使用函数转换：  
  
- 基于 XML 的文档。 使用任何 XML 方言的格式良好的数据均可以通过函数转换容易地操作。 For more information, see [Functional Transformation of XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-transformation-of-xml.md).  
  
- 其他结构化文件格式。 从 Windows.ini 文件到纯文本文档，多数文件都有适于本身进行分析和转换的结构。  
  
- 数据流协议。 将数据编码为通信协议和从通信协议解码数据通常可以由简单的函数转换来表示。  
  
- RDBMS 和 OODBMS 数据。 关系数据库和面向对象的数据库和 XML 一样，是广泛使用的结构化数据源。  
  
- 数学、统计和科学解决方案。 这些字段适用于操作大型数据集，以帮助用户处理可视化、评估或实际解决重要问题。  
  
 As described in [Refactoring Into Pure Functions (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md), using pure functions is an example of functional programming. 除了直接好处外，使用纯函数还可对从函数转换角度考虑问题提供宝贵的经验。 这种方法也可能对程序和类设计产生重要影响。 当问题本身适于数据转换解决方案（如上所述）时更是如此。  
  
 虽然受函数转换透视影响的设计不在本教程的范围内，但在以进程为中心作为操作者和以对象为中心作为操作者之间，他们更倾向于前者，生成的解决方案倾向于以一系列大规模转换而不是单独的对象状态更改的形式实现。  
  
 Again, remember that Visual Basic supports both imperative and functional approaches, so the best design for your application might incorporate elements of both.  
  
## <a name="see-also"></a>请参阅

- [Introduction to Pure Functional Transformations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)
- [XML 的功能转换 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-transformation-of-xml.md)
- [Refactoring Into Pure Functions (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md)
