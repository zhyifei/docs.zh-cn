---
title: dotnet nuget update source 命令
description: dotnet nuget update source 命令在 NuGet 配置文件中更新现有源。
ms.date: 03/20/2020
ms.openlocfilehash: 38335e07f91850756c7671413e1193c2578e7e7e
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148470"
---
# <a name="dotnet-nuget-update-source"></a>dotnet nuget update source

**本文适用于：** ✔️ .NET Core 3.1.200 SDK 及更高版本

## <a name="name"></a>“属性”

`dotnet nuget update source` - 更新 NuGet 源。

## <a name="synopsis"></a>摘要

```dotnetcli
dotnet nuget update source <NAME> [--source] [--username]
    [--password] [--store-password-in-clear-text] [--valid-authentication-types]
    [--configfile]
dotnet nuget update source [-h|--help]
```

## <a name="description"></a>描述

`dotnet nuget update source` 命令在 NuGet 配置文件中更新现有源。

## <a name="arguments"></a>自变量

- **`NAME`**

  源的名称。

## <a name="options"></a>选项

- **`--configfile`**

  NuGet 配置文件。 如果指定，则只使用此文件中的设置。 如果不指定，将使用当前目录中的配置文件的层次结构。 有关详细信息，请参阅[常见的 NuGet 配置](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior)。

- **`-p|--password`**

  连接到已验证源时要使用的密码。

- **`-s|--source`**

  包源的路径。

- **`--store-password-in-clear-text`**

  通过禁用密码加密允许存储可移植包源凭据。

- **`-u|--username`**

  连接到已经过身份验证的源时要使用的用户名。

- **`--valid-authentication-types`**

  此源的有效身份验证类型的逗号分隔列表。 如果服务器公布 NTLM 或协商，并且你必须使用基本机制发送凭据（例如，在本地 Azure DevOps Server 中使用 PAT 时），则将此项设置为 `basic`。 其他有效值包括 `negotiate`、`kerberos`、`ntlm` 和 `digest`，但这些值不太可能有用。

## <a name="examples"></a>示例

- 更新名为 `mySource` 的源：

  ```dotnetcli
  dotnet nuget update source mySource --source c:\packages
  ```

## <a name="see-also"></a>请参阅

- [NuGet.config 文件中的包源部分](/nuget/reference/nuget-config-file#package-source-sections)

- [sources 命令 (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
