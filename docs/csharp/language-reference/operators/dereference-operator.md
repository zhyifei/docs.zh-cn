---
title: -&gt; 运算符（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: 09d67b8386da371f7d98a8171f60298b316091ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
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
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 运算符](../../../csharp/language-reference/operators/index.md)
