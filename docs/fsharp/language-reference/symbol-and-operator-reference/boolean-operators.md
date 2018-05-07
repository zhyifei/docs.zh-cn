---
title: 布尔运算符 (F#)
description: '了解有关 F # 编程语言中可用的布尔运算符。'
ms.date: 05/16/2016
ms.openlocfilehash: f8516ceb531907400f98dc4226d2985d3119e9e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="boolean-operators"></a>布尔运算符

本主题介绍对 F # 语言中的布尔运算符的支持。


## <a name="summary-of-boolean-operators"></a>布尔运算符的摘要
下表总结了在 F # 语言中可用的布尔运算符。 支持这些运算符的唯一类型是`bool`类型。

|运算符|描述|
|--------|-----------|
|`not`|布尔求反|
|<code>&#124;&#124;</code>|布尔 OR|
|`&&`|布尔 AND|

布尔 AND 和 OR 运算符执行*短路计算*，必要以确定表达式的总体结果时，即它们评估运算符右侧的表达式。 第二个表达式`&&`运算符计算仅当第一个表达式的计算结果为`true`; 的第二个表达式`||`运算符计算仅当第一个表达式的计算结果为`false`。

## <a name="see-also"></a>请参阅
[位运算符](bitwise-operators.md)

[算术运算符](arithmetic-operators.md)

[符号和运算符参考](index.md)
