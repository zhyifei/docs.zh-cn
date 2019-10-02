---
title: 如何：确定可为空的值类型 - C# 编程指南
ms.custom: seodec18
description: 了解如何确定类型是否是可为空的值类型或实例是否是可为空的值类型
ms.date: 09/26/2019
helpviewer_keywords:
- nullable value types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
ms.openlocfilehash: 15b1ffedf57648955ee5a004514841a5d140292b
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392608"
---
# <a name="how-to-identify-a-nullable-value-type-c-programming-guide"></a>如何确定可为空的值类型（C# 编程指南）

下面的示例演示了如何确定 <xref:System.Type?displayProperty=nameWithType> 实例是否表示可为空的封闭式泛型值类型，即，具有指定类型参数 `T` 的 <xref:System.Nullable%601?displayProperty=nameWithType> 类型：

[!code-csharp-interactive[whether Type is nullable](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#1)]

如示例所示，使用 [typeof](../../language-reference/operators/type-testing-and-cast.md#typeof-operator) 运算符来创建 <xref:System.Type?displayProperty=nameWithType> 对象。

如果要确定实例是否是可为空的值类型，请不要使用 <xref:System.Object.GetType%2A?displayProperty=nameWithType> 方法获取要通过前面的代码测试的 <xref:System.Type> 实例。 如果对值类型可为空的实例调用 <xref:System.Object.GetType%2A?displayProperty=nameWithType> 方法，该实例将[装箱](using-nullable-types.md#boxing-and-unboxing)到 <xref:System.Object>。 由于对可为空的值类型的非 NULL 实例的装箱等同于对基础类型的值的装箱，因此 <xref:System.Object.GetType%2A> 会返回表示可为空的值类型的基础类型的 <xref:System.Type> 对象：

[!code-csharp-interactive[GetType example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#2)]

请勿使用 [is](../../language-reference/keywords/is.md) 运算符来确定实例是否是可为空的值类型。 如以下示例所示，无法使用 `is` 运算符区分可为空的值类型的实例类型与其基础类型：

[!code-csharp-interactive[is operator example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#3)]

可使用以下示例中提供的代码来确定实例是否是可为空的值类型：

[!code-csharp-interactive[whether an instance is of a nullable type](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#4)]

## <a name="see-also"></a>请参阅

- [可以为 null 的值类型](index.md)
- [使用可为空的值类型](using-nullable-types.md)
- <xref:System.Nullable.GetUnderlyingType%2A>
