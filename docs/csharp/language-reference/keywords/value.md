---
title: value 上下文关键字 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: 34b192d17bd96b6b893c9f14f0d4a77274a32f78
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771745"
---
# <a name="value-c-reference"></a>value（C# 参考）

上下文关键字 `value` 在[属性](../../programming-guide/classes-and-structs/properties.md)和[索引器](../../programming-guide/indexers/index.md)声明的 `set` 访问器中使用。 此关键字类似于方法的输入参数。 关键字 `value` 引用客户端代码尝试分配给属性或索引器的值。 在以下示例中，`MyDerivedClass` 有一个名为 `Name` 的属性，该属性使用 `value` 参数向支持字段 `name` 分配新字符串。 从客户端代码的角度来看，该操作写作一个简单的赋值语句。

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

有关详细信息，请参阅[属性](../../programming-guide/classes-and-structs/properties.md)和[索引器](../../programming-guide/indexers/index.md)一文。

## <a name="c-language-specification"></a>C# 语言规范

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 关键字](index.md)
