---
title: "声明为 For Each 循环控制变量的数组在声明时不能指定初始大小值"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords: BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0635e1b18b24a241fabad6d67da34f8dde9530db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
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
  
## <a name="see-also"></a>另请参阅  
 [For...Next 语句](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [阵列](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [集合](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)
