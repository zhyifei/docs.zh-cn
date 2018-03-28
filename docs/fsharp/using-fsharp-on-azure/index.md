---
title: 在 Azure 上使用 F#
description: '使用 F # 使用 Azure 服务指南'
keywords: Azure, 云, visual f#, f#, 函数编程, .NET, .NET Core
author: sylvanc
ms.author: phcart
ms.date: 09/22/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: FAD4D11E-703A-42D4-9F72-893D9E0F569B
ms.openlocfilehash: 0849bc77139b4f4383e2c772f5bae62741ee2b8b
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="using-f-on-azure"></a><span data-ttu-id="59f56-104">在 Azure 上使用 F#</span><span class="sxs-lookup"><span data-stu-id="59f56-104">Using F# on Azure</span></span>

<span data-ttu-id="59f56-105">F# 是一种出色的云编程语言，常用于编写 Web 应用程序、云服务、云托管微服务，也可用于可缩放数据处理。</span><span class="sxs-lookup"><span data-stu-id="59f56-105">F# is a superb language for cloud programming and is frequently used to write web applications, cloud services, cloud-hosted microservices, and for scalable data processing.</span></span>

<span data-ttu-id="59f56-106">在以下部分中，你将发现如何结合使用 F# 与一系列 Azure 服务的相关资源。</span><span class="sxs-lookup"><span data-stu-id="59f56-106">In the following sections, you will find resources on how to use a range of Azure services with F#.</span></span>

> [!NOTE]
> <span data-ttu-id="59f56-107">如果某特定 Azure 服务不在此文档集中，请参阅适用于该服务的 Azure Functions 或 .NET 文档。</span><span class="sxs-lookup"><span data-stu-id="59f56-107">If a particular Azure service isn't in this documentation set, please consult either the Azure Functions or .NET documentation for that service.</span></span> <span data-ttu-id="59f56-108">某些 Azure 服务独立于语言，不需要任何特定于语言的文档，未在此处列出。</span><span class="sxs-lookup"><span data-stu-id="59f56-108">Some Azure services are language-independent and require no language-specific documentation and are not listed here.</span></span>

## <a name="using-azure-virtual-machines-with-f"></a><span data-ttu-id="59f56-109">使用 F # 使用 Azure 虚拟机</span><span class="sxs-lookup"><span data-stu-id="59f56-109">Using Azure Virtual Machines with F#</span></span> #

