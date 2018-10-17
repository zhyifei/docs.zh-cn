---
title: 下载 JSON Web 标记处理程序包
ms.date: 10/10/2018
ms.assetid: d12b3f5b-f1f1-4a9d-a159-0c13e5976c90
ms.openlocfilehash: 8f878d23afd76488de7da03f16f72cbfa43c17d7
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2018
ms.locfileid: "49316475"
---
# <a name="download-the-json-web-token-handler-package"></a>下载 JSON Web 令牌处理程序包

本主题讨论了如何在项目中下载和使用 JSON Web 令牌处理程序。

JSON Web 令牌处理程序扩展可用作 NuGet 程序包，可将必要程序集和引用添加到项目。 如果尚未安装 NuGet，请转到 [nuget.org](https://nuget.org) 进行安装。 访问 NuGet 上的扩展页面，查看扩展的版本历史记录：[NuGet 上的 JSON Web 令牌处理程序](https://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)

## <a name="use-the-package-manager-gui"></a>使用程序包管理器 GUI

1. 在 Visual Studio 中，在解决方案资源管理器中右键单击项目，然后选择“管理 NuGet 包”。

2. 在“管理 NuGet 包”窗口中，单击搜索框并输入 `JWT Token Handler`，然后按 Enter。

3. 单击结果窗格中第一个结果的“安装”按钮。

4. 将开始下载包。 将包添加到项目前，会出现“许可证接受”对话框。 如果同意许可条款，请单击“我接受”。

5. 将下载最新的 JSON Web 令牌处理程序程序集并添加到项目。

## <a name="use-the-package-manager-console"></a>使用包管理器控制台

1. 在 Visual Studio 中，单击**工具** > **NuGet 包管理器** > **程序包管理器控制台**。

2. 随即出现“包管理器控制台”。 输入以下文本并按 Enter：

    ```powershell
    Install-Package System.IdentityModel.Tokens.Jwt
    ```

3. 将下载最新的 JSON Web 令牌处理程序程序集并添加到项目。