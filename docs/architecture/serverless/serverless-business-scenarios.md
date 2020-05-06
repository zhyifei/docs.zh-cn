---
title: 无服务器应用的示例业务方案和用例
description: 通过访问从映像处理到移动支持和 ETL 管道的示例，亲自了解无服务器操作。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/17/2020
ms.openlocfilehash: 3cb3b73325fccc327ccf17f7298048f2eeb3577a
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158445"
---
# <a name="serverless-business-scenarios-and-use-cases"></a><span data-ttu-id="666a9-103">无服务器业务方案和用例</span><span class="sxs-lookup"><span data-stu-id="666a9-103">Serverless business scenarios and use cases</span></span>

<span data-ttu-id="666a9-104">无服务器应用程序有许多用例和方案。</span><span class="sxs-lookup"><span data-stu-id="666a9-104">There are many use cases and scenarios for serverless applications.</span></span> <span data-ttu-id="666a9-105">本章包含演示不同方案的示例。</span><span class="sxs-lookup"><span data-stu-id="666a9-105">This chapter includes samples that illustrate the different scenarios.</span></span> <span data-ttu-id="666a9-106">这些方案包括指向相关文档和公共源代码存储库的链接。</span><span class="sxs-lookup"><span data-stu-id="666a9-106">The scenarios include links to related documentation and public source code repositories.</span></span> <span data-ttu-id="666a9-107">本章中的示例使你能够开始构建和实现无服务器解决方案。</span><span class="sxs-lookup"><span data-stu-id="666a9-107">The samples in this chapter enable you to get started on your own building and implementing serverless solutions.</span></span>

## <a name="big-data-processing"></a><span data-ttu-id="666a9-108">大数据处理</span><span class="sxs-lookup"><span data-stu-id="666a9-108">Big data processing</span></span>

![map/reduce 关系图](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/media/mapreducearchitecture.png)

<span data-ttu-id="666a9-110">此示例使用无服务器对大数据集执行 map/reduce 操作。</span><span class="sxs-lookup"><span data-stu-id="666a9-110">This example uses serverless to do a map/reduce operation on a big data set.</span></span> <span data-ttu-id="666a9-111">它确定 2017 年纽约黄色出租车每天行程的平均速度。</span><span class="sxs-lookup"><span data-stu-id="666a9-111">It determines the average speed of New York Yellow taxi trips per day in 2017.</span></span>

[<span data-ttu-id="666a9-112">大数据处理：Azure 上的无服务器 MapReduce</span><span class="sxs-lookup"><span data-stu-id="666a9-112">Big Data Processing: Serverless MapReduce on Azure</span></span>](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/)

## <a name="create-serverless-applications-hands-on-lab"></a><span data-ttu-id="666a9-113">创建无服务器应用程序：动手实验室</span><span class="sxs-lookup"><span data-stu-id="666a9-113">Create serverless applications: hands-on lab</span></span>

<span data-ttu-id="666a9-114">了解如何使用函数执行服务器端逻辑并构建无服务器体系结构。</span><span class="sxs-lookup"><span data-stu-id="666a9-114">Learn how to use functions to execute server-side logic and build serverless architectures.</span></span>

- <span data-ttu-id="666a9-115">为你的业务选择最佳 Azure 服务</span><span class="sxs-lookup"><span data-stu-id="666a9-115">Choosing the best Azure service for your business</span></span>
- <span data-ttu-id="666a9-116">创建 Azure Functions</span><span class="sxs-lookup"><span data-stu-id="666a9-116">Creating Azure Functions</span></span>
- <span data-ttu-id="666a9-117">使用触发器</span><span class="sxs-lookup"><span data-stu-id="666a9-117">Using triggers</span></span>
- <span data-ttu-id="666a9-118">链接函数</span><span class="sxs-lookup"><span data-stu-id="666a9-118">Chaining functions</span></span>
- <span data-ttu-id="666a9-119">长时间运行的工作流</span><span class="sxs-lookup"><span data-stu-id="666a9-119">Long-running workflows</span></span>
- <span data-ttu-id="666a9-120">监视</span><span class="sxs-lookup"><span data-stu-id="666a9-120">Monitoring</span></span>
- <span data-ttu-id="666a9-121">开发、测试和部署</span><span class="sxs-lookup"><span data-stu-id="666a9-121">Development, testing, and deployment</span></span>

