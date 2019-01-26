---
title: Null 条件运算符 (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: d30d452a7c140a0c56529386b14ef3a3512df490
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722148"
---
# <a name="-and--null-conditional-operators-visual-basic"></a>?. 和？（） null 条件运算符 (Visual Basic)

测试是否为空的左操作数的值 (`Nothing`) 之前执行成员访问 (`?.`) 或索引 (`?()`); 操作返回`Nothing`如果左操作数的计算结果为`Nothing`。 请注意，在表达式中通常会返回值类型，null 条件运算符返回<xref:System.Nullable%601>。

这些运算符可帮助您编写更少代码来处理 null 检查，尤其是当下降到数据结构。 例如：

```vb
Dim length As Integer? = customers?.Length  ' Nothing if customers is Nothing  
Dim first As Customer = customers?(0)  ' Nothing if customers is Nothing  
Dim count As Integer? = customers?(0)?.Orders?.Count()  ' Nothing if customers, the first customer, or Orders is Nothing  
```

有关比较，这些表达式而无需 null 条件运算符的第一个替代代码是：

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

NULL 条件运算符采用最小化求值策略。  如果条件成员访问和索引操作链中的一个操作不返回任何内容，将停止的链的执行其余部分。  在以下示例中，如果 c （e） 不评估`A`， `B`，或`C`计算结果为 Nothing。

```vb
A?.B?.C?(E);
```

Null 条件成员访问的另一个用途是在使用非常少的代码以线程安全的方式调用委托。  旧方法需要如下所示的代码：  

```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```

新的方法是要简单得多：  

```vb
PropertyChanged?.Invoke(…)
```

新方法是线程安全的，因为编译器生成的代码仅评估 `PropertyChanged` 一次，从而使结果保持在临时变量中。 你需要显式调用 `Invoke` 方法，因为不存在 NULL 条件委托调用语法 `PropertyChanged?(e)`。  

## <a name="see-also"></a>请参阅

- [运算符 (Visual Basic)](index.md)
- [Visual Basic 编程指南](../../../visual-basic/programming-guide/index.md)
- [Visual Basic 语言参考](../../../visual-basic/language-reference/index.md)
