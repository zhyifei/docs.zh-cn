---
title: 发布 NuGet 包
description: 用于将.NET 库发布到 NuGet 的最佳做法建议。
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 0602712311411ef3d59825bec8c5e550bc8d8265
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2018
ms.locfileid: "49369800"
---
# <a name="publishing-a-nuget-package"></a>发布 NuGet 包

NuGet 包发布和使用包存储库中。 虽然 NuGet.org 最广为已知和已用存储库，有许多地方会发布 NuGet 包：

* **[NuGet.org](https://www.nuget.org/)** 是 NuGet 包的主联机存储库。 在 NuGet.org 上的所有包都都向每个人都使用公开提供。 默认情况下，Visual Studio NuGet.org 作为包源，因此很多开发人员 NuGet.org 它们将与之交互的唯一包存储库。 NuGet.org 是发布稳定的包和预发行包上所需社区反馈的最佳位置。

* **[MyGet](https://myget.org/)** 存储库服务支持[可用的自定义包源的开放源代码项目](https://www.myget.org/opensource)。 MyGet 公共自定义源是一个理想位置用于发布所创建的 CI 服务的预发行包。 MyGet 还许可后出于商业目的提供了专用源。

* 一个**[本地数据源](/nuget/hosting-packages/local-feeds)** 使您可以将包存储库等的文件夹，并使`*.nupkg`nuget 的可访问文件夹中的文件。 本地数据源可用于测试之前将其发布到 NuGet.org 的 NuGet 包。

> [!NOTE]
> NuGet.org[不允许要删除的包](/nuget/policies/deleting-packages)是上传。 包可以是未列出，以便它不是在 UI 中公开可见，但`*.nupkg`仍可还原上下载。 此外，nuget.org 不允许重复的包版本。 若要更正的错误必须取消列出包不正确的 NuGet 包，递增的版本号和发布包的新版本。

**执行 ✔️** [发布稳定的包和预发行包](/nuget/create-packages/publish-a-package)想到 NuGet.org 的社区反馈。

**请考虑 ✔️**预发行包发布到 MyGet 源从持续集成生成。

**请考虑 ✔️**使用本地数据源或 MyGet 在开发环境中测试包。 请检查包的工作原理，然后将其发布到 NuGet.org。

## <a name="nugetorg-security"></a>NuGet.org 安全

务必不良参与方无法访问你的 NuGet 帐户并上传恶意版本的库。 发布包时，NuGet.org 将提供双因素身份验证和电子邮件通知。 在登录到 NuGet.org 后启用这些功能**帐户设置**页。

![替换文字](./media/publish-nuget-package/nuget-2fa.png "NuGet 帐户安全")

**✔️ 执行**使用 Microsoft 帐户登录到 NuGet。

**✔️ 执行**启用双因素身份验证用于访问 NuGet。

**✔️ 执行**发布包时启用电子邮件通知。

>[!div class="step-by-step"]
[上一页](./sourcelink.md)
[下一页](./versioning.md)
