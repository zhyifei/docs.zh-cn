---
title: 布尔运算符 (F#)
description: '了解有关 F # 编程语言中可用的布尔运算符。'
ms.date: 05/16/2016
ms.openlocfilehash: faa181090efa7c4064a30b42d83afa4888e98b82
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43784509"
---
# <a name="boolean-operators"></a>布尔运算符

本主题介绍对 F # 语言中的布尔运算符的支持。

## <a name="summary-of-boolean-operators"></a>布尔运算符的摘要

下表汇总了 F # 语言中可用的布尔运算符。 这些运算符支持的唯一类型是`bool`类型。

|运算符|描述|
|--------|-----------|
|`not`|布尔值求反|
|<code>&#124;&#124;</code>|布尔 OR|
|`&&`|布尔 AND|

执行布尔 AND 和 OR 运算符*短路计算*，即，它们仅在必要时以确定总体结果表达式的计算运算符右侧的表达式。 第二个表达式`&&`仅当第一个表达式的计算结果为计算运算符`true`; 的第二个表达式`||`仅当第一个表达式的计算结果为计算运算符`false`。

## <a name="see-also"></a>请参阅

- [位运算符](bitwise-operators.md)
- [算术运算符](arithmetic-operators.md)
- [符号和运算符参考](index.md)
