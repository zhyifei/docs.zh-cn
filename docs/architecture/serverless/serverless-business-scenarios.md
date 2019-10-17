---
title: 无服务器应用的示例业务方案和用例
description: 通过访问从图像处理到移动后端和 ETL 管道的示例，了解无服务器操作。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 8a2301b3c7a5f4a1f465677f31371d5b94783692
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522390"
---
# <a name="serverless-business-scenarios-and-use-cases"></a>无服务器业务方案和用例

无服务器应用程序有许多用例和方案。 本章包含演示不同方案的示例。 这些方案包括指向相关文档和公共源代码存储库的链接。 本章中的示例可让你开始自己构建和实现无服务器解决方案。

## <a name="analyze-and-archive-images"></a>分析和存档映像

此示例演示无服务器事件（事件网格）、工作流（逻辑应用）和代码（Azure Functions）。 它还演示了如何与其他资源（在此例中为图像分析的认知服务）集成。

使用控制台应用程序，您可以将链接传递到 web 上的 URL。 应用将 URL 发布为事件网格消息。 并行，无服务器函数应用和逻辑应用订阅消息。 无服务器函数应用将映像序列化为 blob 存储。 它还将信息存储在 Azure 表存储中。 该元数据存储原始图像 URL 和 blob 映像的名称。 逻辑应用与自定义视觉 API 交互，以分析映像并创建计算机生成的标题。 标题存储在元数据表中。

![分析和存档映像体系结构](./media/image-processing-example.png)

单独的单页面应用程序（SPA）调用无服务器函数以获取图像和元数据的列表。 对于每个映像，它会调用另一个函数，该函数从存档中传递图像数据。 最终的结果是带有自动标题的库。

![自动映像库](./media/automated-image-gallery.png)

