---
title: Azure 逻辑应用-无服务器应用
description: Azure 逻辑应用可以生成自动将应用集成的可缩放工作流和跨云数据服务，并在本地系统。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 14670a8459db3b80b8fbe3139c2675321cf9592c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53147938"
---
# <a name="azure-logic-apps"></a><span data-ttu-id="2d9c8-103">Azure 逻辑应用</span><span class="sxs-lookup"><span data-stu-id="2d9c8-103">Azure Logic Apps</span></span>

<span data-ttu-id="2d9c8-104">[Azure 逻辑应用](https://docs.microsoft.com/azure/logic-apps)提供无服务器引擎生成自动化工作流以将应用程序和云服务之间的数据集成，并在本地系统。</span><span class="sxs-lookup"><span data-stu-id="2d9c8-104">[Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps) provides a serverless engine to build automated workflows to integrate apps and data between cloud services and on-premises systems.</span></span> <span data-ttu-id="2d9c8-105">生成工作流使用可视化设计器。</span><span class="sxs-lookup"><span data-stu-id="2d9c8-105">You build workflows using a visual designer.</span></span> <span data-ttu-id="2d9c8-106">可以触发基于事件或计时器和利用连接器再到集成应用程序的工作流，并促进企业到企业 (B2B) 通信。</span><span class="sxs-lookup"><span data-stu-id="2d9c8-106">You can trigger workflows based on events or timers and leverage connectors to integration applications and facilitate business-to-business (B2B) communication.</span></span> <span data-ttu-id="2d9c8-107">逻辑应用与 Azure Functions 无缝集成。</span><span class="sxs-lookup"><span data-stu-id="2d9c8-107">Logic Apps integrates seamlessly with Azure Functions.</span></span>

![Azure 逻辑应用徽标](./media/logic-apps-logo.png)

<span data-ttu-id="2d9c8-109">个以上的只是连接云服务 （例如函数） 为逻辑应用可以使用云资源 （如队列和数据库）。</span><span class="sxs-lookup"><span data-stu-id="2d9c8-109">Logic Apps can do more than just connect your cloud services (like functions) with cloud resources (like queues and databases).</span></span> <span data-ttu-id="2d9c8-110">此外可以安排在本地与在本地网关的工作流。</span><span class="sxs-lookup"><span data-stu-id="2d9c8-110">You can also orchestrate on-premises workflows with the on-premises gateway.</span></span> <span data-ttu-id="2d9c8-111">例如，可以使用逻辑应用中触发对基于云的事件作出响应的本地 SQL 存储过程或在工作流中的条件逻辑。</span><span class="sxs-lookup"><span data-stu-id="2d9c8-111">For example, you can use the Logic App to trigger an on-premises SQL stored procedure in response to a cloud-based event or conditional logic in your workflow.</span></span> <span data-ttu-id="2d9c8-112">详细了解如何[连接到使用 Azure 本地数据网关的本地数据源](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)。</span><span class="sxs-lookup"><span data-stu-id="2d9c8-112">Learn more about [Connecting to on-premises data sources with Azure On-premises Data Gateway](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).</span></span>

![逻辑应用体系结构](./media/logic-apps-architecture.png)

<span data-ttu-id="2d9c8-114">Azure Functions 等启动逻辑应用工作流分别具有一个触发器。</span><span class="sxs-lookup"><span data-stu-id="2d9c8-114">Like Azure Functions, you kick off Logic App workflows with a trigger.</span></span> <span data-ttu-id="2d9c8-115">有许多触发器，以便从中进行选择。</span><span class="sxs-lookup"><span data-stu-id="2d9c8-115">There are many triggers for you to choose from.</span></span> <span data-ttu-id="2d9c8-116">以下截图显示了一些更受欢迎的外出时的数百个可用。</span><span class="sxs-lookup"><span data-stu-id="2d9c8-116">The following capture shows just a few of the more popular ones out of hundreds that are available.</span></span>

![逻辑应用触发器](./media/logic-app-triggers.png)

<span data-ttu-id="2d9c8-118">应用程序触发后，可以使用可视化设计器生成步骤、 循环、 条件和操作。</span><span class="sxs-lookup"><span data-stu-id="2d9c8-118">Once the app is triggered, you can use the visual designer to build out steps, loops, conditions, and actions.</span></span> <span data-ttu-id="2d9c8-119">可为你在后续步骤中使用上一步中引入的任何数据。</span><span class="sxs-lookup"><span data-stu-id="2d9c8-119">Any data ingested in a previous step is available for you to use in subsequent steps.</span></span> <span data-ttu-id="2d9c8-120">下面的工作流从 CosmosDB 数据库加载 Url。</span><span class="sxs-lookup"><span data-stu-id="2d9c8-120">The following workflow loads URLs from a CosmosDB database.</span></span> <span data-ttu-id="2d9c8-121">它找到的主机具有`t.co`搜索 Twitter 它们。</span><span class="sxs-lookup"><span data-stu-id="2d9c8-121">It finds the ones with a host of `t.co` then searches for them on Twitter.</span></span> <span data-ttu-id="2d9c8-122">如果找到相应的推文，它更新文档的相关推文通过调用一个函数。</span><span class="sxs-lookup"><span data-stu-id="2d9c8-122">If it finds corresponding tweets, it updates the documents with the related tweets by calling a function.</span></span>

![逻辑应用工作流](./media/logic-app-workflow.png)

<span data-ttu-id="2d9c8-124">逻辑应用仪表板显示正在运行的工作流和是否每个运行已完成，不论成功与否的历史记录。</span><span class="sxs-lookup"><span data-stu-id="2d9c8-124">The Logic Apps dashboard shows the history of running your workflows and whether each run completed successfully or not.</span></span> <span data-ttu-id="2d9c8-125">可以导航到任何给定运行并检查每个步骤用于故障排除的数据。</span><span class="sxs-lookup"><span data-stu-id="2d9c8-125">You can navigate into any given run and inspect the data used by each step for troubleshooting.</span></span> <span data-ttu-id="2d9c8-126">逻辑应用还提供了你可以编辑，但非常适用于复杂的企业工作流的现有模板。</span><span class="sxs-lookup"><span data-stu-id="2d9c8-126">Logic Apps also provides existing templates you can edit and are well suited for complex enterprise workflows.</span></span>

<span data-ttu-id="2d9c8-127">若要了解详细信息，请参阅[Azure 逻辑应用](https://docs.microsoft.com/azure/logic-apps)。</span><span class="sxs-lookup"><span data-stu-id="2d9c8-127">To learn more, see [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2d9c8-128">[上一页](application-insights.md)
>[下一页](event-grid.md)</span><span class="sxs-lookup"><span data-stu-id="2d9c8-128">[Previous](application-insights.md)
[Next](event-grid.md)</span></span>