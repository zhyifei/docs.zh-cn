---
title: Null 条件运算符（Visual Basic）
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: 40cb63705eda563b4c3cfd30fa9836a8f632dccf
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581633"
---
# <a name="-and--null-conditional-operators-visual-basic"></a>?. 与?（） null-条件运算符（Visual Basic）

在执行成员访问（`?.`）或索引（`?()`）操作之前，测试左操作数的值是否为 null （`Nothing`）;如果左操作数的计算结果为 `Nothing`，则返回 `Nothing`。 请注意，在通常返回值类型的表达式中，null 条件运算符返回 <xref:System.Nullable%601>。

这些运算符可帮助编写更少的代码来处理 null 检查，尤其是在对数据结构进行降序操作时。 例如:

```vb
' Nothing if customers is Nothing
Dim length As Integer? = customers?.Length

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()
```

为了进行比较，这些表达式中第一个表达式的替代代码没有 null 条件运算符：

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

有时，你需要对可能为 null 的对象执行操作，这取决于该对象上布尔成员的值（如以下示例中的布尔属性 `IsAllowedFreeShipping`）：

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer IsNot Nothing AndAlso customer.IsAllowedFreeShipping Then
  ApplyFreeShippingToOrders(customer)
End If
```

可以通过使用 null 条件运算符来缩短代码，避免手动检查是否为 null，如下所示：

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer?.IsAllowedFreeShipping Then ApplyFreeShippingToOrders(customer)
```

NULL 条件运算符采用最小化求值策略。  如果条件成员访问和索引操作链中的某个操作返回 `Nothing`，则将停止其余链的执行。  在以下示例中，如果 `A`、`B` 或 `C` 的计算结果为 `Nothing`，则不会计算 `C(E)`。

```vb
A?.B?.C?(E);
```

Null 条件成员访问的另一个用途是使用更少的代码以线程安全的方式调用委托。  下面的示例定义了两个类型： `NewsBroadcaster` 和 `NewsReceiver`。 @No__t_0 委托将新闻项目发送给接收方。

```vb
Public Module NewsBroadcaster
   Dim SendNews As Action(Of String)

   Public Sub Main()
      Dim rec As New NewsReceiver()
      Dim rec2 As New NewsReceiver()
      SendNews?.Invoke("Just in: A newsworthy item...")
   End Sub

   Public Sub Register(client As Action(Of String))
      SendNews = SendNews.Combine({SendNews, client})
   End Sub
End Module

Public Class NewsReceiver
   Public Sub New()
      NewsBroadcaster.Register(AddressOf Me.DisplayNews)
   End Sub

   Public Sub DisplayNews(newsItem As String)
      Console.WriteLine(newsItem)
   End Sub
End Class
```

如果 `SendNews` 调用列表中没有元素，则 `SendNews` 委托将引发一个 <xref:System.NullReferenceException>。 在 null 条件运算符之前，如下代码确保委托调用列表不 `Nothing`：

```vb
SendNews = SendNews.Combine({SendNews, client})
If SendNews IsNot Nothing Then
   SendNews("Just in...")
End If
```

新的方法是要简单得多：

```vb
SendNews = SendNews.Combine({SendNews, client})
SendNews?.Invoke("Just in...")
```

新方法是线程安全的，因为编译器生成的代码仅评估 `SendNews` 一次，从而使结果保持在临时变量中。 你需要显式调用 `Invoke` 方法，因为不存在 NULL 条件委托调用语法 `SendNews?(String)`。

## <a name="see-also"></a>请参阅

- [运算符（Visual Basic）](index.md)
- [Visual Basic 编程指南](../../../visual-basic/programming-guide/index.md)
- [Visual Basic 语言参考](../../../visual-basic/language-reference/index.md)
