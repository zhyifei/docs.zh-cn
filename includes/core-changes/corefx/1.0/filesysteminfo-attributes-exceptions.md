---
ms.openlocfilehash: 4091bdcf7d9ed8872aed5faa6e6d3ed143903787
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449386"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a>FileSystemInfo.Attributes 引发的 UnauthorizedAccessException

在 .NET Core 中，当调用方尝试设置文件属性值但没有写权限时，将引发 <xref:System.UnauthorizedAccessException>。

#### <a name="change-description"></a>更改描述

在 .NET Framework 中，当调用方尝试在 <xref:System.ArgumentException> 中设置文件属性值但没有写权限时，将引发 <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>。 在 .NET Core 中，将改为引发 <xref:System.UnauthorizedAccessException>。 （在 .NET Core 中，如果调用方尝试设置无效的文件属性，则仍会引发 <xref:System.ArgumentException>。）

#### <a name="version-introduced"></a>引入的版本

1.0

#### <a name="recommended-action"></a>建议操作

根据需要修改任何 `catch` 语句不是捕获 <xref:System.UnauthorizedAccessException>，而是捕获或者除它之外还捕获 <xref:System.ArgumentException>。

#### <a name="category"></a>类别

CoreFx

#### <a name="affected-apis"></a>受影响的 API

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
