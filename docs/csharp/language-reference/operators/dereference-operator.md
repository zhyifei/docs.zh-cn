---
title: "-&gt; 运算符（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4c5918f56257feb29d2624ba29b8cebaaa4f4ebe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-gt-operator-c-reference"></a>-&gt; 运算符（C# 参考）
`->` 运算符将取消指针引用与成员访问结合起来。  
  
## <a name="remarks"></a>备注  
 形式如下的表达式，  
  
```  
x->y  
```  
  
 （其中 `x` 是 `T*` 类型的指针，`y` 属于 `T`）等效于  
  
```  
(*x).y  
```  
  
 `->` 运算符仅可用于标记为[不安全](../../../csharp/language-reference/keywords/unsafe.md)的代码中。  
  
 不能重载 `->` 运算符。  
  
## <a name="example"></a>示例  
 [!code-csharp[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
