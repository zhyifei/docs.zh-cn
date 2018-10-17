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
# <a name="publishing-a-nuget-package"></a><span data-ttu-id="7bb24-103">发布 NuGet 包</span><span class="sxs-lookup"><span data-stu-id="7bb24-103">Publishing a NuGet package</span></span>

<span data-ttu-id="7bb24-104">NuGet 包发布和使用包存储库中。</span><span class="sxs-lookup"><span data-stu-id="7bb24-104">NuGet packages are published and consumed from package repositories.</span></span> <span data-ttu-id="7bb24-105">虽然 NuGet.org 最广为已知和已用存储库，有许多地方会发布 NuGet 包：</span><span class="sxs-lookup"><span data-stu-id="7bb24-105">While NuGet.org is the most widely known and used repository, there are many places to publish NuGet packages:</span></span>

* <span data-ttu-id="7bb24-106">**[NuGet.org](https://www.nuget.org/)** 是 NuGet 包的主联机存储库。</span><span class="sxs-lookup"><span data-stu-id="7bb24-106">**[NuGet.org](https://www.nuget.org/)** is the primary online repository for NuGet packages.</span></span> <span data-ttu-id="7bb24-107">在 NuGet.org 上的所有包都都向每个人都使用公开提供。</span><span class="sxs-lookup"><span data-stu-id="7bb24-107">All packages on NuGet.org are publicly available to everyone.</span></span> <span data-ttu-id="7bb24-108">默认情况下，Visual Studio NuGet.org 作为包源，因此很多开发人员 NuGet.org 它们将与之交互的唯一包存储库。</span><span class="sxs-lookup"><span data-stu-id="7bb24-108">By default, Visual Studio has NuGet.org as a package source and for many developers NuGet.org is the only package repository they'll interact with.</span></span> <span data-ttu-id="7bb24-109">NuGet.org 是发布稳定的包和预发行包上所需社区反馈的最佳位置。</span><span class="sxs-lookup"><span data-stu-id="7bb24-109">NuGet.org is the best place to publish stable packages and pre-release packages that you want community feedback on.</span></span>

* <span data-ttu-id="7bb24-110">**[MyGet](https://myget.org/)** 存储库服务支持[可用的自定义包源的开放源代码项目](https://www.myget.org/opensource)。</span><span class="sxs-lookup"><span data-stu-id="7bb24-110">**[MyGet](https://myget.org/)** repository service supports [free custom package feeds for open-source projects](https://www.myget.org/opensource).</span></span> <span data-ttu-id="7bb24-111">MyGet 公共自定义源是一个理想位置用于发布所创建的 CI 服务的预发行包。</span><span class="sxs-lookup"><span data-stu-id="7bb24-111">A MyGet public custom feed is an ideal place to publish pre-release packages created by your CI service.</span></span> <span data-ttu-id="7bb24-112">MyGet 还许可后出于商业目的提供了专用源。</span><span class="sxs-lookup"><span data-stu-id="7bb24-112">MyGet also provides private feeds commercially.</span></span>

* <span data-ttu-id="7bb24-113">一个**[本地数据源](/nuget/hosting-packages/local-feeds)** 使您可以将包存储库等的文件夹，并使`*.nupkg`nuget 的可访问文件夹中的文件。</span><span class="sxs-lookup"><span data-stu-id="7bb24-113">A **[local feed](/nuget/hosting-packages/local-feeds)** allows you to treat a folder like a package repository and makes the `*.nupkg` files in the folder accessible by NuGet.</span></span> <span data-ttu-id="7bb24-114">本地数据源可用于测试之前将其发布到 NuGet.org 的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="7bb24-114">A local feed is useful for testing a NuGet package before publishing it to NuGet.org.</span></span>

> [!NOTE]
> <span data-ttu-id="7bb24-115">NuGet.org[不允许要删除的包](/nuget/policies/deleting-packages)是上传。</span><span class="sxs-lookup"><span data-stu-id="7bb24-115">NuGet.org [does not allow a package to be deleted](/nuget/policies/deleting-packages) once it is uploaded.</span></span> <span data-ttu-id="7bb24-116">包可以是未列出，以便它不是在 UI 中公开可见，但`*.nupkg`仍可还原上下载。</span><span class="sxs-lookup"><span data-stu-id="7bb24-116">A package can be unlisted so that it is not publicly visible in the UI but the `*.nupkg` can still be downloaded on restore.</span></span> <span data-ttu-id="7bb24-117">此外，nuget.org 不允许重复的包版本。</span><span class="sxs-lookup"><span data-stu-id="7bb24-117">Also, nuget.org does not allow duplicate package versions.</span></span> <span data-ttu-id="7bb24-118">若要更正的错误必须取消列出包不正确的 NuGet 包，递增的版本号和发布包的新版本。</span><span class="sxs-lookup"><span data-stu-id="7bb24-118">To correct a NuGet package with an error you have to unlist the incorrect package, increment the version number and publish a new version of the package.</span></span>

<span data-ttu-id="7bb24-119">**执行 ✔️** [发布稳定的包和预发行包](/nuget/create-packages/publish-a-package)想到 NuGet.org 的社区反馈。</span><span class="sxs-lookup"><span data-stu-id="7bb24-119">**✔️ DO** [publish stable packages and pre-release packages](/nuget/create-packages/publish-a-package) you want community feedback on to NuGet.org.</span></span>

<span data-ttu-id="7bb24-120">**请考虑 ✔️**预发行包发布到 MyGet 源从持续集成生成。</span><span class="sxs-lookup"><span data-stu-id="7bb24-120">**✔️ CONSIDER** publishing pre-release packages to a MyGet feed from a continuous integration build.</span></span>

<span data-ttu-id="7bb24-121">**请考虑 ✔️**使用本地数据源或 MyGet 在开发环境中测试包。</span><span class="sxs-lookup"><span data-stu-id="7bb24-121">**✔️ CONSIDER** testing packages in your development environment using a local feed or MyGet.</span></span> <span data-ttu-id="7bb24-122">请检查包的工作原理，然后将其发布到 NuGet.org。</span><span class="sxs-lookup"><span data-stu-id="7bb24-122">Check the package works then publish it to NuGet.org.</span></span>

## <a name="nugetorg-security"></a><span data-ttu-id="7bb24-123">NuGet.org 安全</span><span class="sxs-lookup"><span data-stu-id="7bb24-123">NuGet.org security</span></span>

<span data-ttu-id="7bb24-124">务必不良参与方无法访问你的 NuGet 帐户并上传恶意版本的库。</span><span class="sxs-lookup"><span data-stu-id="7bb24-124">It's important that bad actors can't access your NuGet account and upload a malicious version of your library.</span></span> <span data-ttu-id="7bb24-125">发布包时，NuGet.org 将提供双因素身份验证和电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="7bb24-125">NuGet.org offers two-factor authentication and email notifications when a package is published.</span></span> <span data-ttu-id="7bb24-126">在登录到 NuGet.org 后启用这些功能**帐户设置**页。</span><span class="sxs-lookup"><span data-stu-id="7bb24-126">Enable these features after logging into NuGet.org on the **Account settings** page.</span></span>

<span data-ttu-id="7bb24-127">![替换文字](./media/publish-nuget-package/nuget-2fa.png "NuGet 帐户安全")</span><span class="sxs-lookup"><span data-stu-id="7bb24-127">![alt text](./media/publish-nuget-package/nuget-2fa.png "NuGet Account Security")</span></span>

<span data-ttu-id="7bb24-128">**✔️ 执行**使用 Microsoft 帐户登录到 NuGet。</span><span class="sxs-lookup"><span data-stu-id="7bb24-128">**✔️ DO** use a Microsoft account to sign in to NuGet.</span></span>

<span data-ttu-id="7bb24-129">**✔️ 执行**启用双因素身份验证用于访问 NuGet。</span><span class="sxs-lookup"><span data-stu-id="7bb24-129">**✔️ DO** enable two-factor authentication for accessing NuGet.</span></span>

<span data-ttu-id="7bb24-130">**✔️ 执行**发布包时启用电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="7bb24-130">**✔️ DO** enable email notification when a package is published.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="7bb24-131">[上一页](./sourcelink.md)
[下一页](./versioning.md)</span><span class="sxs-lookup"><span data-stu-id="7bb24-131">[Previous](./sourcelink.md)
[Next](./versioning.md)</span></span>
