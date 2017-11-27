---
title: "分区数据 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0ea305a67765e1b11ceebbf65c48a685024a41f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="partitioning-data-visual-basic"></a>分区数据 (Visual Basic)
LINQ 中的分区是指将输入序列划分为两个部分的操作，无需重新排列元素，然后返回其中一个部分。  
  
 下图显示对字符序列进行三种不同的分区操作的结果。 第一个操作返回序列中的前三个元素。 第二个操作跳过前三个元素，返回剩余元素。 第三个操作跳过序列中的前两个元素，返回接下来的三个元素。  
  
 ![LINQ 分区操作](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")  
  
 下面一节列出了对序列进行分区的标准查询运算符方法。  
  
## <a name="operators"></a>运算符  
  
|运算符名称|描述|Visual Basic 查询表达式语法|详细信息|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|Skip|跳过序列中指定位置之前的元素。|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|SkipWhile|基于谓词函数跳过元素，直到元素不符合条件。|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|Take|获取序列中指定位置之前的元素。|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|TakeWhile|基于谓词函数获取元素，直到元素不符合条件。|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>查询表达式语法示例  
  
### <a name="skip"></a>Skip  
 下面的代码示例使用`Skip`中的子句[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]跳过的字符串数组中的前四个字符串，然后返回剩余的字符串数组中。  
  
 [!code-vb[CsLINQPartitioning#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_1.vb)]  
  
### <a name="skipwhile"></a>SkipWhile  
 下面的代码示例使用`Skip While`中的子句[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]跳过时第一个字母，对字符串数组中的字符串是"a"。 返回数组中剩余的字符串。  
  
 [!code-vb[CsLINQPartitioning#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_2.vb)]  
  
### <a name="take"></a>Take  
 下面的代码示例使用`Take`中的子句[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]返回的字符串数组中的前两个字符串。  
  
 [!code-vb[CsLINQPartitioning#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_3.vb)]  
  
### <a name="takewhile"></a>TakeWhile  
 下面的代码示例使用`Take While`中的子句[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]来从数组中返回的字符串，字符串的长度为五个或更少。  
  
 [!code-vb[CsLINQPartitioning#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_4.vb)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Linq>  
 [标准查询运算符概述 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [Skip 子句](../../../../visual-basic/language-reference/queries/skip-clause.md)  
 [Skip While 子句](../../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Take 子句](../../../../visual-basic/language-reference/queries/take-clause.md)  
 [Take While 子句](../../../../visual-basic/language-reference/queries/take-while-clause.md)
