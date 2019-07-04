---
title: new 约束 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: 7c788be52010cdfadbd3c03f9e570815d25bdbef
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2019
ms.locfileid: "67401486"
---
# <a name="new-constraint-c-reference"></a>new 约束（C# 参考）

`new` 约束指定泛型类声明中的类型实参必须有公共的无参数构造函数。 若要使用 `new` 约束，则该类型不能为抽象类型。

当泛型类创建类型的新实例时，请将 `new` 约束应用于类型参数，如下面的示例所示：

[!code-csharp[csrefKeywordsOperator#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#5)]

当与其他约束一起使用时，`new()` 约束必须最后指定：

[!code-csharp[csrefKeywordsOperator#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#6)]

有关详细信息，请参阅[类型参数的约束](../../programming-guide/generics/constraints-on-type-parameters.md)。

`new` 关键字还可用于[创建类型的实例](../operators/new-operator.md)或用作[成员声明修饰符](new-modifier.md)。

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的[类型参数约束](~/_csharplang/spec/classes.md#type-parameter-constraints)部分。

## <a name="see-also"></a>请参阅

- [C# 参考](../../language-reference/index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 关键字](index.md)
- [泛型](../../programming-guide/generics/index.md)
