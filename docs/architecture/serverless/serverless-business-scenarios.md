---
title: 无服务器应用的示例业务方案和用例
description: 通过访问从图像处理到移动后端和 ETL 管道的示例, 了解无服务器操作。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: adc4e1f3249cd72c423430ad4cb5dbb8eea8baf9
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577280"
---
# <a name="serverless-business-scenarios-and-use-cases"></a><span data-ttu-id="e2f67-103">无服务器业务方案和用例</span><span class="sxs-lookup"><span data-stu-id="e2f67-103">Serverless business scenarios and use cases</span></span>

<span data-ttu-id="e2f67-104">无服务器应用程序有许多用例和方案。</span><span class="sxs-lookup"><span data-stu-id="e2f67-104">There are many use cases and scenarios for serverless applications.</span></span> <span data-ttu-id="e2f67-105">本章包含演示不同方案的示例。</span><span class="sxs-lookup"><span data-stu-id="e2f67-105">This chapter includes samples that illustrate the different scenarios.</span></span> <span data-ttu-id="e2f67-106">这些方案包括指向相关文档和公共源代码存储库的链接。</span><span class="sxs-lookup"><span data-stu-id="e2f67-106">The scenarios include links to related documentation and public source code repositories.</span></span> <span data-ttu-id="e2f67-107">本章中的示例可让你开始自己构建和实现无服务器解决方案。</span><span class="sxs-lookup"><span data-stu-id="e2f67-107">The samples in this chapter enable you to get started on your own building and implementing serverless solutions.</span></span>

## <a name="analyze-and-archive-images"></a><span data-ttu-id="e2f67-108">分析和存档映像</span><span class="sxs-lookup"><span data-stu-id="e2f67-108">Analyze and archive images</span></span>

<span data-ttu-id="e2f67-109">此示例演示无服务器事件 (事件网格)、工作流 (逻辑应用) 和代码 (Azure Functions)。</span><span class="sxs-lookup"><span data-stu-id="e2f67-109">This sample demonstrates serverless events (Event Grid), workflows (Logic App), and code (Azure Functions).</span></span> <span data-ttu-id="e2f67-110">它还演示了如何与其他资源 (在此例中为图像分析的认知服务) 集成。</span><span class="sxs-lookup"><span data-stu-id="e2f67-110">It also shows how to integrate with another resource, in this case Cognitive Services for image analysis.</span></span>

<span data-ttu-id="e2f67-111">使用控制台应用程序, 您可以将链接传递到 web 上的 URL。</span><span class="sxs-lookup"><span data-stu-id="e2f67-111">A console application allows you to pass a link to a URL on the web.</span></span> <span data-ttu-id="e2f67-112">应用将 URL 发布为事件网格消息。</span><span class="sxs-lookup"><span data-stu-id="e2f67-112">The app publishes the URL as an event grid message.</span></span> <span data-ttu-id="e2f67-113">并行, 无服务器函数应用和逻辑应用订阅消息。</span><span class="sxs-lookup"><span data-stu-id="e2f67-113">In parallel, a serverless function app and a logic app subscribe to the message.</span></span> <span data-ttu-id="e2f67-114">无服务器函数应用将映像序列化为 blob 存储。</span><span class="sxs-lookup"><span data-stu-id="e2f67-114">The serverless function app serializes the image to blob storage.</span></span> <span data-ttu-id="e2f67-115">它还将信息存储在 Azure 表存储中。</span><span class="sxs-lookup"><span data-stu-id="e2f67-115">It also stores information in Azure Table Storage.</span></span> <span data-ttu-id="e2f67-116">该元数据存储原始图像 URL 和 blob 映像的名称。</span><span class="sxs-lookup"><span data-stu-id="e2f67-116">The metadata stores the original image URL and the name of the blob image.</span></span> <span data-ttu-id="e2f67-117">逻辑应用与自定义视觉 API 交互, 以分析映像并创建计算机生成的标题。</span><span class="sxs-lookup"><span data-stu-id="e2f67-117">The logic app interacts with the Custom Vision API to analyze the image and create a machine-generated caption.</span></span> <span data-ttu-id="e2f67-118">标题存储在元数据表中。</span><span class="sxs-lookup"><span data-stu-id="e2f67-118">The caption is stored in the metadata table.</span></span>

