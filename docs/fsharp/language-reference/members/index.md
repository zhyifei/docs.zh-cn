---
title: 成员 (F#)
description: '了解在 F # 编程语言的对象成员。'
keywords: visual f#, f#, 函数编程
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e472f50a-4939-4e62-abbc-471f8f265790
ms.openlocfilehash: ca34c8d073594791ec268a85ad56f50cc6d9e435
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="members"></a>成员

本部分介绍 F# 对象类型的成员。


## <a name="remarks"></a>备注
*成员*是一种属于类型定义的功能，可使用 `member` 关键字进行声明。 记录、类、可区分联合、接口和结构等 F# 对象类型都支持成员。 有关详细信息，请参阅[记录](../records.md)、[类](../classes.md)、[可区分联合](../discriminated-Unions.md)、[接口](../interfaces.md)和[结构](../structures.md)。

成员通常组成类型的公共接口，这就是成员通常是公共成员（除非另外指定）的原因。 也可以声明私有成员或内部成员。 有关详细信息，请参阅[访问控制](../access-Control.md)。 类型的签名还可用于公开或不公开类型的某些成员。 有关详细信息，请参阅[签名](../signatures.md)。

只能与类一起使用的私有字段和 `do` 绑定不是真正的成员，因为它们从不是类型的公共接口的一部分，并且也不是用 `member` 关键字声明的，但本部分对它们也进行了介绍。


## <a name="related-topics"></a>相关主题


|主题|说明|
|-----|-----------|
|[类中的 `let` 绑定](let-bindings-in-classes.md)|介绍类中私有字段和函数的定义。|
|[类中的 `do` 绑定](do-bindings-in-classes.md)|介绍对象初始化代码的规范。|
|[属性](properties.md)|介绍类和其他类型中的属性成员。|
|[索引属性](indexed-properties.md)|介绍类和其他类型中的类似数组的属性。|
|[方法](methods.md)|介绍属于类型的成员的函数。|
|[构造函数](constructors.md)|介绍用于初始化类型的对象的特殊函数。|
|[运算符重载](../operator-overloading.md)|介绍类型的自定义运算符的定义。|
|[事件](events.md)|介绍 F# 中的事件定义和事件处理支持。|
|[显式字段：`val` 关键字](explicit-fields-the-val-keyword.md)|介绍类型中未初始化字段的定义。|
