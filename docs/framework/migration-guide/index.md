---
title: '.NET Framework 4.7、4.6 和 4.5 的迁移指南 '
ms.custom: updateeachrelease
ms.date: 04/10/2018
helpviewer_keywords:
- .NET Framework, migrating applications to
- migration, .NET Framework
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f8ef6d73aa6cd044cf6808878bf6142a735d015c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="migration-guide-to-the-net-framework-47-46-and-45"></a><span data-ttu-id="a4c65-102">.NET Framework 4.7、4.6 和 4.5 的迁移指南</span><span class="sxs-lookup"><span data-stu-id="a4c65-102">Migration Guide to the .NET Framework 4.7, 4.6, and 4.5</span></span> 
<span data-ttu-id="a4c65-103">如果使用之前版本的 .NET Framework 创建了应用，通常可以轻松地将它升级为 .NET Framework 4.5 及其子版本（4.5.1 和 4.5.2）、.NET Framework 4.6 及其子版本（4.6.1 和 4.6.2）或者 .NET Framework 4.7 及其子版本（4.7.1 和 4.7.2）。</span><span class="sxs-lookup"><span data-stu-id="a4c65-103">If you created your app using an earlier version of the .NET Framework, you can generally upgrade it to the .NET Framework 4.5 and its point releases (4.5.1 and 4.5.2), the .NET Framework 4.6 and its point releases (4.6.1 and 4.6.2), or the .NET Framework 4.7 and its point releases (4.7.1 and 4.7.2) easily.</span></span> <span data-ttu-id="a4c65-104">在 Visual Studio 中打开项目。</span><span class="sxs-lookup"><span data-stu-id="a4c65-104">Open your project in Visual Studio.</span></span> <span data-ttu-id="a4c65-105">如果项目是在之前版本的 Visual Studio 中创建的，则会自动打开“项目兼容性”对话框。</span><span class="sxs-lookup"><span data-stu-id="a4c65-105">If your project was created in an earlier version of Visual Studio, the **Project Compatibility** dialog box automatically opens.</span></span> <span data-ttu-id="a4c65-106">有关在 Visual Studio 中升级项目的详细信息，请参阅[移植、迁移和升级 Visual Studio 项目](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects)和 [Visual Studio 2017 平台目标以及兼容性](/visualstudio/productinfo/vs2017-compatibility-vs)。</span><span class="sxs-lookup"><span data-stu-id="a4c65-106">For more information about upgrading a project in Visual Studio, see [Port, Migrate, and Upgrade Visual Studio Projects](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects) and [Visual Studio 2017 Platform Targeting and Compatibility](/visualstudio/productinfo/vs2017-compatibility-vs).</span></span>  
  
 <span data-ttu-id="a4c65-107">但是，.NET Framework 中的某些更改需要更改你的代码。</span><span class="sxs-lookup"><span data-stu-id="a4c65-107">However, some changes in the .NET Framework require changes to your code.</span></span> <span data-ttu-id="a4c65-108">也可利用 .NET Framework 4.5 及其子版本、.NET Framework 4.6 及其子版本或 .NET Framework 4.7 及其子版本中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="a4c65-108">You may also want to take advantage of functionality that is new in the .NET Framework 4.5 and its point releases, in the .NET Framework 4.6 and its point releases, or in the .NET Framework 4.7 and its point releases.</span></span> <span data-ttu-id="a4c65-109">通常，针对新版本的 .NET Framework 来对应用进行这些类型的更改的过程称作“迁移”。</span><span class="sxs-lookup"><span data-stu-id="a4c65-109">Making these types of changes to your app for a new version of the .NET Framework is typically referred to as *migration*.</span></span> <span data-ttu-id="a4c65-110">如果不需要迁移应用，可以在 .NET Framework 4.5 或更高版本中运行此应用，无需对其进行重新编译。</span><span class="sxs-lookup"><span data-stu-id="a4c65-110">If your app doesn't have to be migrated, you can run it in the .NET Framework 4.5 or a later version without recompiling it.</span></span>  
  
## <a name="migration-resources"></a><span data-ttu-id="a4c65-111">迁移资源</span><span class="sxs-lookup"><span data-stu-id="a4c65-111">Migration resources</span></span>  
 <span data-ttu-id="a4c65-112">将应用从之前版本的 .NET Framework 迁移到 4.5、4.5.1、4.5.2、4.6、4.6.1、4.6.2、4.7、4.7.1 或 4.7.2 之前，需查看下列文档：</span><span class="sxs-lookup"><span data-stu-id="a4c65-112">Review the following documents before you migrate your app from earlier versions of the .NET Framework to version 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, or 4.7.2:</span></span>  
  