<span data-ttu-id="59f56-110">Azure 支持各种不同的虚拟机 (VM) 配置，请参阅 [Linux 和 Azure 虚拟机](https://azure.microsoft.com/services/virtual-machines/)。</span><span class="sxs-lookup"><span data-stu-id="59f56-110">Azure supports a wide range of virtual machine (VM) configurations, see [Linux and Azure Virtual Machines](https://azure.microsoft.com/services/virtual-machines/).</span></span>

<span data-ttu-id="59f56-111">若要在虚拟机上安装 F# 用来执行、编译和/或编写脚本，请参阅[在 Linux 上使用 F#](http://fsharp.org/use/linux) 和[在 Windows 上使用 F#](http://fsharp.org/use/windows)。</span><span class="sxs-lookup"><span data-stu-id="59f56-111">To install F# on a virtual machine for execution, compilation and/or scripting see [Using F# on Linux](http://fsharp.org/use/linux) and [Using F# on Windows](http://fsharp.org/use/windows).</span></span>


## <a name="using-azure-functions-with-f"></a><span data-ttu-id="59f56-112">使用 F # 使用 Azure 函数</span><span class="sxs-lookup"><span data-stu-id="59f56-112">Using Azure Functions with F#</span></span> #

<span data-ttu-id="59f56-113">[Azure Functions](https://azure.microsoft.com/services/functions/) 是一个在云中轻松运行小代码段或“函数”的解决方案。</span><span class="sxs-lookup"><span data-stu-id="59f56-113">[Azure Functions](https://azure.microsoft.com/services/functions/) is a solution for easily running small pieces of code, or "functions," in the cloud.</span></span> <span data-ttu-id="59f56-114">可针对手头的问题编写所需代码，无需担心用来运行该代码的完整应用程序或基础结构。</span><span class="sxs-lookup"><span data-stu-id="59f56-114">You can write just the code you need for the problem at hand, without worrying about a whole application or the infrastructure to run it.</span></span> <span data-ttu-id="59f56-115">函数连接到 Azure 存储和其他云托管资源中的事件。</span><span class="sxs-lookup"><span data-stu-id="59f56-115">Your functions are connected to events in Azure storage and other cloud-hosted resources.</span></span> <span data-ttu-id="59f56-116">数据通过函数参数流入 F# 函数。</span><span class="sxs-lookup"><span data-stu-id="59f56-116">Data flows into your F# functions via function arguments.</span></span> <span data-ttu-id="59f56-117">可以使用所选择的开发语言，信任 Azure 按需进行扩展。</span><span class="sxs-lookup"><span data-stu-id="59f56-117">You can use your development language of choice, trusting Azure to scale as needed.</span></span>

<span data-ttu-id="59f56-118">Azure Functions 支持 F# 作为第一类语言，它执行 F# 代码时高效、反应迅速且可缩放。</span><span class="sxs-lookup"><span data-stu-id="59f56-118">Azure Functions support F# as a first-class language with efficient, reactive, scalable execution of F# code.</span></span> <span data-ttu-id="59f56-119">请参阅 [Azure Functions F# 开发人员参考](/azure/azure-functions/functions-reference-fsharp)，了解如何将 F# 用于 Azure Functions 的相关参考文档。</span><span class="sxs-lookup"><span data-stu-id="59f56-119">See the [Azure Functions F# Developer Reference](/azure/azure-functions/functions-reference-fsharp) for reference documentation on how to use F# with Azure Functions.</span></span>

<span data-ttu-id="59f56-120">结合使用 Azure Functions 和 F# 的其他资源：</span><span class="sxs-lookup"><span data-stu-id="59f56-120">Other resources for using Azure Functions and F#:</span></span>

* <span data-ttu-id="59f56-121">[Scale Up Azure Functions in F# Using Suave](https://blog.tamizhvendan.in/blog/2016/09/19/scale-up-azure-functions-in-f-number-using-suave/)（使用 Suave 以 F# 扩展 Azure Functions）</span><span class="sxs-lookup"><span data-stu-id="59f56-121">[Scale Up Azure Functions in F# Using Suave](https://blog.tamizhvendan.in/blog/2016/09/19/scale-up-azure-functions-in-f-number-using-suave/)</span></span>
* <span data-ttu-id="59f56-122">[How to create Azure function in F#](https://mnie.github.io/2016-09-08-AzureFunctions/)（如何以 F# 创建 Azure Functions）</span><span class="sxs-lookup"><span data-stu-id="59f56-122">[How to create Azure function in F#](https://mnie.github.io/2016-09-08-AzureFunctions/)</span></span>
* [<span data-ttu-id="59f56-123">与 Azure 函数一起使用的 Azure 类型提供程序</span><span class="sxs-lookup"><span data-stu-id="59f56-123">Using the Azure Type Provider with Azure Functions</span></span>](https://compositional-it.com/blog/2017/08-30-using-the-azure-type-provider-with-azure-functions/index.html)

## <a name="using-azure-storage-with-f"></a><span data-ttu-id="59f56-124">使用 F # 使用 Azure 存储空间</span><span class="sxs-lookup"><span data-stu-id="59f56-124">Using Azure Storage with F#</span></span> #

<span data-ttu-id="59f56-125">Azure 存储是一种基层存储服务，用于依赖于持久性、可用性和可缩放性来满足其客户需求的现代应用程序。</span><span class="sxs-lookup"><span data-stu-id="59f56-125">Azure Storage is a base layer of storage services for modern applications that rely on durability, availability, and scalability to meet the needs of customers.</span></span> <span data-ttu-id="59f56-126">F# 程序可使用以下文章中所述的技术，直接与 Azure 存储服务交互。</span><span class="sxs-lookup"><span data-stu-id="59f56-126">F# programs can interact directly with Azure storage services, using the techinques described in the following articles.</span></span>

* [<span data-ttu-id="59f56-127">通过 F# 实现 Azure Blob 入门</span><span class="sxs-lookup"><span data-stu-id="59f56-127">Get started with Azure Blob storage using F#</span></span>](blob-storage.md)
* [<span data-ttu-id="59f56-128">通过 F# 实现 Azure 文件存储入门</span><span class="sxs-lookup"><span data-stu-id="59f56-128">Get started with Azure File storage using F#</span></span>](file-storage.md)
* [<span data-ttu-id="59f56-129">通过 F# 实现 Azure 队列存储入门</span><span class="sxs-lookup"><span data-stu-id="59f56-129">Get started with Azure Queue storage using F#</span></span>](queue-storage.md)
* [<span data-ttu-id="59f56-130">通过 F# 实现 Azure 表格存储入门</span><span class="sxs-lookup"><span data-stu-id="59f56-130">Get started with Azure Table storage using F#</span></span>](table-storage.md)

<span data-ttu-id="59f56-131">Azure 存储还可以通过声明性配置（而非显式 API 调用）与 Azure Functions 结合使用。</span><span class="sxs-lookup"><span data-stu-id="59f56-131">Azure Storage can also be used in conjunction with Azure Functions through declarative configuration rather than explicit API calls.</span></span> <span data-ttu-id="59f56-132">请参阅 [Azure Functions triggers and bindings for Azure Storage](/azure/azure-functions/functions-bindings-storage)（用于 Azure 存储的 Azure Functions 触发器和绑定），其中包括 F # 示例。</span><span class="sxs-lookup"><span data-stu-id="59f56-132">See [Azure Functions triggers and bindings for Azure Storage](/azure/azure-functions/functions-bindings-storage) which includes F# examples.</span></span>

## <a name="using-azure-app-service-with-f"></a><span data-ttu-id="59f56-133">使用 F # 使用 Azure App Service</span><span class="sxs-lookup"><span data-stu-id="59f56-133">Using Azure App Service with F#</span></span> #

<span data-ttu-id="59f56-134">[Azure 应用服务](https://azure.microsoft.com/services/app-service/)是一个用于构建功能强大的 Web 和移动应用的云平台，这些应用可连接到任何位置（云中或本地）的数据。</span><span class="sxs-lookup"><span data-stu-id="59f56-134">[Azure App Service](https://azure.microsoft.com/services/app-service/) is a cloud platform to build powerful web and mobile apps that connect to data anywhere, in the cloud or on-premises.</span></span>

* [<span data-ttu-id="59f56-135">F# Azure Web API 示例</span><span class="sxs-lookup"><span data-stu-id="59f56-135">F# Azure Web API example</span></span>](https://github.com/fsprojects/azure-webapi-example)
* <span data-ttu-id="59f56-136">[Hosting F# in a web application on Azure](https://github.com/isaacabraham/fsharp-demonstrator)（在 Azure 上的 Web 应用程序中托管 F#）</span><span class="sxs-lookup"><span data-stu-id="59f56-136">[Hosting F# in a web application on Azure](https://github.com/isaacabraham/fsharp-demonstrator)</span></span>

## <a name="using-apache-spark-with-f-with-azure-hdinsight"></a><span data-ttu-id="59f56-137">通过 Azure HDInsight 结合使用 Apache Spark 与 F#</span><span class="sxs-lookup"><span data-stu-id="59f56-137">Using Apache Spark with F# with Azure HDInsight</span></span>

<span data-ttu-id="59f56-138">[Apache Spark for Azure HDInsight](https://azure.microsoft.com/services/hdinsight/apache-spark/) 是一个开放源代码处理框架，用于运行大型数据分析应用程序。</span><span class="sxs-lookup"><span data-stu-id="59f56-138">[Apache Spark for Azure HDInsight](https://azure.microsoft.com/services/hdinsight/apache-spark/) is an open source processing framework that runs large-scale data analytics applications.</span></span> <span data-ttu-id="59f56-139">Azure 使 Apache Spark 的部署简单且经济实惠。</span><span class="sxs-lookup"><span data-stu-id="59f56-139">Azure makes Apache Spark easy and cost effective to deploy.</span></span> <span data-ttu-id="59f56-140">通过 [Mobius](https://github.com/Microsoft/Mobius)（适用于 Spark 的 .NET API）使用 F# 开发 Spark 应用程序。</span><span class="sxs-lookup"><span data-stu-id="59f56-140">Develop your Spark application in F# using [Mobius](https://github.com/Microsoft/Mobius), a .NET API for Spark.</span></span>

* <span data-ttu-id="59f56-141">[Implementing Spark Apps in F# using Mobius](https://github.com/Microsoft/Mobius/blob/master/notes/spark-fsharp-mobius.md)（使用 Mobius 以 F# 形式实现 Spark 应用）</span><span class="sxs-lookup"><span data-stu-id="59f56-141">[Implementing Spark Apps in F# using Mobius](https://github.com/Microsoft/Mobius/blob/master/notes/spark-fsharp-mobius.md)</span></span>
* [<span data-ttu-id="59f56-142">使用 Mobius 的示例 F# Spark 应用</span><span class="sxs-lookup"><span data-stu-id="59f56-142">Example F# Spark Apps using Mobius</span></span>](https://github.com/Microsoft/Mobius/tree/master/examples/fsharp)

## <a name="using-azure-cosmos-db-with-f"></a><span data-ttu-id="59f56-143">使用 F # 使用 Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="59f56-143">Using Azure Cosmos DB with F#</span></span> #

<span data-ttu-id="59f56-144">[Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db)是高度可用的全局分布式应用程序的 NoSQL 服务。</span><span class="sxs-lookup"><span data-stu-id="59f56-144">[Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db) is a NoSQL service for highly available, globally distributed apps.</span></span>

<span data-ttu-id="59f56-145">两种方式，可以使用 F # 使用 azure Cosmos DB:</span><span class="sxs-lookup"><span data-stu-id="59f56-145">Azure Cosmos DB can be used with F# in two ways:</span></span>

1. <span data-ttu-id="59f56-146">通过创建 F # Azure 函数的响应，或导致对 Azure Cosmos DB 集合的更改。</span><span class="sxs-lookup"><span data-stu-id="59f56-146">Through the creation of F# Azure Functions which react to or cause changes to Azure Cosmos DB collections.</span></span> <span data-ttu-id="59f56-147">请参阅[Azure 函数的 Azure Cosmos DB 绑定](/azure/azure-functions/functions-bindings-cosmosdb)，或</span><span class="sxs-lookup"><span data-stu-id="59f56-147">See [Azure Cosmos DB bindings for Azure Functions](/azure/azure-functions/functions-bindings-cosmosdb), or</span></span>
2. <span data-ttu-id="59f56-148">通过使用[Azure Cosmos DB.NET SDK for SQL API](/azure/cosmos-db/sql-api-sdk-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="59f56-148">By using the [Azure Cosmos DB .NET SDK for SQL API](/azure/cosmos-db/sql-api-sdk-dotnet).</span></span> <span data-ttu-id="59f56-149">相关的示例是用 C#。</span><span class="sxs-lookup"><span data-stu-id="59f56-149">The related samples are in C#.</span></span>

## <a name="using-azure-event-hubs-with-f"></a><span data-ttu-id="59f56-150">使用 F # 使用 Azure 事件中心</span><span class="sxs-lookup"><span data-stu-id="59f56-150">Using Azure Event Hubs with F#</span></span> #

<span data-ttu-id="59f56-151">[Azure 事件中心](https://azure.microsoft.com/services/event-hubs/)提供来自网站、应用和设备的云规模遥测引入。</span><span class="sxs-lookup"><span data-stu-id="59f56-151">[Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/) provide cloud-scale telemetry ingestion from websites, apps, and devices.</span></span>

<span data-ttu-id="59f56-152">可采用两种方式结合使用 Azure 事件中心与 F#：</span><span class="sxs-lookup"><span data-stu-id="59f56-152">Azure Event Hubs can be used with F# in two ways:</span></span>

1. <span data-ttu-id="59f56-153">通过创建由事件触发的 F# Azure Functions。</span><span class="sxs-lookup"><span data-stu-id="59f56-153">Through the creation of F# Azure Functions which are triggered by events.</span></span> <span data-ttu-id="59f56-154">请参阅 [Azure Function 事件中心触发器](/azure/azure-functions/functions-bindings-event-hubs)，或</span><span class="sxs-lookup"><span data-stu-id="59f56-154">See [Azure Function triggers for Event Hubs](/azure/azure-functions/functions-bindings-event-hubs), or</span></span>
2. <span data-ttu-id="59f56-155">通过使用[适用于 Azure 的 .NET SDK](/azure/event-hubs/event-hubs-csharp-ephcs-getstarted)。</span><span class="sxs-lookup"><span data-stu-id="59f56-155">By using the [.NET SDK for Azure](/azure/event-hubs/event-hubs-csharp-ephcs-getstarted).</span></span> <span data-ttu-id="59f56-156">请注意，这些示例使用的是 C#。</span><span class="sxs-lookup"><span data-stu-id="59f56-156">Note these examples are in C#.</span></span>

## <a name="using-azure-notification-hubs-with-f"></a><span data-ttu-id="59f56-157">使用 F # 使用 Azure 通知中心</span><span class="sxs-lookup"><span data-stu-id="59f56-157">Using Azure Notification Hubs with F#</span></span> #

<span data-ttu-id="59f56-158">[Azure 通知中心](/azure/notification-hubs/)是多平台扩展式推送基础结构，可使用它从任何后端（云中或本地）向任何移动平台发送移动推送通知。</span><span class="sxs-lookup"><span data-stu-id="59f56-158">[Azure Notification Hubs](/azure/notification-hubs/) are multiplatform, scaled-out push infrastructure that enable you to send mobile push notifications from any backend (in the cloud or on-premises) to any mobile platform.</span></span>

<span data-ttu-id="59f56-159">可采用两种方式结合使用 Azure 通知中心与 F#：</span><span class="sxs-lookup"><span data-stu-id="59f56-159">Azure Notification Hubs can be used with F# in two ways:</span></span>

1. <span data-ttu-id="59f56-160">通过创建向通知中心发送结果的 F# Azure Functions。</span><span class="sxs-lookup"><span data-stu-id="59f56-160">Through the creation of F# Azure Functions which send results to a notification hub.</span></span> <span data-ttu-id="59f56-161">请参阅 [Azure Functions 通知中心输出触发器](/azure/azure-functions/functions-bindings-notification-hubs)，或</span><span class="sxs-lookup"><span data-stu-id="59f56-161">See [Azure Function output triggers for Notification Hubs](/azure/azure-functions/functions-bindings-notification-hubs), or</span></span>
2. <span data-ttu-id="59f56-162">通过使用[适用于 Azure 的 .NET SDK](https://blogs.msdn.microsoft.com/azuremobile/2014/04/08/push-notifications-using-notification-hub-and-net-backend/)。</span><span class="sxs-lookup"><span data-stu-id="59f56-162">By using the [.NET SDK for Azure](https://blogs.msdn.microsoft.com/azuremobile/2014/04/08/push-notifications-using-notification-hub-and-net-backend/).</span></span> <span data-ttu-id="59f56-163">请注意，这些示例使用的是 C#。</span><span class="sxs-lookup"><span data-stu-id="59f56-163">Note these examples are in C#.</span></span>


## <a name="implementing-webhooks-on-azure-with-f"></a><span data-ttu-id="59f56-164">在 F # 的 Azure 上实现 Webhook</span><span class="sxs-lookup"><span data-stu-id="59f56-164">Implementing WebHooks on Azure with F#</span></span> #

<span data-ttu-id="59f56-165">[Webhook](https://en.wikipedia.org/wiki/Webhook) 是通过 Web 请求触发的回调。</span><span class="sxs-lookup"><span data-stu-id="59f56-165">A [Webhook](https://en.wikipedia.org/wiki/Webhook) is a callback triggered via a web request.</span></span> <span data-ttu-id="59f56-166">Webhook 由 GitHub 等站点使用，用以向事件发送信号。</span><span class="sxs-lookup"><span data-stu-id="59f56-166">Webhooks are used by sites such as GitHub to signal events.</span></span> 

<span data-ttu-id="59f56-167">Webhook 可采用 F# 实现，并通过 [Azure Function in F# with a Webhook Binding](/azure/azure-functions/functions-bindings-http-webhook)（具有 Web 绑定的 F# Azure Function）在 Azure 上进行托管。</span><span class="sxs-lookup"><span data-stu-id="59f56-167">Webhooks can be implemented in F# and hosted on Azure via an [Azure Function in F# with a Webhook Binding](/azure/azure-functions/functions-bindings-http-webhook).</span></span>

## <a name="using-webjobs-with-f"></a><span data-ttu-id="59f56-168">使用 web 作业的 F #</span><span class="sxs-lookup"><span data-stu-id="59f56-168">Using Webjobs with F#</span></span> #

<span data-ttu-id="59f56-169">[Webjob](/azure/app-service-web/web-sites-create-web-jobs) 是可采用以下三种方式在应用服务 Web 应用中运行的程序：按需、连续或按计划。</span><span class="sxs-lookup"><span data-stu-id="59f56-169">[Webjobs](/azure/app-service-web/web-sites-create-web-jobs) are programs you can run in your App Service web app in three ways: on demand, continuously, or on a schedule.</span></span>

[<span data-ttu-id="59f56-170">示例 F# Webjob</span><span class="sxs-lookup"><span data-stu-id="59f56-170">Example F# Webjob</span></span>](https://github.com/andredublin/fsharp-azure-webjob)

## <a name="implementing-timers-on-azure-with-f"></a><span data-ttu-id="59f56-171">在 F # 的 Azure 上实现计时器</span><span class="sxs-lookup"><span data-stu-id="59f56-171">Implementing Timers on Azure with F#</span></span> #

<span data-ttu-id="59f56-172">计时器触发器基于计划调用一次或重复调用函数。</span><span class="sxs-lookup"><span data-stu-id="59f56-172">Timer triggers call functions based on a schedule, one time or recurring.</span></span>

<span data-ttu-id="59f56-173">计时器可采用 F# 实现，并通过 [Azure Function in F# with a Timer Trigger](/azure/azure-functions/functions-bindings-timer)（具有计时器触发器的 F# Azure Function）在 Azure 上进行托管。</span><span class="sxs-lookup"><span data-stu-id="59f56-173">Timers can be implemented in F# and hosted on Azure via an [Azure Function in F# with a Timer Trigger](/azure/azure-functions/functions-bindings-timer).</span></span>

## <a name="deploying-and-managing-azure-resources-with-f-scripts"></a><span data-ttu-id="59f56-174">使用 F# 脚本部署和管理 Azure 资源</span><span class="sxs-lookup"><span data-stu-id="59f56-174">Deploying and Managing Azure Resources with F# Scripts</span></span> #

<span data-ttu-id="59f56-175">可使用 Microsoft.Azure.Management 包和 API，以编程方式通过 F# 脚本部署和管理 Azure VM。</span><span class="sxs-lookup"><span data-stu-id="59f56-175">Azure VMs may be programmatically deployed and managed from F# scripts by using the Microsoft.Azure.Management packages and APIs.</span></span> <span data-ttu-id="59f56-176">有关示例，请参阅 [.NET 管理库入门](https://msdn.microsoft.com/library/dn722415.aspx)和[使用 Azure 资源管理器](/azure/azure-resource-manager/resource-manager-deployment-model)。</span><span class="sxs-lookup"><span data-stu-id="59f56-176">For example, see [Get Started with the Management Libraries for .NET](https://msdn.microsoft.com/library/dn722415.aspx) and [Using Azure Resource Manager](/azure/azure-resource-manager/resource-manager-deployment-model).</span></span>

<span data-ttu-id="59f56-177">同样，其他 Azure 资源也可用相同的组件通过 F# 脚本进行部署和管理。</span><span class="sxs-lookup"><span data-stu-id="59f56-177">Likewise, other Azure resources may also be deployed and managed from F# scripts using the same components.</span></span> <span data-ttu-id="59f56-178">例如，你可以创建存储帐户、 部署 Azure 云服务、 创建 Azure Cosmos 数据库实例和从 F # 脚本以编程方式管理 Azure 通知中心。</span><span class="sxs-lookup"><span data-stu-id="59f56-178">For example, you can create storage accounts, deploy Azure Cloud Services, create Azure Cosmos DB instances and manage Azure Notifcation Hubs programmatically from F# scripts.</span></span>

<span data-ttu-id="59f56-179">通常，使用 F# 脚本来部署和管理资源并不必要。</span><span class="sxs-lookup"><span data-stu-id="59f56-179">Using F# scripts to deploy and manage resources is not normally necessary.</span></span> <span data-ttu-id="59f56-180">例如，Azure 资源也可直接通过 JSON 模板说明进行部署，可对该模板进行参数化。</span><span class="sxs-lookup"><span data-stu-id="59f56-180">For example, Azure resources may also be deployed directy from JSON template descriptions, which can be parameterized.</span></span> <span data-ttu-id="59f56-181">请参阅 [Azure 资源管理器模板](/azure/azure-resource-manager/resource-manager-template-best-practices)，包括 [Azure 快速入门模板](https://azure.microsoft.com/documentation/templates/)等示例。</span><span class="sxs-lookup"><span data-stu-id="59f56-181">See [Azure Resource Manager Templates](/azure/azure-resource-manager/resource-manager-template-best-practices) including examples such as the [Azure Quickstart Templates](https://azure.microsoft.com/documentation/templates/).</span></span>

## <a name="other-resources"></a><span data-ttu-id="59f56-182">其他资源</span><span class="sxs-lookup"><span data-stu-id="59f56-182">Other resources</span></span>

* [<span data-ttu-id="59f56-183">有关所有 Azure 服务的完整文档</span><span class="sxs-lookup"><span data-stu-id="59f56-183">Full documentation on all Azure services</span></span>](/azure/)
