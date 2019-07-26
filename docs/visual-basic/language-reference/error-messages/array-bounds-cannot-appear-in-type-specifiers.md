---
title: 数组界限不能出现在类型说明符中
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: 951f710160ae1023671773c21c73946f5ae94c2b
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512766"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a>数组界限不能出现在类型说明符中

数组大小不能声明为数据类型说明符的一部分。

**错误 ID:** BC30638

## <a name="to-correct-this-error"></a>更正此错误

- 指定紧随变量名称后面的数组大小, 而不是将数组大小放在类型之后, 如下面的示例中所示。

  ```vb
  Dim Array(8) As Integer
  ```

- 定义一个数组, 并用所需的元素数对其进行初始化, 如以下示例中所示。

  ```vb
  Dim Array2() As Integer = New Integer(8) {}
  ```

## <a name="see-also"></a>请参阅

- [数组](../../../visual-basic/programming-guide/language-features/arrays/index.md)
