---
title: 下载验证颁发者名称注册表包
ms.date: 10/10/2018
ms.assetid: ff8b0014-c5d4-4614-90f0-13fcc0ba777a
ms.openlocfilehash: 833a0722fdd27df4e488ed7fac99444c6d9b8905
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940577"
---
# <a name="download-the-validating-issuer-name-registry-package"></a>下载验证颁发者名称注册表包

本主题讨论如何在项目中下载和使用验证颁发者名称注册表 (VINR)。

VINR 可用作 NuGet 包，可将必要程序集和引用添加到项目。 如果尚未安装 NuGet，请转到 [nuget.org](https://nuget.org) 进行安装。 可以通过在 NuGet 上访问其页面看到扩展的版本控制历史记录：[Microsoft 验证 NuGet 上的颁发者名称注册表](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)

## <a name="use-the-package-manager-gui"></a>使用程序包管理器 GUI

1. 在 Visual Studio 中，在解决方案资源管理器中右键单击项目，然后选择“管理 NuGet 包”。

2. 在“管理 NuGet 包”窗口中，单击搜索框并输入 `ValidatingIssuerNameRegistry`，然后按 Enter。

3. 单击结果窗格中第一个结果的“安装”按钮。

4. 将开始下载包。 将包添加到项目前，会出现“许可证接受”对话框。 如果同意许可条款，请单击“我接受”。

5. 将下载并添加最新 VINR 程序集到项目。

## <a name="use-the-package-manager-console"></a>使用包管理器控制台

1. 在 Visual Studio 中，单击**工具** > **NuGet 包管理器** > **程序包管理器控制台**。

2. 随即出现“包管理器控制台”。 输入以下文本并按 Enter：

    ```powershell
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry
    ```

3. 将下载并添加最新 VINR 程序集到项目。