---
title: NULL 条件运算符（C# 和 Visual Basic）
ms.date: 04/03/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- null-conditional operators [C#]
- null-conditional operators [Visual Basic]
- ?. operator [C#]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3ffeaa3c2088d0bb2c000704cfe312b0f9453b68
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2018
---
# <a name="-and--null-conditional-operators-c-and-visual-basic"></a>?. 和 ?[] NULL 条件运算符（C# 和 Visual Basic）
用于在执行成员访问 (`?.`) 或索引 (`?[]`) 操作之前，测试是否存在 NULL。  这些运算符可帮助编写更少的代码来处理 null 检查，尤其是对于下降到数据结构。  
  
```csharp  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
```  
  
```vb  
Dim length = customers?.Length  ' null if customers is null  
Dim first as Customer = customers?(0)  ' null if customers is null  
Dim count as Integer? = customers?(0)?.Orders?.Count()  ' null if customers, the first customer, or Orders is null  
```  
  
 NULL 条件运算符采用最小化求值策略。  如果条件成员访问和索引操作链中的某个操作返回 NULL，则该链其余部分的执行将停止。  在下面的示例中，如果 `A`、`B` 或 `C` 的计算结果为 NULL，就不会执行 `E`。
  
```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

```vb
A?.B?.C?.Do(E);
A?.B?.C?(E);
```  
  
 NULL 条件成员访问的另一个用途是使用非常少的代码以线程安全的方式调用委托。  旧方法需要如下所示的代码：  
  
```csharp  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…);
```  
  
```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```  
  
 新的方法是要简单得多：  
  
```csharp
PropertyChanged?.Invoke(e)  
```  

```vb
PropertyChanged?.Invoke(e)
```  
  
 新方法是线程安全的，因为编译器生成的代码仅评估 `PropertyChanged` 一次，从而使结果保持在临时变量中。  
  
 你需要显式调用 `Invoke` 方法，因为不存在 NULL 条件委托调用语法 `PropertyChanged?(e)`。  
  
## <a name="language-specifications"></a>语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
 有关详细信息，请参阅 [Visual Basic 语言参考](../../../visual-basic/language-reference/index.md)。  
  
## <a name="see-also"></a>请参阅  
 [??（空合运算符）](null-conditional-operator.md)  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [Visual Basic 语言参考](../../../visual-basic/language-reference/index.md)  
 [Visual Basic 编程指南](../../../visual-basic/programming-guide/index.md)
