---
title: Array Dimensions in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: cf295288dd034d744dceb71b5c58278be5cc2a2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651751"
---
# <a name="array-dimensions-in-visual-basic"></a>Array Dimensions in Visual Basic
A*维度*是在其中您可以改变数组的元素的规范方向。 保存总销量，每月的每一天的数组具有一个维度 （每月天数）。 保存总销量由部门的每一天的月份的数组具有两个维度 （部门数和每月天数）。 调用的维数的数组具有其*级别*。  
  
> [!NOTE]
>  你可以使用<xref:System.Array.Rank%2A>属性来确定多少维数的数组具有。  
  
## <a name="working-with-dimensions"></a>使用的维度  
 通过提供指定数组的数组元素*索引*或*下标*其维度的每个。 元素将从 0 到最高的索引，该维度连续沿每个维度。  
  
 下图显示具有不同的秩的数组的概念结构。 每个元素的插图内显示访问它的索引值。 例如，可以通过指定索引访问二维数组的第二行的第一个元素`(1, 0)`。  
  
 ![一个示意图&#45;维数组](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.gif "ArrayExDimOne")  
一维数组  
  
 ![两个图形关系图&#45;维数组](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")  
二维数组  
  
 ![三个示意图&#45;维数组](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.gif "ArrayExDimThree")  
三维数组  
  
### <a name="one-dimension"></a>一个维度  
 多个数组具有只有一个维度，如每个期限的人员数。 要指定某个元素的唯一要求是，该元素包含计数的期限。 因此，这样的数组使用只有一个索引。 下面的示例声明一个变量以保存*一维数组*的年龄 0 到 120 计数的年龄。  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### <a name="two-dimensions"></a>两个维度  
 某些数组具有两个维度，如在上一区域每个生成的每一层上的机构数量。 元素的规范要求的建筑号和基底，和每个元素包含构造和层的该组合的计数。 因此，这样的数组使用这两个索引。 下面的示例声明一个变量以保存*二维数组*office 计数，建筑物从 0 到 40 和楼层从 0 到 5。  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 二维数组也被称为*矩形数组*。  
  
### <a name="three-dimensions"></a>三个维度  
 几个数组具有三个维度，如在三维空间中的值。 这样的数组使用三个索引，在这种情况下表示 x、 y 和 z 坐标的物理空间。 下面的示例声明一个变量以保存*三维数组*的气温三维卷中的各个点。  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### <a name="more-than-three-dimensions"></a>三个以上的维度  
 尽管数组可具有多达 32 维度，但很少使用多个三种。  
  
> [!NOTE]
>  将维度添加到一个数组，数组所需的总存储增加有相当大，因此使用多维数组时要小心。  
  
## <a name="using-different-dimensions"></a>使用不同维度  
 假设你想要跟踪的存在月中每天的销售额。 一个用于每个月的日期，如下面的示例演示，你可能会声明 31 元素的一维数组。  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 现在假设你想要跟踪的相同信息不仅每天每月的而且还要为每个月的年份。 如以下示例所示，可能会声明一个二维数组具有 12 行 （表示月为单位） 和 （对于天），31 列。  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 现在假设你决定让你的数组将保存多个为一年的信息。 如果你想要跟踪的 5 年的销售额，你无法声明具有 5 层、 12 行和 31 列的三维数组，如以下示例所示。  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 请注意，由于每个索引会发生从 0 到其最大值，每个维度的变化`salesAmounts`该维度被声明为一个小于所需的长度。 另请注意，数组的大小会增加随每个新的维度。 前面的示例中的三个大小分别为 31、 372 和 1860 个元素。  
  
> [!NOTE]
>  你可以创建一个数组，而不使用`Dim`语句或`New`子句。 例如，你可以调用<xref:System.Array.CreateInstance%2A>方法或另一个组件可以通过你的代码以这种方式创建的数组。 这样的数组可以下限为非 0。 始终可以通过使用测试维度的下限<xref:System.Array.GetLowerBound%2A>方法或`LBound`函数。  
  
## <a name="see-also"></a>请参阅  
 [数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [数组疑难解答](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
