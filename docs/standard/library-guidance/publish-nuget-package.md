---
title: 发布 NuGet 包
description: 将 .NET 库发布到 NuGet 的最佳做法建议。
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 9c8442b52ed2c54d2fb3368a2e886c5fc2b19148
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65640778"
---
# <a name="publishing-a-nuget-package"></a><span data-ttu-id="bb1f6-103">发布 NuGet 包</span><span class="sxs-lookup"><span data-stu-id="bb1f6-103">Publishing a NuGet package</span></span>

<span data-ttu-id="bb1f6-104">从包存储库发布和使用 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-104">NuGet packages are published and consumed from package repositories.</span></span> <span data-ttu-id="bb1f6-105">虽然 NuGet.org 是最广为人知和使用范围最广的存储库，但有很多平台可以发布 NuGet 包：</span><span class="sxs-lookup"><span data-stu-id="bb1f6-105">While NuGet.org is the most widely known and used repository, there are many places to publish NuGet packages:</span></span>

* <span data-ttu-id="bb1f6-106">[NuGet.org](https://www.nuget.org/) 是 NuGet 包的主要联机存储库。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-106">**[NuGet.org](https://www.nuget.org/)** is the primary online repository for NuGet packages.</span></span> <span data-ttu-id="bb1f6-107">NuGet.org 上的所有包是向所有用户公开提供的。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-107">All packages on NuGet.org are publicly available to everyone.</span></span> <span data-ttu-id="bb1f6-108">默认情况下，Visual Studio 将 NuGet.org 作为包源，并且对于许多开发人员来说，NuGet.org 是他们与之交互的唯一包存储库。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-108">By default, Visual Studio has NuGet.org as a package source and for many developers NuGet.org is the only package repository they'll interact with.</span></span> <span data-ttu-id="bb1f6-109">NuGet.org 是发布想要获得社区反馈的稳定包和预发行包的最佳位置。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-109">NuGet.org is the best place to publish stable packages and pre-release packages that you want community feedback on.</span></span>

* <span data-ttu-id="bb1f6-110">[MyGet](https://myget.org/) 是支持开源项目的自定义包源的存储库服务。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-110">**[MyGet](https://myget.org/)** is a repository service that supports custom package feeds for open-source projects.</span></span> <span data-ttu-id="bb1f6-111">MyGet 公共自定义源是发布由你的 CI 服务创建的预发行包的理想位置。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-111">A MyGet public custom feed is an ideal place to publish pre-release packages created by your CI service.</span></span> <span data-ttu-id="bb1f6-112">MyGet 还提供用于商业目的的专用源。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-112">MyGet also provides private feeds commercially.</span></span>

* <span data-ttu-id="bb1f6-113">[本地源](/nuget/hosting-packages/local-feeds)使你能够将文件夹视为包存储库并使文件夹中的 `*.nupkg` 文件可由 NuGet 访问。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-113">A **[local feed](/nuget/hosting-packages/local-feeds)** allows you to treat a folder like a package repository and makes the `*.nupkg` files in the folder accessible by NuGet.</span></span> <span data-ttu-id="bb1f6-114">本地源可用于在将 NuGet 发布到 MyGet.org 前对 NuGet 包进行测试。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-114">A local feed is useful for testing a NuGet package before publishing it to NuGet.org.</span></span>

> [!NOTE]
> <span data-ttu-id="bb1f6-115">上传包后，NuGet.org [不允许将其删除](/nuget/policies/deleting-packages)。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-115">NuGet.org [does not allow a package to be deleted](/nuget/policies/deleting-packages) once it is uploaded.</span></span> <span data-ttu-id="bb1f6-116">可以不列出包，使其不在 UI 中公开可见，但仍可在还原后下载 `*.nupkg`。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-116">A package can be unlisted so that it is not publicly visible in the UI but the `*.nupkg` can still be downloaded on restore.</span></span> <span data-ttu-id="bb1f6-117">此外，nuget.org 不允许重复的包版本。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-117">Also, nuget.org does not allow duplicate package versions.</span></span> <span data-ttu-id="bb1f6-118">若要更正存在错误的 NuGet 包，必须取消列出不正确的包，递增版本号并发布新版本的包。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-118">To correct a NuGet package with an error you have to unlist the incorrect package, increment the version number and publish a new version of the package.</span></span>

<span data-ttu-id="bb1f6-119">✔️ 务必[将想要获取社区反馈的稳定包和预发行包发布](/nuget/create-packages/publish-a-package)到 NuGet.org。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-119">**✔️ DO** [publish stable packages and pre-release packages](/nuget/create-packages/publish-a-package) you want community feedback on to NuGet.org.</span></span>

<span data-ttu-id="bb1f6-120">✔️ 请考虑将预发行包从持续集成版本发布到 MyGet 源。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-120">**✔️ CONSIDER** publishing pre-release packages to a MyGet feed from a continuous integration build.</span></span>

<span data-ttu-id="bb1f6-121">✔️ 请考虑使用本地源或 MyGet 在开发环境中测试包。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-121">**✔️ CONSIDER** testing packages in your development environment using a local feed or MyGet.</span></span> <span data-ttu-id="bb1f6-122">检查包是否运行正常，然后将其发布到 NuGet.org。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-122">Check the package works then publish it to NuGet.org.</span></span>

## <a name="nugetorg-security"></a><span data-ttu-id="bb1f6-123">NuGet.org 安全</span><span class="sxs-lookup"><span data-stu-id="bb1f6-123">NuGet.org security</span></span>

<span data-ttu-id="bb1f6-124">不良因素不能访问 NuGet 帐户且不能上传库的恶意版本，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-124">It's important that bad actors can't access your NuGet account and upload a malicious version of your library.</span></span> <span data-ttu-id="bb1f6-125">NuGet.org 在发布包时提供双因素身份验证和电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-125">NuGet.org offers two-factor authentication and email notifications when a package is published.</span></span> <span data-ttu-id="bb1f6-126">登录到“帐户设置”页面上的 NuGet.org 后，启用这些功能。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-126">Enable these features after logging into NuGet.org on the **Account settings** page.</span></span>

<span data-ttu-id="bb1f6-127">![替换文本](./media/publish-nuget-package/nuget-2fa.png "NuGet 帐户安全")</span><span class="sxs-lookup"><span data-stu-id="bb1f6-127">![alt text](./media/publish-nuget-package/nuget-2fa.png "NuGet Account Security")</span></span>

<span data-ttu-id="bb1f6-128">✔️ 务必使用 Microsoft 帐户登录到 NuGet。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-128">**✔️ DO** use a Microsoft account to sign in to NuGet.</span></span>

<span data-ttu-id="bb1f6-129">✔️ 务必启用双因素身份验证来访问 NuGet。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-129">**✔️ DO** enable two-factor authentication for accessing NuGet.</span></span>

<span data-ttu-id="bb1f6-130">✔️ 务必在发布包时启用电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="bb1f6-130">**✔️ DO** enable email notification when a package is published.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bb1f6-131">[上一页](sourcelink.md)
>[下一页](versioning.md)</span><span class="sxs-lookup"><span data-stu-id="bb1f6-131">[Previous](sourcelink.md)
[Next](versioning.md)</span></span>
