---
ms.openlocfilehash: ef3e4f9f8145677732b9d2e66d416be277697f55
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920633"
---

添加到包管理器源的包以可改动的格式命名：`{product}-{type}-{version}`。

- **product**\
要安装的 .NET 产品的类型。 有效选项是：

  - dotnet
  - aspnetcore

- **type**\
选择 SDK 或运行时。 有效选项是：

  - SDK
  - Runtime — 运行时

- **version**\
要安装的 SDK 或运行时的版本。 本文始终提供最新支持的版本的说明。 有效选项为任何已发布的版本，例如：

  - 3.0
  - 2.2
  - 2.1

### <a name="examples"></a>示例

- 安装 .NET Core 2.2 SDK：`dotnet-sdk-2.2`
- 安装 ASP.NET Core 3.1 运行时：`aspnetcore-runtime-3.1`
- 安装 .NET Core 2.1 运行时：`dotnet-runtime-2.1`

### <a name="package-missing"></a>缺少包

如果包版本组合无效，则它不可用。 例如，未安装 ASP.NET Core SDK，所有 SDK 组件都包含在 .NET Core SDK 中。 `aspnetcore-sdk-2.2` 的值不正确，应为 `dotnet-sdk-2.2`。
