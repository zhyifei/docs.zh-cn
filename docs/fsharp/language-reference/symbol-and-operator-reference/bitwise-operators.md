---
title: "位运算符 (F#)"
description: "了解有关 F # 编程语言中可用的按位运算符的信息。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8a2c87f5-b4c7-47fe-8580-82c956f605e5
ms.openlocfilehash: 61a8e6bafe97a229480c967a4afb5d2a256474c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="bitwise-operators"></a>位运算符

本主题介绍对 F # 语言中提供的按位运算符。

## <a name="summary-of-bitwise-operators"></a>按位运算符的摘要
下表介绍对 F # 语言中的未装箱整型类型的支持的按位运算符。

|运算符|说明|
|--------|-----|
|`&&&`|按位 AND 运算符。 当且仅当在源中的两个操作数的相应位均为 1，结果中的位将具有值 1。|
|<code>&#124;&#124;&#124;</code>|按位 OR 运算符。 结果中的位具有值 1，如果任一操作数的源中的对应位都是 1。|
|`^^^`|按位异或运算符。 当且仅当源操作数中的位具有不相等的值，结果中的位将具有值 1。|
|`~~~`|按位求反运算符。 这是一个一元运算符，并生成的结果，在其中源操作数中的所有 0 位转换为 1 位，而所有 1 位转换为 0 的位。|
|`<<<`|按位左移运算符。 结果是第一个操作数中的位左移的第二个操作数中的位数。 移出最高有效位的数位不会转入最低有效位。 最低有效位用零填充。 第二个参数的类型是`int32`。|
|`>>>`|按位右移运算符。 结果是通过第二个操作数中的位数向右位移位进行运算的第一个操作数。 移去最低有效位不会转入最高有效位。 对于无符号类型，最高有效位将补零。 对于有符号类型，最高有效位将补替换为。 第二个参数的类型是`int32`。|

可与按位运算符使用以下类型： `byte`， `sbyte`， `int16`， `uint16`， `int32 (int)`， `uint32`， `int64`， `uint64`， `nativeint`，和`unativeint`。

## <a name="see-also"></a>另请参阅
[符号和运算符参考](index.md)

[算术运算符](arithmetic-operators.md)

[布尔运算符](boolean-operators.md)

