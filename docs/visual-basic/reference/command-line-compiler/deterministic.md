---
title: -确定性
ms.date: 04/11/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 273abf8811f04cd7f58599ce3421ca1f17c740d9
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="-deterministic"></a>-确定性

使编译器生成的程序集针对同一个输入编译都是相同的字节的字节输出。 

## <a name="syntax"></a>语法

```
-deterministic
```

## <a name="remarks"></a>备注

默认情况下，从给定的一组输入编译器输出是唯一的因为编译器将添加的时间戳和从随机数生成的 GUID。 你使用`-deterministic`选项来生成*确定性的程序集*，其中一个，只要输入保持不变，其二进制内容是跨编译相同。

编译器认为出于确定性目的的以下输入：

- 命令行参数的序列。
- 编译器的.rsp 响应文件的内容。
- 使用，则编译器的精确版本和其引用的程序集。
- 当前的目录路径。
- 所有文件的二进制内容显式传递到编译器直接或间接包括： 
    - 源文件
    - 引用的程序集
    - 引用的模块
    - 资源
    - 强名称密钥文件
    - @ 响应文件
    - 分析器
    - 规则集
    - 可能由分析器的其他文件
- （用于诊断和异常生成消息的语言） 的当前区域性。
- 默认编码 （或当前代码页） 如果未指定的编码。
- 是否存在、 不存在，以及编译器的搜索路径上的文件的内容 (例如，由指定`/lib`或`/recurse`)。
- 在其运行编译器 CLR 平台。
- 值`%LIBPATH%`，这可能会影响分析器的依赖项加载。

当源公开可用时，确定性编译可以用于建立从受信任的源是否已编译二进制文件。 它还可用于确定是否依赖于对二进制文件的更改的生成步骤需要执行连续生成系统中有用。 

## <a name="see-also"></a>请参阅
[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
[示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
