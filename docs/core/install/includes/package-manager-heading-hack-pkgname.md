---
ms.openlocfilehash: 7a55641b3673dc4d8d9b328f0de99b7247ca51d4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74998797"
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
- 安装 ASP.NET Core 3.0 运行时：`aspnetcore-runtime-3.0`
- 安装 .NET Core 2.1 运行时：`dotnet-runtime-2.1`

### <a name="troubleshoot"></a>疑难解答

如果包组合无效，则它不可用。 例如，未安装 ASP.NET Core SDK，所有 SDK 组件都包含在 .NET Core SDK 中。 `aspnetcore-sdk-2.2` 的值不正确，应为 `dotnet-sdk-2.2`
