---
title: 数组疑难解答 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: 4ab6d376ad8652e460e33c4f2c3285e8c80286fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-arrays-visual-basic"></a>数组疑难解答 (Visual Basic)
此页列出与数组一起使用时可能发生的一些常见问题的方法。  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a>编译错误声明并初始化数组  
 编译错误可能会产生误解的声明、 创建和初始化数组的规则。 错误的最常见原因如下所示：  
  
-   提供[New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)子句后在数组变量声明中指定维的长度。 下面的代码行显示了无效的此类型的声明。  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   为多个顶级数组交错数组的指定维的长度。 下面的代码行显示此类型的一个无效的声明。  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   省略`New`关键字时指定的元素值。 下面的代码行显示此类型的一个无效的声明。  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   提供`New`子句时没有使用大括号 (`{}`)。 下面的代码行显示了无效的此类型的声明。  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a>访问超出界限的数组  
 初始化数组的过程将分配给每个维度的上限和下限。 每次访问数组的元素必须指定有效的索引或下标，对于每个维度。 如果任何索引其下限低于或高于其上限<xref:System.IndexOutOfRangeException>异常结果。 编译器无法检测此类错误，因此在运行时出错。  
  
### <a name="determining-bounds"></a>确定边界  
 如果另一个组件将数组传递给你的代码，例如作为过程自变量，你不知道该数组的大小或其维度的长度。 然后再尝试访问任何元素，你始终应该确定对于数组的每个维度的上限。 如果 Visual Basic 以外的其他一些方式创建了数组`New`子句，下限可能不是 0，并且它是最安全的做法是，以确定该下限。  
  
### <a name="specifying-the-dimension"></a>指定维度  
 在确定多维数组的边界时，一定要小心如何指定的维度。 `dimension`参数<xref:System.Array.GetLowerBound%2A>和<xref:System.Array.GetUpperBound%2A>方法是从 0 开始时`Rank`参数的 Visual Basic<xref:Microsoft.VisualBasic.Information.LBound%2A>和<xref:Microsoft.VisualBasic.Information.UBound%2A>函数都是基于 1 的。  
  
## <a name="see-also"></a>请参阅  
 [数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [如何：在 Visual Basic 中初始化数组变量](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
