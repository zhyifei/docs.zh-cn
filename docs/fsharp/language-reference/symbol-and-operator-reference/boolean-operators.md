---
title: "布尔运算符 (F#)"
description: "了解有关 F # 编程语言中可用的布尔运算符。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f79370b8-4bc2-4704-b514-d392c80942bd
ms.openlocfilehash: 63588f2e371bf2c0f15de0b8a26a46be82f832c7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
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

## <a name="see-also"></a>另请参阅
[位运算符](bitwise-operators.md)

[算术运算符](arithmetic-operators.md)

[符号和运算符参考](index.md)
