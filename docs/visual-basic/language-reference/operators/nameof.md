---
title: NameOf 运算符
description: 了解如何在 Visual Basic 中使用 NameOf 运算符
ms.date: 10/27/2019
helpviewer_keywords:
- NameOf operator [Visual Basic]
ms.openlocfilehash: e7dd55bfd98b34449b9f1a35375198598f57b46f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347022"
---
# <a name="nameof-operator---visual-basic"></a><span data-ttu-id="b0cb1-103">NameOf 运算符-Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b0cb1-103">NameOf operator - Visual Basic</span></span>

<span data-ttu-id="b0cb1-104">`NameOf` 运算符获取变量、类型或成员的名称作为字符串常量：</span><span class="sxs-lookup"><span data-stu-id="b0cb1-104">The `NameOf` operator obtains the name of a variable, type, or member as the string constant:</span></span>

```vb
Console.WriteLine(NameOf(System.Collections.Generic))  ' output: Generic
Console.WriteLine(NameOf(List(Of Integer)))  ' output: List
Console.WriteLine(NameOf(List(Of Integer).Count))  ' output: Count
Console.WriteLine(NameOf(List(Of Integer).Add))  ' output: Add

Dim numbers As New List(Of Integer) From { 1, 2, 3 }
Console.WriteLine(NameOf(numbers))  ' output: numbers
Console.WriteLine(NameOf(numbers.Count))  ' output: Count
Console.WriteLine(NameOf(numbers.Add))  ' output: Add
```

<span data-ttu-id="b0cb1-105">如前面的示例所示，对于类型和命名空间，生成的名称通常不是[完全限定的](~/_csharplang/spec/basic-concepts.md#fully-qualified-names)名称。</span><span class="sxs-lookup"><span data-stu-id="b0cb1-105">As the preceding example shows, in the case of a type and a namespace, the produced name is usually not [fully qualified](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).</span></span>

<span data-ttu-id="b0cb1-106">`NameOf` 运算符在编译时进行求值，在运行时无效。</span><span class="sxs-lookup"><span data-stu-id="b0cb1-106">The `NameOf` operator is evaluated at compile time, and has no effect at run time.</span></span>

<span data-ttu-id="b0cb1-107">可以使用 `NameOf` 运算符使参数检查代码更易于维护：</span><span class="sxs-lookup"><span data-stu-id="b0cb1-107">You can use the `NameOf` operator to make the argument-checking code more maintainable:</span></span>

```vb
Private _name As String

Public Property Name As String
    Get
        Return _name
    End Get
    Set
        If value Is Nothing Then
            Throw New ArgumentNullException(NameOf(value), $"{NameOf(name)} cannot be null.")
        End If
    End Set
End Property
```

<span data-ttu-id="b0cb1-108">`NameOf` 运算符在 Visual Basic 14 及更高版本中可用。</span><span class="sxs-lookup"><span data-stu-id="b0cb1-108">The `NameOf` operator is available in Visual Basic 14 and later.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0cb1-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0cb1-109">See also</span></span>

- [<span data-ttu-id="b0cb1-110">Visual Basic 语言参考</span><span class="sxs-lookup"><span data-stu-id="b0cb1-110">Visual Basic Language Reference</span></span>](../index.md)
- [<span data-ttu-id="b0cb1-111">运算符（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="b0cb1-111">Operators (Visual Basic)</span></span>](index.md)