[<span data-ttu-id="666a9-122">创建无服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="666a9-122">Create serverless applications</span></span>](https://docs.microsoft.com/learn/paths/create-serverless-applications/)

## <a name="customer-reviews"></a><span data-ttu-id="666a9-123">客户评审</span><span class="sxs-lookup"><span data-stu-id="666a9-123">Customer reviews</span></span>

<span data-ttu-id="666a9-124">此示例展示了 Visual Studio 中 C# 类库的新 Azure Functions 工具。</span><span class="sxs-lookup"><span data-stu-id="666a9-124">This sample showcases the new Azure Functions tooling for C# Class Libraries in Visual Studio.</span></span> <span data-ttu-id="666a9-125">创建一个网站，客户可以在其中提交存储在 Azure 存储 blob 和 CosmosDB 中的产品评论。</span><span class="sxs-lookup"><span data-stu-id="666a9-125">Create a website where customers submit product reviews that are stored in Azure storage blobs and CosmosDB.</span></span> <span data-ttu-id="666a9-126">添加 Azure Function，以使用 Azure 认知服务执行客户评审的自动审核。</span><span class="sxs-lookup"><span data-stu-id="666a9-126">Add an Azure Function to perform automated moderation of the customer reviews using Azure Cognitive Services.</span></span> <span data-ttu-id="666a9-127">使用 Azure 存储队列将网站与函数分离。</span><span class="sxs-lookup"><span data-stu-id="666a9-127">Use an Azure storage queue to decouple the website from the function.</span></span>

[<span data-ttu-id="666a9-128">客户通过认知服务评审应用</span><span class="sxs-lookup"><span data-stu-id="666a9-128">Customer Reviews App with Cognitive Services</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-customer-reviews/customer-reviews-cognitive-services/)

## <a name="docker-linux-image-support"></a><span data-ttu-id="666a9-129">Docker Linux 映像支持</span><span class="sxs-lookup"><span data-stu-id="666a9-129">Docker Linux image support</span></span>

<span data-ttu-id="666a9-130">此示例演示如何创建 `Dockerfile` 以在 Linux Docker 容器上生成和运行 Azure Functions。</span><span class="sxs-lookup"><span data-stu-id="666a9-130">This sample demonstrates how to create a `Dockerfile` to build and run Azure Functions on a Linux Docker container.</span></span>

[<span data-ttu-id="666a9-131">Linux 上的 Azure Functions</span><span class="sxs-lookup"><span data-stu-id="666a9-131">Azure Functions on Linux</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-linux-custom-image/azure-functions-on-linux-custom-image-tutorial-sample-project/)

## <a name="file-processing-and-validation"></a><span data-ttu-id="666a9-132">文件处理和验证</span><span class="sxs-lookup"><span data-stu-id="666a9-132">File processing and validation</span></span>

<span data-ttu-id="666a9-133">此示例分析来自假设客户的一组 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="666a9-133">This example parses a set of CSV files from hypothetical customers.</span></span> <span data-ttu-id="666a9-134">它确保客户“批处理”所需的所有文件都已准备就绪，然后验证每个文件的结构。</span><span class="sxs-lookup"><span data-stu-id="666a9-134">It ensures that all files required for a customer "batch" are ready, then validates the structure of each file.</span></span> <span data-ttu-id="666a9-135">使用 Azure Functions、逻辑应用和 Durable Functions 将提供不同的解决方案。</span><span class="sxs-lookup"><span data-stu-id="666a9-135">Different solutions are presented using Azure Functions, Logic Apps, and Durable Functions.</span></span>

[<span data-ttu-id="666a9-136">使用 Azure Functions、逻辑应用和 Durable Functions 进行文件处理和验证</span><span class="sxs-lookup"><span data-stu-id="666a9-136">File processing and validation using Azure Functions, Logic Apps, and Durable Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/serverless-file-validation/file-processing-and-validation-using-azure-functions-logic-apps-and-durable-functions/)

## <a name="game-data-visualization"></a><span data-ttu-id="666a9-137">游戏数据可视化</span><span class="sxs-lookup"><span data-stu-id="666a9-137">Game data visualization</span></span>

![游戏遥测](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/media/points.png)

<span data-ttu-id="666a9-139">提供了一个示例，演示了开发人员如何为其游戏实现编辑器内数据可视化解决方案。</span><span class="sxs-lookup"><span data-stu-id="666a9-139">An example of how a developer could implement an in-editor data visualization solution for their game.</span></span> <span data-ttu-id="666a9-140">事实上，Unreal Engine 4 插件和 Unity 插件是使用此示例作为其后端开发的。</span><span class="sxs-lookup"><span data-stu-id="666a9-140">In fact, an Unreal Engine 4 Plugin and Unity Plugin were developed using this sample as its backend.</span></span> <span data-ttu-id="666a9-141">服务组件与游戏引擎无关。</span><span class="sxs-lookup"><span data-stu-id="666a9-141">The service component is game engine agnostic.</span></span>

[<span data-ttu-id="666a9-142">编辑器内游戏遥测可视化</span><span class="sxs-lookup"><span data-stu-id="666a9-142">In-editor game telemetry visualization</span></span>](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/)

## <a name="graphql"></a><span data-ttu-id="666a9-143">GraphQL</span><span class="sxs-lookup"><span data-stu-id="666a9-143">GraphQL</span></span>

<span data-ttu-id="666a9-144">创建公开 GraphQL API 的无服务器函数。</span><span class="sxs-lookup"><span data-stu-id="666a9-144">Create a serverless function that exposes a GraphQL API.</span></span>

[<span data-ttu-id="666a9-145">GraphQL 的无服务器函数</span><span class="sxs-lookup"><span data-stu-id="666a9-145">Serverless functions for GraphQL</span></span>](https://github.com/softchris/graphql-workshop-dotnet/blob/master/docs/workshop/4.md)

## <a name="internet-of-things-iot-reliable-edge-relay"></a><span data-ttu-id="666a9-146">物联网 (IoT) 可靠边缘中继</span><span class="sxs-lookup"><span data-stu-id="666a9-146">Internet of Things (IoT) reliable edge relay</span></span>

![IoT 体系结构](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/media/architecture.png)

<span data-ttu-id="666a9-148">此示例实现新的通信协议，以便从 IoT 设备启用可靠的上游通信。</span><span class="sxs-lookup"><span data-stu-id="666a9-148">This sample implements a new communication protocol to enable reliable upstream communication from IoT devices.</span></span> <span data-ttu-id="666a9-149">它自动执行数据间隙检测和回填。</span><span class="sxs-lookup"><span data-stu-id="666a9-149">It automates data gap detection and backfill.</span></span>

[<span data-ttu-id="666a9-150">IoT 可靠边缘中继</span><span class="sxs-lookup"><span data-stu-id="666a9-150">IoT Reliable Edge Relay</span></span>](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/)

## <a name="microservices-reference-architecture"></a><span data-ttu-id="666a9-151">微服务参考体系结构</span><span class="sxs-lookup"><span data-stu-id="666a9-151">Microservices reference architecture</span></span>

![参考体系结构](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/media/macro-architecture.png)

<span data-ttu-id="666a9-153">此参考体系结构指导你完成设计、开发和交付 Rideshare by Relecloud 应用程序（虚构公司）所涉及的决策过程。</span><span class="sxs-lookup"><span data-stu-id="666a9-153">A reference architecture that walks you through the decision-making process involved in designing, developing, and delivering the Rideshare by Relecloud application (a fictitious company).</span></span> <span data-ttu-id="666a9-154">它包含有关配置和部署体系结构的所有组件的实际操作说明。</span><span class="sxs-lookup"><span data-stu-id="666a9-154">It includes hands-on instructions for configuring and deploying all of the architecture's components.</span></span>

[<span data-ttu-id="666a9-155">无服务器微服务参考体系结构</span><span class="sxs-lookup"><span data-stu-id="666a9-155">Serverless Microservices reference architecture</span></span>](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/)

## <a name="migrate-console-apps-to-serverless"></a><span data-ttu-id="666a9-156">将控制台应用迁移到无服务器</span><span class="sxs-lookup"><span data-stu-id="666a9-156">Migrate console apps to serverless</span></span>

<span data-ttu-id="666a9-157">此示例是一个泛型函数（`.csx` 文件），可用于将任何控制台应用程序转换为 Azure Functions 中的 HTTP Web 服务。</span><span class="sxs-lookup"><span data-stu-id="666a9-157">This sample is a generic function (`.csx` file) that can be used to convert any console application to an HTTP web service in Azure Functions.</span></span> <span data-ttu-id="666a9-158">只需编辑配置文件，并指定哪些输入参数将作为自变量传递到 `.exe`。</span><span class="sxs-lookup"><span data-stu-id="666a9-158">All you have to do is edit a configuration file and specify what input parameters will be passed as arguments to the `.exe`.</span></span>

[<span data-ttu-id="666a9-159">在 Azure Functions 上运行控制台应用</span><span class="sxs-lookup"><span data-stu-id="666a9-159">Run Console Apps on Azure Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-dotnet-migrating-console-apps/run-console-apps-on-azure-functions/)

## <a name="serverless-for-mobile"></a><span data-ttu-id="666a9-160">无服务器移动设备</span><span class="sxs-lookup"><span data-stu-id="666a9-160">Serverless for mobile</span></span>

<span data-ttu-id="666a9-161">Azure Functions 易于实现和维护，并可通过 HTTP 访问。</span><span class="sxs-lookup"><span data-stu-id="666a9-161">Azure Functions are easy to implement and maintain, and accessible through HTTP.</span></span> <span data-ttu-id="666a9-162">它们是实现移动应用程序 API 的好方法。</span><span class="sxs-lookup"><span data-stu-id="666a9-162">They are a great way to implement an API for a mobile application.</span></span> <span data-ttu-id="666a9-163">Microsoft 通过 Xamarin 提供适用于 iOS、Android 和 Windows 的优质跨平台工具。</span><span class="sxs-lookup"><span data-stu-id="666a9-163">Microsoft offers great cross-platform tools for iOS, Android, and Windows with Xamarin.</span></span> <span data-ttu-id="666a9-164">因此，Xamarin 和 Azure Functions 可以很好地协同工作。</span><span class="sxs-lookup"><span data-stu-id="666a9-164">As such, Xamarin and Azure Functions are working great together.</span></span> <span data-ttu-id="666a9-165">本文介绍了如何在 Azure 门户或 Visual Studio 中首先实现 Azure Function，并使用在 Android、iOS 和 Windows 上运行的 Xamarin.Forms 构建跨平台客户端。</span><span class="sxs-lookup"><span data-stu-id="666a9-165">This article shows how to implement an Azure Function in the Azure portal or in Visual Studio at first, and build a cross-platform client with Xamarin.Forms running on Android, iOS, and Windows.</span></span>

[<span data-ttu-id="666a9-166">通过 Xamarin.Forms 客户端执行单个 Azure 函数</span><span class="sxs-lookup"><span data-stu-id="666a9-166">Implementing a simple Azure Function with a Xamarin.Forms client</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)

## <a name="serverless-messaging"></a><span data-ttu-id="666a9-167">无服务器消息</span><span class="sxs-lookup"><span data-stu-id="666a9-167">Serverless messaging</span></span>

<span data-ttu-id="666a9-168">此示例演示如何利用 Durable Functions 的扇出模式跨任意数量的会话/分区加载任意数量的消息。</span><span class="sxs-lookup"><span data-stu-id="666a9-168">This sample shows how to utilize Durable Functions' fan-out pattern to load an arbitrary number of messages across any number of sessions/partitions.</span></span> <span data-ttu-id="666a9-169">它针对服务总线、事件中心或存储队列。</span><span class="sxs-lookup"><span data-stu-id="666a9-169">It targets Service Bus, Event Hubs, or Storage Queues.</span></span> <span data-ttu-id="666a9-170">该示例还添加了使用其他 Azure Function 来使用这些消息的功能，并将生成的计时数据加载到另一个事件中心。</span><span class="sxs-lookup"><span data-stu-id="666a9-170">The sample also adds the ability to consume those messages with another Azure Function and load the resulting timing data in to another Event Hub.</span></span> <span data-ttu-id="666a9-171">然后，数据引入到 Azure 数据资源管理器等分析服务中。</span><span class="sxs-lookup"><span data-stu-id="666a9-171">The data is then ingested into analytics services like Azure Data Explorer.</span></span>

[<span data-ttu-id="666a9-172">使用 Azure Functions 通过服务总线、事件中心和存储队列生成和使用消息</span><span class="sxs-lookup"><span data-stu-id="666a9-172">Produce and Consume messages through Service Bus, Event Hubs, and Storage Queues with Azure Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/durable-functions-producer-consumer/product-consume-messages-az-functions/)

## <a name="recommended-resources"></a><span data-ttu-id="666a9-173">推荐的资源</span><span class="sxs-lookup"><span data-stu-id="666a9-173">Recommended resources</span></span>

- [<span data-ttu-id="666a9-174">Linux 上的 Azure Functions</span><span class="sxs-lookup"><span data-stu-id="666a9-174">Azure Functions on Linux</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-linux-custom-image/azure-functions-on-linux-custom-image-tutorial-sample-project/)
- [<span data-ttu-id="666a9-175">大数据处理：Azure 上的无服务器 MapReduce</span><span class="sxs-lookup"><span data-stu-id="666a9-175">Big Data Processing: Serverless MapReduce on Azure</span></span>](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/)
- [<span data-ttu-id="666a9-176">创建无服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="666a9-176">Create serverless applications</span></span>](https://docs.microsoft.com/learn/paths/create-serverless-applications/)
- [<span data-ttu-id="666a9-177">客户通过认知服务评审应用</span><span class="sxs-lookup"><span data-stu-id="666a9-177">Customer Reviews App with Cognitive Services</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-customer-reviews/customer-reviews-cognitive-services/)
- [<span data-ttu-id="666a9-178">使用 Azure Functions、逻辑应用和 Durable Functions 进行文件处理和验证</span><span class="sxs-lookup"><span data-stu-id="666a9-178">File processing and validation using Azure Functions, Logic Apps, and Durable Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/serverless-file-validation/file-processing-and-validation-using-azure-functions-logic-apps-and-durable-functions/)
- [<span data-ttu-id="666a9-179">通过 Xamarin.Forms 客户端执行单个 Azure 函数</span><span class="sxs-lookup"><span data-stu-id="666a9-179">Implementing a simple Azure Function with a Xamarin.Forms client</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)
- [<span data-ttu-id="666a9-180">编辑器内游戏遥测可视化</span><span class="sxs-lookup"><span data-stu-id="666a9-180">In-editor game telemetry visualization</span></span>](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/)
- [<span data-ttu-id="666a9-181">IoT 可靠边缘中继</span><span class="sxs-lookup"><span data-stu-id="666a9-181">IoT Reliable Edge Relay</span></span>](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/)
- [<span data-ttu-id="666a9-182">使用 Azure Functions 通过服务总线、事件中心和存储队列生成和使用消息</span><span class="sxs-lookup"><span data-stu-id="666a9-182">Produce and Consume messages through Service Bus, Event Hubs, and Storage Queues with Azure Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/durable-functions-producer-consumer/product-consume-messages-az-functions/)
- [<span data-ttu-id="666a9-183">在 Azure Functions 上运行控制台应用</span><span class="sxs-lookup"><span data-stu-id="666a9-183">Run Console Apps on Azure Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-dotnet-migrating-console-apps/run-console-apps-on-azure-functions/)
- [<span data-ttu-id="666a9-184">GraphQL 的无服务器函数</span><span class="sxs-lookup"><span data-stu-id="666a9-184">Serverless functions for GraphQL</span></span>](https://github.com/softchris/graphql-workshop-dotnet/blob/master/docs/workshop/4.md)
- [<span data-ttu-id="666a9-185">无服务器微服务参考体系结构</span><span class="sxs-lookup"><span data-stu-id="666a9-185">Serverless Microservices reference architecture</span></span>](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/)

>[!div class="step-by-step"]
><span data-ttu-id="666a9-186">[上一页](orchestration-patterns.md)
>[下一页](serverless-conclusion.md)</span><span class="sxs-lookup"><span data-stu-id="666a9-186">[Previous](orchestration-patterns.md)
[Next](serverless-conclusion.md)</span></span>
