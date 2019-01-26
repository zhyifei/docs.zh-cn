---
title: 分区数据 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
ms.openlocfilehash: afbbd479d3dadd69b81cdd6aead0a4263b92dfe9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728263"
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
 下面的代码示例使用`Skip`子句在 Visual Basic 中要跳过的字符串数组中的前四个字符串，然后返回剩余字符串数组中。  
  
 [!code-vb[CsLINQPartitioning#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_1.vb)]  
  
### <a name="skipwhile"></a>SkipWhile  
 下面的代码示例使用`Skip While`子句在 Visual Basic 中字符串的第一个字母时跳过数组中的字符串"a"。 返回数组中剩余的字符串。  
  
 [!code-vb[CsLINQPartitioning#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_2.vb)]  
  
### <a name="take"></a>Take  
 下面的代码示例使用`Take`在 Visual Basic 中的字符串数组中返回的前两个字符串中的子句。  
  
 [!code-vb[CsLINQPartitioning#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_3.vb)]  
  
### <a name="takewhile"></a>TakeWhile  
 下面的代码示例使用`Take While`来从数组中返回的字符串，但该字符串的长度为五个或更少的 Visual Basic 中的子句。  
  
 [!code-vb[CsLINQPartitioning#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_4.vb)]  
  
## <a name="see-also"></a>请参阅
- <xref:System.Linq>
- [标准查询运算符概述 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Skip 子句](../../../../visual-basic/language-reference/queries/skip-clause.md)
- [Skip While 子句](../../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Take 子句](../../../../visual-basic/language-reference/queries/take-clause.md)
- [Take While 子句](../../../../visual-basic/language-reference/queries/take-while-clause.md)
