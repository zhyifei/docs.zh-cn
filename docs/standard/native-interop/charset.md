---
title: 字符集和封送 - .NET
description: 了解字符集的不同值如何更改 .NET 将数据封送到本机代码的方式。
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: c50c58ad639b1efb29c13e5124fe3c32e8af96fc
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063335"
---
# <a name="charsets-and-marshaling"></a>字符集和封送

`char` 值、`string` 对象和 `System.Text.StringBuilder` 对象的封送方式取决于 P/Invoke 或结构上的 `CharSet` 字段的值。 可以通过在声明 P/Invoke 时设置 <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 字段来设置 P/Invoke 的 `CharSet`。 若要设置结构的 `CharSet`，请在声明结构时设置 <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> 字段。 未设置这些属性字段时，将由语言编译器确定使用哪些 `CharSet`。 C# 和 VB 默认使用 <xref:System.Runtime.InteropServices.CharSet.Ansi> 字符集。

下表显示了每个字符集之间的映射以及字符或字符串在使用该字符集封送时的表示形式：

| `CharSet` 值 | Windows            | Unix 上的 .NET Core 2.2 及更低版本 | Unix 上的 .NET Core 3.0 及更高版本和 Mono |
|-----------------|--------------------|-----------------------------------|------------------------------------------|
| Ansi            | `char` (ANSI)      | `char` (UTF-8)                    | `char` (UTF-8)                           |
| Unicode         | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char16_t` (UTF-16)                      |
| 自动            | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char` (UTF-8)                           |

确保了解选择字符集时所需的本机表示形式。
