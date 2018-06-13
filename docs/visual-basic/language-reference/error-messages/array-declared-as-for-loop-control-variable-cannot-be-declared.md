---
title: 声明为 For Each 循环控制变量的数组在声明时不能指定初始大小值
ms.date: 07/20/2015
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords:
- BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
ms.openlocfilehash: f6cf397b1e76313ab399d5e39a43ae0263df619c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587979"
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a>声明为 For Each 循环控制变量的数组在声明时不能指定初始大小值
A`For Each`循环使用数组作为其*元素*迭代变量但初始化该数组。  
  
 以下语句显示可以如何生成此错误。  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 第一个`For Each`语句访问的元素的正确方法是`arrayList`。 第二个`For Each`语句会生成此错误。  
  
 **错误 ID:** BC32039  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   从的声明中删除初始化*元素*迭代变量。  
  
## <a name="see-also"></a>请参阅  
 [For...Next 语句](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [数组](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [集合](../../../standard/collections/index.md)
