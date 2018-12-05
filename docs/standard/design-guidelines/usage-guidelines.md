---
title: 使用准则
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e583bf7768c60477effb6c1cf9b838ae4c8c182
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197933"
---
# <a name="usage-guidelines"></a>使用准则

本部分包含在可公开访问的 API 中使用常见类型的指南。其中涉及如何直接使用内置框架类型（例如，序列化属性）和重载常用运算符。
  
<xref:System.IDisposable?displayProperty=nameWithType> 接口不在此部分进行介绍，但在 [Dispose 模式](../../../docs/standard/design-guidelines/dispose-pattern.md) 部分进行了讨论。

> [!NOTE]
> 有关其他常见内置 .NET Framework 类型的指南和其他信息，请参阅以下内容的参考主题：<xref:System.DateTime?displayProperty=nameWithType>、<xref:System.DateTimeOffset?displayProperty=nameWithType>、<xref:System.ICloneable?displayProperty=nameWithType>、<xref:System.IComparable%601?displayProperty=nameWithType>、<xref:System.IEquatable%601?displayProperty=nameWithType>、<xref:System.Nullable%601?displayProperty=nameWithType>、<xref:System.Object?displayProperty=nameWithType>、<xref:System.Uri?displayProperty=nameWithType>。

## <a name="in-this-section"></a>本节内容

[数组](arrays.md)
[属性](attributes.md)
[集合](guidelines-for-collections.md)
[序列化](serialization.md)
[System.Xml 用法](system-xml-usage.md)
[相等运算符](equality-operators.md)

*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*

*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
