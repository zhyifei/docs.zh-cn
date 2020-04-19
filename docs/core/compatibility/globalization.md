---
title: 全球化中断性变更
description: 列出 .NET Core 中全球化过程内的中断性变更。
ms.date: 04/07/2020
ms.openlocfilehash: 1436f9e2ec540b0f8b1e710b25c2115646d4e5b4
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888159"
---
# <a name="globalization-breaking-changes"></a>全球化中断性变更

本页记录了以下中断性变更：

| 重大更改 | 引入的版本 |
| - | :-: |
| [StringInfo 和 TextElementEnumerator 现在与 UAX29 兼容](#stringinfo-and-textelementenumerator-are-now-uax29-compliant) | 5.0 |
| [“C”区域设置映射到固定区域设置](#c-locale-maps-to-the-invariant-locale) | 3.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [uax29-compliant-grapheme-enumeration](../../../includes/core-changes/globalization/5.0/uax29-compliant-grapheme-enumeration.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE["C" locale maps to the invariant locale](~/includes/core-changes/globalization/3.0/c-locale-maps-to-invariant-locale.md)]

***
