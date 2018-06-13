---
title: 如何：在 Visual Basic 中初始化数组变量
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], initializing
- arrays [Visual Basic], variables
- arrays [Visual Basic], initializing
- arrays [Visual Basic], declaring
ms.assetid: aadd7a60-7ca4-4608-b986-091f19e7fc10
ms.openlocfilehash: ee8cb91fd2fae9637a0d0e33fca63a4cdb9d2fce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651565"
---
# <a name="how-to-initialize-an-array-variable-in-visual-basic"></a>如何：在 Visual Basic 中初始化数组变量
可以通过包括数组文本中初始化数组变量`New`子句和指定数组的初始值。 你可以指定的类型，或允许其被推断从数组文本中的值。 有关如何推断出的类型的详细信息，请参见"填充数组与初始值"[数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)。  
  
### <a name="to-initialize-an-array-variable-by-using-an-array-literal"></a>若要通过使用数组文本中初始化数组变量  
  
-   在`New`子句，或当分配的数组值时，提供在括号内的元素值 (`{}`)。 下面的示例演示通过多种方式来声明、 创建和初始化一个变量来包含具有类型的元素的数组的`Char`。  
  
     [!code-vb[VbVbalrArrays#16](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_1.vb)]  
  
     每个语句执行后，数组创建有长度为 3，与通过索引包含初始值的 2 的索引 0 处的元素。 如果你提供的上限和值，则必须包含从 0 到上限的每个元素的值。  
  
     请注意你无需指定索引上限，如果你提供数组文本中的元素值。 如果指定没有上限，则数组的大小是基于推断出的数组文本中的值的数目。  
  
### <a name="to-initialize-a-multidimensional-array-variable-by-using-array-literals"></a>若要通过使用数组文本初始化多维数组变量  
  
-   嵌套在括号内的值 (`{}`) 在大括号内。 请确保所有推断为相同类型和长度的数组的嵌套的数组文本。 下面的代码示例显示几个示例的多维数组初始化。  
  
     [!code-vb[VbVbalrArrays#17](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_2.vb)]  
  
-   你可以显式指定数组界限，或省略它们并让编译器推断基于文本数组中的值的数组边界。 如果你提供了上限和值，则必须每个维度中包含从 0 到上限的每个元素的值。 下面的示例演示通过多种方式来声明、 创建和初始化一个变量来包含一个具有类型的元素的二维数组 `Short`  
  
     [!code-vb[VbVbalrArrays#18](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_3.vb)]  
  
     每个语句执行后，创建的数组包含有索引的六个初始化的元素`(0,0)`， `(0,1)`， `(0,2)`， `(1,0)`， `(1,1)`，和`(1,2)`。 每个数组位置包含的值`10`。  
  
-   下面的示例循环访问一个多维数组。 在 Windows 控制台应用程序在 Visual Basic 中编写的将粘贴内的代码`Sub Main()`方法。 最后一个注释显示输出。  
  
     [!code-vb[VbVbalrArrays#31](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_4.vb)]  
  
### <a name="to-initialize-a-jagged-array-variable-by-using-array-literals"></a>若要通过使用数组文本初始化交错的数组变量  
  
-   嵌套在括号内的对象值 (`{}`)。 虽然你还可以嵌套数组文本指定数组的不同长度，对于交错数组，请确保嵌套的数组文本括在括号中 (`()`)。 括号强制的嵌套的数组文本中，计算，生成的数组可用作交错数组的初始值。 下面的代码示例显示交错的数组初始化的两个示例。  
  
     [!code-vb[VbVbalrArrays#19](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_5.vb)]  
  
-   下面的示例循环访问一个交错数组。 在 Windows 控制台应用程序在 Visual Basic 中编写的将粘贴内的代码`Sub Main()`方法。  在代码中的最后一个注释显示输出。  
  
     [!code-vb[VbVbalrArrays#32](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_6.vb)]  
  
## <a name="see-also"></a>请参阅  
 [数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [数组疑难解答](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
