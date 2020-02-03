---
title: 无服务器应用的示例业务方案和用例
description: 通过访问从映像处理到移动后端和 ETL 管道的示例，亲自了解无服务器操作。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 5f0d7a4c5cd736d1168ec76c1c0ea19627505f15
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76787892"
---
# <a name="serverless-business-scenarios-and-use-cases"></a>无服务器业务方案和用例

无服务器应用程序有许多用例和方案。 本章包含演示不同方案的示例。 这些方案包括指向相关文档和公共源代码存储库的链接。 本章中的示例使你能够开始构建和实现无服务器解决方案。

## <a name="analyze-and-archive-images"></a>分析和归档映像

此示例演示无服务器事件（事件网格）、工作流（逻辑应用）和代码 (Azure Functions)。 它还演示了如何与其他资源（在此例中为映像分析的认知服务）相集成。

使用控制台应用程序，你可以将链接传递到 Web 上的 URL。 应用将 URL 发布为事件网格消息。 并行时，无服务器函数应用和逻辑应用订阅消息。 无服务器函数应用将映像序列化为 blob 存储。 它还将信息存储在 Azure 表存储中。 元数据存储 blob 映像的原始映像 URL 和名称。 逻辑应用与自定义视觉 API 交互，以分析映像并创建计算机生成的标题。 标题存储在元数据表中。

![分析和归档映像体系结构](./media/image-processing-example.png)

单独的单页面应用程序 (SPA) 调用无服务器函数以获取映像和元数据的列表。 对于每个映像，它会调用另一个函数，此函数从存档中传递映像数据。 最终的结果是带有自动标题的库。

![自动化映像库](./media/automated-image-gallery.png)

