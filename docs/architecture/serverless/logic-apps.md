---
title: Azure 逻辑应用-无服务器应用
description: Azure 逻辑应用支持构建可跨云服务和本地系统集成应用和数据的自动可扩展工作流。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7ece3d30209713d42ee44ef9c1be1cf0fe82464a
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577450"
---
# <a name="azure-logic-apps"></a>Azure 逻辑应用

[Azure 逻辑应用](https://docs.microsoft.com/azure/logic-apps)提供无服务器引擎来构建自动化工作流, 以便在云服务和本地系统之间集成应用和数据。 使用可视化设计器生成工作流。 你可以基于事件或计时器触发工作流, 并利用连接器来集成应用程序并促进企业到企业 (B2B) 通信。 逻辑应用与 Azure Functions 无缝集成。

![Azure 逻辑应用徽标](./media/logic-apps-logo.png)

逻辑应用只需将云服务 (如功能) 与云资源 (如队列和数据库) 连接即可完成。 还可以通过本地网关协调本地工作流。 例如, 可以使用逻辑应用来触发本地 SQL 存储过程, 以响应工作流中基于云的事件或条件逻辑。 详细了解[如何通过 Azure 本地数据网关连接到本地数据源](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)。

![逻辑应用体系结构](./media/logic-apps-architecture.png)

与 Azure Functions 一样, 你可以使用触发器启动逻辑应用工作流。 有很多可供选择的触发器。 以下捕获只显示数以百计的数百个更常用的文件。

![逻辑应用触发器](./media/logic-app-triggers.png)

触发应用后, 可以使用可视化设计器来构建步骤、循环、条件和操作。 可在后续步骤中使用上一步中的任何数据引入。 以下工作流从 CosmosDB 数据库加载 Url。 它会查找具有的主机`t.co` , 然后在 Twitter 上搜索它们。 如果找到相应的推文, 它将通过调用函数来更新具有相关推文的文档。

![逻辑应用工作流](./media/logic-app-workflow.png)

逻辑应用仪表板显示运行工作流的历史记录, 以及每个运行是否已成功完成。 你可以导航到任何给定的运行, 并检查每个步骤使用的数据以进行故障排除。 逻辑应用还提供了可以编辑并非常适合复杂企业工作流的现有模板。

若要了解详细信息, 请参阅[Azure 逻辑应用](https://docs.microsoft.com/azure/logic-apps)。

>[!div class="step-by-step"]
>[上一页](application-insights.md)
>[下一页](event-grid.md)
