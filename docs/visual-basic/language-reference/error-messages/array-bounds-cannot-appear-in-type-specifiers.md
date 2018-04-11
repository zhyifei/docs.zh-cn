---
title: 数组界限不能出现在类型说明符中
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 770f86ca960110965b6917a22d284678ff8b6f8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a>数组界限不能出现在类型说明符中
数组大小不能声明为数据类型说明符的一部分。  
  
 **错误 ID:** BC30638  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   指定紧靠而不是类型之后，将数组大小的变量名称，如下面的示例中所示的数组的大小。  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   定义一个数组，并将其与所需的元素数进行初始化，如下面的示例中所示。  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [阵列](../../../visual-basic/programming-guide/language-features/arrays/index.md)
