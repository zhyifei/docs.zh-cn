---
ms.openlocfilehash: 2a751acc129ebd1c917b87f8083ffef72c7d8c17
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568198"
---
### <a name="apis-that-report-version-now-report-product-and-not-file-version"></a>报告版本的 API 现报告的是产品版本而不是文件版本

返回 .NET Core 中的版本的很多 API 现在返回的是产品版本，而不是文件版本。

#### <a name="change-description"></a>更改描述

在 .NET Core 2.2 及更低版本中，<xref:System.Environment.Version?displayProperty=nameWithType> 和 <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> 等方法以及 .NET Core 程序集的“文件属性”对话框反映的都是文件版本。 自 .NET Core 3.0 起，它们反映的是产品版本。

下图展示了由“Windows 资源管理器”文件属性对话框显示的 .NET Core 2.2（左侧）与 .NET Core 3.0（右侧）的 System.Runtime.dll 程序集版本信息区别   。

![产品版本信息中的差异](~/docs/images/core-changes/corefx/version-information-changes/file-details.png)

#### <a name="version-introduced"></a>引入的版本

3.0

#### <a name="recommended-action"></a>建议的操作

无。 此更改会使版本检测变得直观而非退化。

#### <a name="category"></a>类别

CoreFx

#### <a name="affected-apis"></a>受影响的 API

- <xref:System.Environment.Version?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>

<!--

### Affected APIs

- `P:System.Environment.Version`
- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