![分析和存档映像体系结构](./media/image-processing-example.png)

<span data-ttu-id="e2f67-120">单独的单页面应用程序 (SPA) 调用无服务器函数以获取图像和元数据的列表。</span><span class="sxs-lookup"><span data-stu-id="e2f67-120">A separate single page application (SPA) calls a serverless function to get a list of images and metadata.</span></span> <span data-ttu-id="e2f67-121">对于每个映像, 它会调用另一个函数, 该函数从存档中传递图像数据。</span><span class="sxs-lookup"><span data-stu-id="e2f67-121">For each image, it calls another function that delivers the image data from the archive.</span></span> <span data-ttu-id="e2f67-122">最终的结果是带有自动标题的库。</span><span class="sxs-lookup"><span data-stu-id="e2f67-122">The final result is a gallery with automatic captions.</span></span>

![自动映像库](./media/automated-image-gallery.png)

<span data-ttu-id="e2f67-124">可在此处获取完整的存储库和生成逻辑应用的说明:[事件网格粘附](https://github.com/JeremyLikness/Event-Grid-Glue)。</span><span class="sxs-lookup"><span data-stu-id="e2f67-124">The full repository and instructions to build the logic app are available here: [Event grid glue](https://github.com/JeremyLikness/Event-Grid-Glue).</span></span>

## <a name="cross-platform-mobile-client-using-xamarinforms-and-functions"></a><span data-ttu-id="e2f67-125">使用 Xamarin 的跨平台移动客户端。窗体和函数</span><span class="sxs-lookup"><span data-stu-id="e2f67-125">Cross-platform mobile client using Xamarin.Forms and functions</span></span>

<span data-ttu-id="e2f67-126">请参阅如何在 Azure Web 门户或 Visual Studio 中实现简单的无服务器 Azure 功能。</span><span class="sxs-lookup"><span data-stu-id="e2f67-126">See how to implement a simple serverless Azure Function in the Azure Web Portal or in Visual Studio.</span></span> <span data-ttu-id="e2f67-127">使用在 Android、iOS 和 Windows 上运行的 Xamarin. Forms 生成客户端。</span><span class="sxs-lookup"><span data-stu-id="e2f67-127">Build a client with Xamarin.Forms that runs on Android, iOS, and Windows.</span></span> <span data-ttu-id="e2f67-128">然后, 将应用程序进行优化, 以将 JavaScript 对象表示法 (JSON) 用作服务器与具有无服务器后端的移动客户端之间的通信媒介。</span><span class="sxs-lookup"><span data-stu-id="e2f67-128">The application is then refined to use JavaScript Object Notation (JSON) as a communication medium between the server and the mobile clients with a serverless back end.</span></span>

<span data-ttu-id="e2f67-129">有关详细信息, 请参阅[使用 Xamarin 客户端实现简单的 Azure 函数](https://azure.microsoft.com/resources/samples/functions-xamarin-getting-started/)</span><span class="sxs-lookup"><span data-stu-id="e2f67-129">For more information, see [Implementing a simple Azure Function with a Xamarin.Forms client](https://azure.microsoft.com/resources/samples/functions-xamarin-getting-started/)</span></span>

## <a name="generate-a-photo-mosaic-with-serverless-image-recognition"></a><span data-ttu-id="e2f67-130">使用无服务器映像识别生成照片马赛克</span><span class="sxs-lookup"><span data-stu-id="e2f67-130">Generate a photo mosaic with serverless image recognition</span></span>

<span data-ttu-id="e2f67-131">该示例使用 Azure Functions 和 Microsoft 认知服务自定义影像服务从输入图像生成照片马赛克。</span><span class="sxs-lookup"><span data-stu-id="e2f67-131">The sample uses Azure Functions and Microsoft Cognitive Services Custom Vision Service to generate a photo mosaic from an input image.</span></span> <span data-ttu-id="e2f67-132">对模型进行训练以识别图像。</span><span class="sxs-lookup"><span data-stu-id="e2f67-132">The model is trained to recognize images.</span></span> <span data-ttu-id="e2f67-133">当上载图像时, 它将识别图像并使用必应搜索。</span><span class="sxs-lookup"><span data-stu-id="e2f67-133">When an image is uploaded, it recognizes the image and searches with Bing.</span></span> <span data-ttu-id="e2f67-134">使用搜索结果 recomposed 原始图像。</span><span class="sxs-lookup"><span data-stu-id="e2f67-134">The original image is recomposed using the search results.</span></span>

![奥兰多眼睛照片和马赛克](./media/orlando-eye-both.png)

<span data-ttu-id="e2f67-136">例如, 您可以为您的模型提供奥兰多特征点, 如奥兰多。</span><span class="sxs-lookup"><span data-stu-id="e2f67-136">For example, you can train your model with Orlando landmarks, such as the Orlando Eye.</span></span> <span data-ttu-id="e2f67-137">自定义视觉将识别奥兰多的图像, 该函数将创建由必应图像搜索结果组成的照片马赛克用于 "奥兰多眼睛"。</span><span class="sxs-lookup"><span data-stu-id="e2f67-137">Custom Vision will recognize an image of the Orlando Eye, and the function will create a photo mosaic composed of Bing image search results for "Orlando Eye."</span></span>

<span data-ttu-id="e2f67-138">有关详细信息, 请参阅[Azure Functions 照片马赛克生成器](https://azure.microsoft.com/resources/samples/functions-dotnet-photo-mosaic/)。</span><span class="sxs-lookup"><span data-stu-id="e2f67-138">For more information, see [Azure Functions photo mosaic generator](https://azure.microsoft.com/resources/samples/functions-dotnet-photo-mosaic/).</span></span>

## <a name="migrate-an-existing-application-to-the-cloud"></a><span data-ttu-id="e2f67-139">将现有应用程序迁移到云</span><span class="sxs-lookup"><span data-stu-id="e2f67-139">Migrate an existing application to the cloud</span></span>

<span data-ttu-id="e2f67-140">如前面几章所述, 通常采用 N 层体系结构在本地托管应用程序。</span><span class="sxs-lookup"><span data-stu-id="e2f67-140">As discussed in previous chapters, it's common to embrace an N-Tier architecture to host your application on-premises.</span></span> <span data-ttu-id="e2f67-141">尽管使用虚拟机迁移资源是最不具风险的云路径, 但很多公司选择使用此机会重构其应用程序。</span><span class="sxs-lookup"><span data-stu-id="e2f67-141">Although migrating resources "as is" using virtual machines is the least risky path to the cloud, many companies choose to use the opportunity to refactor their applications.</span></span> <span data-ttu-id="e2f67-142">幸运的是, 重构不一定是一项 "全部或无意义"。</span><span class="sxs-lookup"><span data-stu-id="e2f67-142">Fortunately, refactoring doesn't have to be an "all-or-nothing" effort.</span></span> <span data-ttu-id="e2f67-143">事实上, 可以迁移你的应用程序, 然后将组件逐段替换为云本机对应项。</span><span class="sxs-lookup"><span data-stu-id="e2f67-143">In fact, it's possible to migrate your app then piecemeal replace components with cloud native counterparts.</span></span>

<span data-ttu-id="e2f67-144">应用程序使用 Azure Functions 的代理功能, 启用将终结点从旧的本地代码重构到无服务器终结点。</span><span class="sxs-lookup"><span data-stu-id="e2f67-144">The application uses the proxies feature of Azure Functions to enable refactoring an endpoint from legacy on-premises code to a serverless endpoint.</span></span>

![迁移体系结构](./media/migration-architecture.png)

<span data-ttu-id="e2f67-146">代理提供单个 API 终结点, 该终结点经过更新, 可在移动到无服务器函数时重新路由单独的请求。</span><span class="sxs-lookup"><span data-stu-id="e2f67-146">The proxy provides a single API endpoint that is updated to reroute individual requests as they're moved into serverless functions.</span></span>

<span data-ttu-id="e2f67-147">可以查看视频来完成整个迁移:[无服务器 Azure 功能的提升和转移](https://channel9.msdn.com/Events/Connect/2017/E102)。</span><span class="sxs-lookup"><span data-stu-id="e2f67-147">You can view a video that walks through the entire migration: [Lift and shift with serverless Azure functions](https://channel9.msdn.com/Events/Connect/2017/E102).</span></span> <span data-ttu-id="e2f67-148">访问示例代码:[引入你自己的应用](https://github.com/JeremyLikness/bring-own-app-connect-17)。</span><span class="sxs-lookup"><span data-stu-id="e2f67-148">Access the sample code: [Bring your own app](https://github.com/JeremyLikness/bring-own-app-connect-17).</span></span>

## <a name="parse-a-csv-file-and-insert-into-a-database"></a><span data-ttu-id="e2f67-149">分析 CSV 文件并将其插入到数据库中</span><span class="sxs-lookup"><span data-stu-id="e2f67-149">Parse a CSV file and insert into a database</span></span>

<span data-ttu-id="e2f67-150">提取、转换和加载 (ETL) 是集成不同系统的常见业务功能。</span><span class="sxs-lookup"><span data-stu-id="e2f67-150">Extract, Transform, and Load (ETL) is a common business function that integrates different systems.</span></span> <span data-ttu-id="e2f67-151">传统方法通常涉及设置专用 FTP 服务器, 然后部署计划作业以分析文件并翻译它们以供业务使用。</span><span class="sxs-lookup"><span data-stu-id="e2f67-151">Traditional approaches often involve setting up dedicated FTP servers then deploying scheduled jobs to parse files and translate them for business use.</span></span> <span data-ttu-id="e2f67-152">无服务器体系结构使作业更简单, 因为在上传文件时, 触发器可能会激发。</span><span class="sxs-lookup"><span data-stu-id="e2f67-152">Serverless architecture makes the job easier because a trigger can fire when the file is uploaded.</span></span> <span data-ttu-id="e2f67-153">Azure Functions 处理任务, 如 ETL, 这是一小部分代码的理想撰写, 重点介绍特定的问题。</span><span class="sxs-lookup"><span data-stu-id="e2f67-153">Azure Functions tackles tasks like ETL through its ideal composition of small pieces of code that focus on a specific problem.</span></span>

![显示 csv 分析过程的屏幕截图。](./media/serverless-business-scenarios/csv-parse-database-import.png)

<span data-ttu-id="e2f67-155">有关源代码和动手实验, 请参阅[CSV 导入实验室](https://github.com/JeremyLikness/azure-fn-file-process-hol)。</span><span class="sxs-lookup"><span data-stu-id="e2f67-155">For source code and a hands-on lab, see [CSV import lab](https://github.com/JeremyLikness/azure-fn-file-process-hol).</span></span>

## <a name="shorten-links-and-track-metrics"></a><span data-ttu-id="e2f67-156">缩短链接和跟踪指标</span><span class="sxs-lookup"><span data-stu-id="e2f67-156">Shorten links and track metrics</span></span>

<span data-ttu-id="e2f67-157">Link 缩短工具最初有助于编码短 twitter 帖子中的 Url, 以适应140字符的限制。</span><span class="sxs-lookup"><span data-stu-id="e2f67-157">Link shortening tools originally helped encode URLs in short twitter posts to accommodate the 140 character limit.</span></span> <span data-ttu-id="e2f67-158">它们已发展为包含几个用途, 最常见的是跟踪演练的分析。</span><span class="sxs-lookup"><span data-stu-id="e2f67-158">They've grown to encompass several uses, most commonly to track click-throughs for analytics.</span></span> <span data-ttu-id="e2f67-159">Link 缩短符方案是一个完全无服务器的应用程序, 用于管理链接和报告指标。</span><span class="sxs-lookup"><span data-stu-id="e2f67-159">The link shortener scenario is an entirely serverless application that manages links and reports metrics.</span></span>

<span data-ttu-id="e2f67-160">Azure Functions 用于提供单个页面应用程序 (SPA), 该应用程序允许你粘贴长 URL 并生成短 url。</span><span class="sxs-lookup"><span data-stu-id="e2f67-160">Azure Functions is used to serve a Single Page Application (SPA) that allows you to paste the long URL and generate short URLs.</span></span> <span data-ttu-id="e2f67-161">标记 Url 以跟踪活动 (主题) 和媒体 (如链接发布到的社交网络) 等。</span><span class="sxs-lookup"><span data-stu-id="e2f67-161">The URLs are tagged to track things like campaigns (topics) and mediums (such as social networks that the links are posted to).</span></span> <span data-ttu-id="e2f67-162">短代码作为密钥存储在 Azure 表存储中, 长 URL 作为值。</span><span class="sxs-lookup"><span data-stu-id="e2f67-162">The short code is stored in Azure Table Storage as the key, with the long URL as the value.</span></span> <span data-ttu-id="e2f67-163">单击短链接时, 另一个函数查找长 URL, 发送重定向, 并将有关事件的信息放置在队列中。</span><span class="sxs-lookup"><span data-stu-id="e2f67-163">When you click on the short link, another function looks up the long URL, sends a redirect, and places information about the event on a queue.</span></span> <span data-ttu-id="e2f67-164">另一个 Azure 函数处理队列, 并将信息放入 Azure Cosmos DB。</span><span class="sxs-lookup"><span data-stu-id="e2f67-164">Another Azure Function processes the queue and places the information into Azure Cosmos DB.</span></span>

![链接缩短符体系结构](./media/link-shortener-architecture.png)

<span data-ttu-id="e2f67-166">然后, 你可以创建一个 Power BI 仪表板, 以便收集有关收集的数据的见解。</span><span class="sxs-lookup"><span data-stu-id="e2f67-166">You can then create a Power BI dashboard to gather insights about the data collected.</span></span> <span data-ttu-id="e2f67-167">在后端, Application Insights 提供重要的指标。</span><span class="sxs-lookup"><span data-stu-id="e2f67-167">On the back end, Application Insights provides important metrics.</span></span> <span data-ttu-id="e2f67-168">遥测包括平均用户重定向花费的时间以及访问 Azure 表存储所用的时间。</span><span class="sxs-lookup"><span data-stu-id="e2f67-168">Telemetry includes how long it takes for the average user to redirect and how long it takes to access Azure Table Storage.</span></span>

![Power BI 示例](./media/power-bi-example.png)

<span data-ttu-id="e2f67-170">可在此处获取完整的链接缩短符存储库, 其中包含说明:[无服务器 URL 缩短符](https://github.com/jeremylikness/serverless-url-shortener)。</span><span class="sxs-lookup"><span data-stu-id="e2f67-170">The full link shortener repository with instructions is available here: [Serverless URL shortener](https://github.com/jeremylikness/serverless-url-shortener).</span></span> <span data-ttu-id="e2f67-171">可在此处阅读有关简化版本的信息:[Azure Storage for 无服务器 .net 应用 (分钟)](https://blogs.msdn.microsoft.com/webdev/2018/01/25/azure-storage-for-serverless-net-apps-in-minutes/)。</span><span class="sxs-lookup"><span data-stu-id="e2f67-171">You can read about a simplified version here: [Azure Storage for serverless .NET apps in minutes](https://blogs.msdn.microsoft.com/webdev/2018/01/25/azure-storage-for-serverless-net-apps-in-minutes/).</span></span>

## <a name="verify-device-connectivity-using-a-ping"></a><span data-ttu-id="e2f67-172">使用 ping 验证设备连接</span><span class="sxs-lookup"><span data-stu-id="e2f67-172">Verify device connectivity using a ping</span></span>

<span data-ttu-id="e2f67-173">该示例包含 Azure IoT 中心和 Azure 函数。</span><span class="sxs-lookup"><span data-stu-id="e2f67-173">The sample consists of an Azure IoT Hub and an Azure Function.</span></span> <span data-ttu-id="e2f67-174">IoT 中心上的新消息将触发 Azure 函数。</span><span class="sxs-lookup"><span data-stu-id="e2f67-174">A new message on the IoT Hub triggers the Azure Function.</span></span> <span data-ttu-id="e2f67-175">无服务器代码会将相同的消息内容发送回发送的设备。</span><span class="sxs-lookup"><span data-stu-id="e2f67-175">The serverless code sends the same message content back to the device that sent it.</span></span> <span data-ttu-id="e2f67-176">项目包含解决方案所需的所有代码和部署配置。</span><span class="sxs-lookup"><span data-stu-id="e2f67-176">The project has all the code and deployment configuration needed for the solution.</span></span>

<span data-ttu-id="e2f67-177">有关详细信息, 请参阅[Azure IoT 中心 ping](https://azure.microsoft.com/resources/samples/iot-hub-node-ping/)。</span><span class="sxs-lookup"><span data-stu-id="e2f67-177">For more information, see [Azure IoT Hub ping](https://azure.microsoft.com/resources/samples/iot-hub-node-ping/).</span></span>

## <a name="recommended-resources"></a><span data-ttu-id="e2f67-178">推荐的资源</span><span class="sxs-lookup"><span data-stu-id="e2f67-178">Recommended resources</span></span>

* [<span data-ttu-id="e2f67-179">Azure Functions 照片马赛克生成器</span><span class="sxs-lookup"><span data-stu-id="e2f67-179">Azure Functions photo mosaic generator</span></span>](https://azure.microsoft.com/resources/samples/functions-dotnet-photo-mosaic/)
* [<span data-ttu-id="e2f67-180">Azure IoT 中心 ping</span><span class="sxs-lookup"><span data-stu-id="e2f67-180">Azure IoT Hub ping</span></span>](https://azure.microsoft.com/resources/samples/iot-hub-node-ping/)
* [<span data-ttu-id="e2f67-181">Azure Storage for 无服务器 .NET 应用 (分钟)</span><span class="sxs-lookup"><span data-stu-id="e2f67-181">Azure Storage for serverless .NET apps in minutes</span></span>](https://blogs.msdn.microsoft.com/webdev/2018/01/25/azure-storage-for-serverless-net-apps-in-minutes/)
* [<span data-ttu-id="e2f67-182">自带应用</span><span class="sxs-lookup"><span data-stu-id="e2f67-182">Bring your own app</span></span>](https://github.com/JeremyLikness/bring-own-app-connect-17)
* [<span data-ttu-id="e2f67-183">CSV 导入实验室</span><span class="sxs-lookup"><span data-stu-id="e2f67-183">CSV import lab</span></span>](https://github.com/JeremyLikness/azure-fn-file-process-hol)
* [<span data-ttu-id="e2f67-184">事件网格粘附</span><span class="sxs-lookup"><span data-stu-id="e2f67-184">Event grid glue</span></span>](https://github.com/JeremyLikness/Event-Grid-Glue)
* [<span data-ttu-id="e2f67-185">使用 Xamarin client 实现简单的 Azure 函数</span><span class="sxs-lookup"><span data-stu-id="e2f67-185">Implementing a simple Azure Function with a Xamarin.Forms client</span></span>](https://azure.microsoft.com/resources/samples/functions-xamarin-getting-started/)
* [<span data-ttu-id="e2f67-186">无服务器 Azure 功能的提升和移位</span><span class="sxs-lookup"><span data-stu-id="e2f67-186">Lift and shift with serverless Azure functions</span></span>](https://channel9.msdn.com/Events/Connect/2017/E102)
* [<span data-ttu-id="e2f67-187">无服务器 URL 缩短符</span><span class="sxs-lookup"><span data-stu-id="e2f67-187">Serverless URL shortener</span></span>](https://github.com/jeremylikness/serverless-url-shortener)

>[!div class="step-by-step"]
><span data-ttu-id="e2f67-188">[上一页](orchestration-patterns.md)
>[下一页](serverless-conclusion.md)</span><span class="sxs-lookup"><span data-stu-id="e2f67-188">[Previous](orchestration-patterns.md)
[Next](serverless-conclusion.md)</span></span>