用于生成逻辑应用的完整存储库和说明可在此处找到：[事件网格粘附](https://github.com/JeremyLikness/Event-Grid-Glue)。

## <a name="cross-platform-mobile-client-using-xamarinforms-and-functions"></a>使用 Xamarin 的跨平台移动客户端。窗体和函数

请参阅如何在 Azure Web 门户或 Visual Studio 中实现简单的无服务器 Azure 功能。 使用在 Android、iOS 和 Windows 上运行的 Xamarin. Forms 生成客户端。 然后，将应用程序进行优化，以将 JavaScript 对象表示法（JSON）用作服务器与具有无服务器后端的移动客户端之间的通信媒介。

有关详细信息，请参阅[使用 Xamarin Client 实现简单的 Azure 函数](https://azure.microsoft.com/resources/samples/functions-xamarin-getting-started/)。

## <a name="generate-a-photo-mosaic-with-serverless-image-recognition"></a>使用无服务器映像识别生成照片马赛克

该示例使用 Azure Functions 和 Microsoft 认知服务自定义影像服务从输入图像生成照片马赛克。 对模型进行训练以识别图像。 当上载图像时，它将识别图像并使用必应搜索。 使用搜索结果 recomposed 原始图像。

![奥兰多眼睛照片和马赛克](./media/orlando-eye-both.png)

例如，您可以为您的模型提供奥兰多特征点，如奥兰多。 自定义视觉将识别奥兰多的图像，该函数将创建由必应图像搜索结果组成的照片马赛克用于 "奥兰多眼睛"。

有关详细信息，请参阅[Azure Functions 照片马赛克生成器](https://azure.microsoft.com/resources/samples/functions-dotnet-photo-mosaic/)。

## <a name="migrate-an-existing-application-to-the-cloud"></a>将现有应用程序迁移到云

如前面几章所述，通常采用 N 层体系结构在本地托管应用程序。 尽管使用虚拟机迁移资源是最不具风险的云路径，但很多公司选择使用此机会重构其应用程序。 幸运的是，重构不一定是一项 "全部或无意义"。 事实上，可以迁移你的应用程序，然后将组件逐段替换为云本机对应项。

应用程序使用 Azure Functions 的代理功能，启用将终结点从旧的本地代码重构到无服务器终结点。

![迁移体系结构](./media/migration-architecture.png)

代理提供单个 API 终结点，该终结点经过更新，可在移动到无服务器函数时重新路由单独的请求。

可以观看整个迁移的视频：通过[无服务器 Azure 功能](https://channel9.msdn.com/Events/Connect/2017/E102)进行直接迁移。 访问示例代码：[引入自己的应用](https://github.com/JeremyLikness/bring-own-app-connect-17)。

## <a name="parse-a-csv-file-and-insert-into-a-database"></a>分析 CSV 文件并将其插入到数据库中

提取、转换和加载（ETL）是集成不同系统的常见业务功能。 传统方法通常涉及设置专用 FTP 服务器，然后部署计划作业以分析文件并翻译它们以供业务使用。 无服务器体系结构使作业更简单，因为在上传文件时，触发器可能会激发。 Azure Functions 处理任务，如 ETL，这是一小部分代码的理想撰写，重点介绍特定的问题。

![显示 csv 分析过程的屏幕截图。](./media/serverless-business-scenarios/csv-parse-database-import.png)

有关源代码和动手实验，请参阅[CSV 导入实验室](https://github.com/JeremyLikness/azure-fn-file-process-hol)。

## <a name="shorten-links-and-track-metrics"></a>缩短链接和跟踪指标

Link 缩短工具最初有助于编码短 twitter 帖子中的 Url，以适应140字符的限制。 它们已发展为包含几个用途，最常见的是跟踪演练的分析。 Link 缩短符方案是一个完全无服务器的应用程序，用于管理链接和报告指标。

Azure Functions 用于提供单个页面应用程序（SPA），该应用程序允许你粘贴长 URL 并生成短 url。 标记 Url 以跟踪活动（主题）和媒体（如链接发布到的社交网络）等。 短代码作为密钥存储在 Azure 表存储中，长 URL 作为值。 单击短链接时，另一个函数查找长 URL，发送重定向，并将有关事件的信息放置在队列中。 另一个 Azure 函数处理队列，并将信息放入 Azure Cosmos DB。

![链接缩短符体系结构](./media/link-shortener-architecture.png)

然后，你可以创建一个 Power BI 仪表板，以便收集有关收集的数据的见解。 在后端，Application Insights 提供重要的指标。 遥测包括平均用户重定向花费的时间以及访问 Azure 表存储所用的时间。

![Power BI 示例](./media/power-bi-example.png)

可在此处获取完整的链接缩短符存储库，其中包含说明：[无服务器 URL 缩短符](https://github.com/jeremylikness/serverless-url-shortener)。 你可以在此处阅读有关简化版本的信息：[以分钟为单位的无服务器 .net 应用的 Azure 存储](https://devblogs.microsoft.com/aspnet/azure-storage-for-serverless-net-apps-in-minutes/)。

## <a name="verify-device-connectivity-using-a-ping"></a>使用 ping 验证设备连接

该示例包含 Azure IoT 中心和 Azure 函数。 IoT 中心上的新消息将触发 Azure 函数。 无服务器代码会将相同的消息内容发送回发送的设备。 项目包含解决方案所需的所有代码和部署配置。

有关详细信息，请参阅[Azure IoT 中心 ping](https://azure.microsoft.com/resources/samples/iot-hub-node-ping/)。

## <a name="recommended-resources"></a>推荐的资源

- [Azure Functions 照片马赛克生成器](https://azure.microsoft.com/resources/samples/functions-dotnet-photo-mosaic/)
- [Azure IoT 中心 ping](https://azure.microsoft.com/resources/samples/iot-hub-node-ping/)
- [Azure Storage for 无服务器 .NET 应用（分钟）](https://devblogs.microsoft.com/aspnet/azure-storage-for-serverless-net-apps-in-minutes/)
- [自带应用](https://github.com/JeremyLikness/bring-own-app-connect-17)
- [CSV 导入实验室](https://github.com/JeremyLikness/azure-fn-file-process-hol)
- [事件网格粘附](https://github.com/JeremyLikness/Event-Grid-Glue)
- [使用 Xamarin client 实现简单的 Azure 函数](https://azure.microsoft.com/resources/samples/functions-xamarin-getting-started/)
- [无服务器 Azure 功能的提升和移位](https://channel9.msdn.com/Events/Connect/2017/E102)
- [无服务器 URL 缩短符](https://github.com/jeremylikness/serverless-url-shortener)

>[!div class="step-by-step"]
>[上一页](orchestration-patterns.md)
>[下一页](serverless-conclusion.md)
