---
title: Windows 窗体的 ClickOnce 部署
ms.date: 03/30/2017
helpviewer_keywords:
- ClickOnce deployment [Windows Forms]
- Windows Forms, ClickOnce deployment
- walkthroughs [Windows Forms], ClickOnce deployment
ms.assetid: 1451fce9-1965-4a03-b4d3-831b5fe4ad66
ms.openlocfilehash: a9721b7e13c24af6256d692fef879b08f2858a68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="clickonce-deployment-for-windows-forms"></a><span data-ttu-id="327be-102">Windows 窗体的 ClickOnce 部署</span><span class="sxs-lookup"><span data-stu-id="327be-102">ClickOnce Deployment for Windows Forms</span></span>
<span data-ttu-id="327be-103">下面的主题描述了 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]，这是一种用于将 Windows 窗体应用程序轻松部署到客户端计算机的技术。</span><span class="sxs-lookup"><span data-stu-id="327be-103">The following topics describe [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)], a technology used for easily deploying Windows Forms applications to client computers.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="327be-104">相关章节</span><span class="sxs-lookup"><span data-stu-id="327be-104">Related Sections</span></span>  
 [<span data-ttu-id="327be-105">选择 ClickOnce 部署策略</span><span class="sxs-lookup"><span data-stu-id="327be-105">Choosing a ClickOnce Deployment Strategy</span></span>](/visualstudio/deployment/choosing-a-clickonce-deployment-strategy)  
 <span data-ttu-id="327be-106">演示用于部署 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 应用程序的若干选项。</span><span class="sxs-lookup"><span data-stu-id="327be-106">Presents several options for deploying [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] applications.</span></span>  
  
 [<span data-ttu-id="327be-107">选择 ClickOnce 更新策略</span><span class="sxs-lookup"><span data-stu-id="327be-107">Choosing a ClickOnce Update Strategy</span></span>](/visualstudio/deployment/choosing-a-clickonce-update-strategy)  
 <span data-ttu-id="327be-108">演示用于更新 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 应用程序的若干选项。</span><span class="sxs-lookup"><span data-stu-id="327be-108">Presents several options for updating [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] applications.</span></span>  
  
 [<span data-ttu-id="327be-109">保护 ClickOnce 应用程序</span><span class="sxs-lookup"><span data-stu-id="327be-109">Securing ClickOnce Applications</span></span>](/visualstudio/deployment/securing-clickonce-applications)  
 <span data-ttu-id="327be-110">解释 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 部署的安全问题。</span><span class="sxs-lookup"><span data-stu-id="327be-110">Explains the security implications of [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] deployment.</span></span>  
  
 [<span data-ttu-id="327be-111">ClickOnce 部署疑难解答</span><span class="sxs-lookup"><span data-stu-id="327be-111">Troubleshooting ClickOnce Deployments</span></span>](/visualstudio/deployment/troubleshooting-clickonce-deployments)  
 <span data-ttu-id="327be-112">描述在部署 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 应用程序时可能发生的各种问题，并记录 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 可能生成的顶级错误消息。</span><span class="sxs-lookup"><span data-stu-id="327be-112">Describes various problems that can occur when deploying [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] applications, and documents the top-level error messages that [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] might generate.</span></span>  
  
 [<span data-ttu-id="327be-113">ClickOnce 和应用程序设置</span><span class="sxs-lookup"><span data-stu-id="327be-113">ClickOnce and Application Settings</span></span>](/visualstudio/deployment/clickonce-and-application-settings)  
 <span data-ttu-id="327be-114">描述 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 部署如何使用应用程序设置，从而存储应用程序和用户设置以便未来检索。</span><span class="sxs-lookup"><span data-stu-id="327be-114">Describes how [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] deployment works with application settings, which stores application and user settings for future retrieval.</span></span>  
  
 [<span data-ttu-id="327be-115">受信任的应用程序部署概述</span><span class="sxs-lookup"><span data-stu-id="327be-115">Trusted Application Deployment Overview</span></span>](/visualstudio/deployment/trusted-application-deployment-overview)  
 <span data-ttu-id="327be-116">描述一项 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 功能，该功能允许受信任的应用程序在客户端计算机上以更高级别的权限运行。</span><span class="sxs-lookup"><span data-stu-id="327be-116">Describes a [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] feature that allows trusted applications to run with a higher level of permission on client computers.</span></span>  
  
 [<span data-ttu-id="327be-117">ClickOnce 和 Authenticode</span><span class="sxs-lookup"><span data-stu-id="327be-117">ClickOnce and Authenticode</span></span>](/visualstudio/deployment/clickonce-and-authenticode)  
 <span data-ttu-id="327be-118">描述如何在受信任的应用程序部署中使用验证码技术。</span><span class="sxs-lookup"><span data-stu-id="327be-118">Describes how Authenticode technology is used in trusted application deployment.</span></span>  
  
 [<span data-ttu-id="327be-119">演练：手动部署 ClickOnce 应用程序</span><span class="sxs-lookup"><span data-stu-id="327be-119">Walkthrough: Manually Deploying a ClickOnce Application</span></span>](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)  
 <span data-ttu-id="327be-120">演示如何使用命令行和 SDK 工具（而不使用 Visual Studio）来部署 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 应用程序。</span><span class="sxs-lookup"><span data-stu-id="327be-120">Demonstrates using command-line and SDK tools to deploy a [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] application without using Visual Studio.</span></span>  
  
 [<span data-ttu-id="327be-121">如何：为 ClickOnce 应用程序向客户端计算机添加一个受信任的发布者</span><span class="sxs-lookup"><span data-stu-id="327be-121">How to: Add a Trusted Publisher to a Client Computer for ClickOnce Applications</span></span>](/visualstudio/deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications)  
 <span data-ttu-id="327be-122">演示如何一次性配置受信任的应用程序部署所需要的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="327be-122">Demonstrates the one-time configuration of client computers required for trusted application deployment.</span></span>  
  
 [<span data-ttu-id="327be-123">如何：指定部署更新的其他位置</span><span class="sxs-lookup"><span data-stu-id="327be-123">How to: Specify an Alternate Location for Deployment Updates</span></span>](/visualstudio/deployment/how-to-specify-an-alternate-location-for-deployment-updates)  
 <span data-ttu-id="327be-124">演示如何使用 SDK 工具来配置 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 应用程序，以检查另一个用于新版本应用程序的位置。</span><span class="sxs-lookup"><span data-stu-id="327be-124">Demonstrates configuring a [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] application, using SDK tools, to check a different location for new versions of an application.</span></span>  
  
 [<span data-ttu-id="327be-125">演练：使用 ClickOnce 部署 API 按需下载程序集</span><span class="sxs-lookup"><span data-stu-id="327be-125">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api)  
 <span data-ttu-id="327be-126">演示如何在应用程序第一次尝试加载程序集时使用 API 调用来检索程序集。</span><span class="sxs-lookup"><span data-stu-id="327be-126">Demonstrates using API calls to retrieve an assembly the first time your application attempts to load it.</span></span>  
  
 [<span data-ttu-id="327be-127">如何：在联机 ClickOnce 应用程序中检索查询字符串信息</span><span class="sxs-lookup"><span data-stu-id="327be-127">How to: Retrieve Query String Information in an Online ClickOnce Application</span></span>](/visualstudio/deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application)  
 <span data-ttu-id="327be-128">演示如何从 URL 检索用于运行 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 应用程序的参数。</span><span class="sxs-lookup"><span data-stu-id="327be-128">Demonstrates retrieving parameters from the URL used to run a [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] application.</span></span>  
  
 [<span data-ttu-id="327be-129">ClickOnce 缓存概述</span><span class="sxs-lookup"><span data-stu-id="327be-129">ClickOnce Cache Overview</span></span>](/visualstudio/deployment/clickonce-cache-overview)  
 <span data-ttu-id="327be-130">描述用于在本地计算机上存储 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 应用程序的缓存。</span><span class="sxs-lookup"><span data-stu-id="327be-130">Describes the cache used to store [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] applications on the local computer.</span></span>  
  
 [<span data-ttu-id="327be-131">在 ClickOnce 应用程序中访问本地数据和远程数据</span><span class="sxs-lookup"><span data-stu-id="327be-131">Accessing Local and Remote Data in ClickOnce Applications</span></span>](/visualstudio/deployment/accessing-local-and-remote-data-in-clickonce-applications)  
 <span data-ttu-id="327be-132">介绍如何从 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 应用程序访问本地数据文件和远程数据源。</span><span class="sxs-lookup"><span data-stu-id="327be-132">Describes how to access local data files and remote data sources from a [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] application.</span></span>  
  
 [<span data-ttu-id="327be-133">如何：将数据文件包括到 ClickOnce 应用程序中</span><span class="sxs-lookup"><span data-stu-id="327be-133">How to: Include a Data File in a ClickOnce Application</span></span>](/visualstudio/deployment/how-to-include-a-data-file-in-a-clickonce-application)  
 <span data-ttu-id="327be-134">演示如何标记文件以使它在 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 数据目录中可用。</span><span class="sxs-lookup"><span data-stu-id="327be-134">Demonstrates how to mark a file so that it is available in the [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] data directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="327be-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="327be-135">See Also</span></span>  
 [<span data-ttu-id="327be-136">应用程序设置概述</span><span class="sxs-lookup"><span data-stu-id="327be-136">Application Settings Overview</span></span>](../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [<span data-ttu-id="327be-137">发布 ClickOnce 应用程序</span><span class="sxs-lookup"><span data-stu-id="327be-137">Publishing ClickOnce Applications</span></span>](/visualstudio/deployment/publishing-clickonce-applications)  
 [<span data-ttu-id="327be-138">从命令行生成 ClickOnce 应用程序</span><span class="sxs-lookup"><span data-stu-id="327be-138">Building ClickOnce Applications from the Command Line</span></span>](/visualstudio/deployment/building-clickonce-applications-from-the-command-line)  
 [<span data-ttu-id="327be-139">调试使用 System.Deployment.Application 的 ClickOnce 应用程序</span><span class="sxs-lookup"><span data-stu-id="327be-139">Debugging ClickOnce Applications That Use System.Deployment.Application</span></span>](http://msdn.microsoft.com/library/86f31948-2ca8-47c0-8e8b-c2b817bbf79f)  
 [<span data-ttu-id="327be-140">使用 ClickOnce 部署 COM 组件</span><span class="sxs-lookup"><span data-stu-id="327be-140">Deploying COM Components with ClickOnce</span></span>](/visualstudio/deployment/deploying-com-components-with-clickonce)  
 [<span data-ttu-id="327be-141">如何：使用发布向导发布 ClickOnce 应用程序</span><span class="sxs-lookup"><span data-stu-id="327be-141">How to: Publish a ClickOnce Application using the Publish Wizard</span></span>](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)