可在此处获取完整的存储库和生成逻辑应用的说明：[事件网格粘附](https://github.com/JeremyLikness/Event-Grid-Glue)。

## <a name="cross-platform-mobile-client-using-xamarinforms-and-functions"></a>使用 Xamarin.Forms 和函数的跨平台移动客户端

请参阅如何在 Azure 门户网站或 Visual Studio 中实现简单的无服务器 Azure 函数。 使用在 Android、iOS 和 Windows 上运行的 Xamarin. Forms 生成客户端。 然后，优化应用程序以将 JavaScript 对象表示法 (JSON) 用作服务器与带无服务器后端的移动客户端之间的通信媒介。

有关详细信息，请参阅[通过 Xamarin.Forms 客户端执行单个 Azure 函数](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)。

## <a name="generate-a-photo-mosaic-with-serverless-image-recognition"></a>使用无服务器映像识别生成照片马赛克

该示例使用 Azure Functions 和 Microsoft 认知服务自定义视觉服务从输入映像生成照片马赛克。 训练模型以识别图像。 上传图像时，它会识别图像并使用必应搜索。 使用搜索结果重构原始图像。

![奥兰多之眼照片和马赛克](./media/orlando-eye-both.png)

例如，可以使用奥兰多地标（奥兰多之眼）来训练模型。 自定义视觉将识别奥兰多之眼的图像，此函数将创建由必应关于“奥兰多之眼”图像搜索结果组成的照片马赛克。

有关详细信息，请参阅 [Azure Functions 照片马赛克生成器](https://github.com/Azure-Samples/functions-dotnet-photo-mosaic)。

## <a name="migrate-an-existing-application-to-the-cloud"></a>将现有应用程序迁移到云

如前面几章所述，通常采用 N 层体系结构在本地托管应用程序。 尽管使用虚拟机按原样迁移资源是最不具风险的云路径，但很多公司选择把握此机会重构其应用程序。 幸运的是，重构不一定是一项“要么全有，要么全无”的工作。 事实上，可以迁移应用，然后将组件逐段替换为云本机对应项。

应用程序使用 Azure Functions 的代理功能，以实现将终结点从旧的本地代码重构为无服务器终结点。

![迁移体系结构](./media/migration-architecture.png)

代理提供单个 API 终结点，此终结点经过更新，可在移动到无服务器函数时重新路由单独的请求。

可以查看视频来完成整个迁移：[使用无服务器 Azure 函数直接迁移](https://channel9.msdn.com/Events/Connect/2017/E102)。 访问示例代码：[自带应用](https://github.com/JeremyLikness/bring-own-app-connect-17)。

## <a name="parse-a-csv-file-and-insert-into-a-database"></a>分析 CSV 文件并将其插入数据库

提取、转换和加载 (ETL) 是集成不同系统的常见业务功能。 传统方法通常涉及设置专用 FTP 服务器，然后部署计划作业以分析文件并进行转换以供业务使用。 无服务器体系结构让作业变得更加简单，因为触发器可能会在上传文件时触发。 Azure Functions 通过重点关注特定问题的一小部分代码的理想构成处理 ETL 等任务。

![显示 csv 分析进程的屏幕截图。](./media/serverless-business-scenarios/csv-parse-database-import.png)

有关源代码和动手实验，请参阅 [CSV 导入实验室](https://github.com/JeremyLikness/azure-fn-file-process-hol)。

## <a name="shorten-links-and-track-metrics"></a>缩短链接和跟踪指标

链接缩短工具最初帮助编码缩短 Twitter 帖子中的 URL，以适应 140 字符的限制。 它们已发展为包含多种用途，最常见的是跟踪点击以供分析。 链接缩短符方案是一个完全无服务器的应用程序，用于管理链接和报告指标。

Azure Functions 用于提供单个页面应用程序 (SPA)，此应用程序允许粘贴长 URL 并生成短 URL。 标记 URL 以跟踪活动（主题）和媒体（如向其发布链接的社交网络）等。 短代码作为密钥存储在 Azure 表存储中，长 URL 为值。 单击短链接时，另一个函数查找长 URL，发送重定向，并将事件相关信息放置在队列中。 另一个 Azure 函数处理队列，并将信息放入 Azure Cosmos DB。

![链接缩短符体系结构](./media/link-shortener-architecture.png)

然后，你可以创建一个 Power BI 仪表板，以便收集对收集到的数据的见解。 在后端，Application Insights 提供重要指标。 遥测包括平均用户重定向花费的时间以及访问 Azure 表存储所用的时间。

![Power BI 示例](./media/power-bi-example.png)

此处提供带说明的完整链接缩短符存储库：[无服务器 URL 缩短符](https://github.com/jeremylikness/serverless-url-shortener)。 可以在此处阅读简化版本：[数分钟即可为无服务器 .NET 应用实现 Azure 存储](https://devblogs.microsoft.com/aspnet/azure-storage-for-serverless-net-apps-in-minutes/)。

## <a name="verify-device-connectivity-using-a-ping"></a>使用 ping 确认设备连接

此示例包含 Azure IoT 中心和 Azure 函数。 IoT 中心上的新消息将触发 Azure 函数。 无服务器代码会将相同的消息内容发送回发送设备。 项目具有解决方案所需的所有代码和部署配置。

有关详细信息，请参阅 [Azure IoT 中心 ping](https://github.com/Azure-Samples/iot-hub-node-ping)。

## <a name="recommended-resources"></a>推荐的资源

- [Azure Functions 照片马赛克生成器](https://github.com/Azure-Samples/functions-dotnet-photo-mosaic)
- [Azure IoT 中心 ping](https://github.com/Azure-Samples/iot-hub-node-ping)
- [数分钟即可为无服务器 .NET 应用实现 Azure 存储](https://devblogs.microsoft.com/aspnet/azure-storage-for-serverless-net-apps-in-minutes/)
- [自带应用](https://github.com/JeremyLikness/bring-own-app-connect-17)
- [CSV 导入实验室](https://github.com/JeremyLikness/azure-fn-file-process-hol)
- [事件网格粘附](https://github.com/JeremyLikness/Event-Grid-Glue)
- [通过 Xamarin.Forms 客户端执行单个 Azure 函数](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)
- [使用无服务器 Azure 函数直接迁移](https://channel9.msdn.com/Events/Connect/2017/E102)
- [无服务器 URL 缩短符](https://github.com/jeremylikness/serverless-url-shortener)

>[!div class="step-by-step"]
>[上一页](orchestration-patterns.md)
>[下一页](serverless-conclusion.md)