-   <span data-ttu-id="a4c65-113">请参阅[版本和依赖关系](../../../docs/framework/migration-guide/versions-and-dependencies.md)以了解作为每个 .NET Framework 版本基础的 CLR 版本，并查看成功设定应用目标的指南。</span><span class="sxs-lookup"><span data-stu-id="a4c65-113">See [Versions and Dependencies](../../../docs/framework/migration-guide/versions-and-dependencies.md) to understand the CLR version underlying each version of the .NET Framework and to review guidelines for targeting your apps successfully.</span></span>  
  
-   <span data-ttu-id="a4c65-114">查看[应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility.md)以了解可能影响应用的运行时和重定目标更改以及如何处理这些更改。</span><span class="sxs-lookup"><span data-stu-id="a4c65-114">Review [Application Compatibility](../../../docs/framework/migration-guide/application-compatibility.md) to find out about runtime and retargeting changes that might affect your app and how to handle them.</span></span>  
  
-   <span data-ttu-id="a4c65-115">查看[类库中过时的内容](../../../docs/framework/whats-new/whats-obsolete.md)以确定代码中已过时的任何类型或成员以及建议的备选项。</span><span class="sxs-lookup"><span data-stu-id="a4c65-115">Review [What's Obsolete in the Class Library](../../../docs/framework/whats-new/whats-obsolete.md) to determine any types or members in your code that have been made obsolete, and the recommended alternatives.</span></span>  
  
-   <span data-ttu-id="a4c65-116">查看[新增功能](../../../docs/framework/whats-new/index.md)以了解可能需要向应用添加的新功能的说明。</span><span class="sxs-lookup"><span data-stu-id="a4c65-116">See [What's New](../../../docs/framework/whats-new/index.md) for descriptions of new features that you may want to add to your app.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4c65-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4c65-117">See Also</span></span>  
 [<span data-ttu-id="a4c65-118">应用程序兼容性</span><span class="sxs-lookup"><span data-stu-id="a4c65-118">Application Compatibility</span></span>](../../../docs/framework/migration-guide/application-compatibility.md)  
 [<span data-ttu-id="a4c65-119">从 .NET Framework 1.1 迁移</span><span class="sxs-lookup"><span data-stu-id="a4c65-119">Migrating from the .NET Framework 1.1</span></span>](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)  
 [<span data-ttu-id="a4c65-120">版本兼容性</span><span class="sxs-lookup"><span data-stu-id="a4c65-120">Version Compatibility</span></span>](../../../docs/framework/migration-guide/version-compatibility.md)  
 [<span data-ttu-id="a4c65-121">版本和依赖关系</span><span class="sxs-lookup"><span data-stu-id="a4c65-121">Versions and Dependencies</span></span>](../../../docs/framework/migration-guide/versions-and-dependencies.md)  
 [<span data-ttu-id="a4c65-122">如何：将应用程序配置为支持 .NET Framework 4 或 4.5</span><span class="sxs-lookup"><span data-stu-id="a4c65-122">How to: Configure an App to Support .NET Framework 4 or 4.5</span></span>](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)  
 [<span data-ttu-id="a4c65-123">新增功能</span><span class="sxs-lookup"><span data-stu-id="a4c65-123">What's New</span></span>](../../../docs/framework/whats-new/index.md)  
 [<span data-ttu-id="a4c65-124">类库中过时的内容</span><span class="sxs-lookup"><span data-stu-id="a4c65-124">What's Obsolete in the Class Library</span></span>](../../../docs/framework/whats-new/whats-obsolete.md)  
 [<span data-ttu-id="a4c65-125">.NET Framework 版本和程序集信息</span><span class="sxs-lookup"><span data-stu-id="a4c65-125">.NET Framework Version and Assembly Information</span></span>](http://go.microsoft.com/fwlink/?LinkId=201701)  
 <span data-ttu-id="a4c65-126">[Microsoft .NET Framework 支持生命周期策略](http://go.microsoft.com/fwlink/?LinkId=196607) [.NET Framework 4 迁移问题](net-framework-4-migration-issues.md)</span><span class="sxs-lookup"><span data-stu-id="a4c65-126">[Microsoft .NET Framework Support Lifecycle Policy](http://go.microsoft.com/fwlink/?LinkId=196607) [.NET Framework 4 migration issues](net-framework-4-migration-issues.md)</span></span>
