---
title: "如何：定义连接字符串"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 355d313fd607ccf85ba55b09b9ece4d9c88e298f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-define-the-connection-string"></a><span data-ttu-id="bdaf6-102">如何：定义连接字符串</span><span class="sxs-lookup"><span data-stu-id="bdaf6-102">How to: Define the Connection String</span></span>
<span data-ttu-id="bdaf6-103">本主题介绍如何定义在连接到概念模型时使用的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="bdaf6-103">This topic shows how to define the connection string that is used when connecting to a conceptual model.</span></span> <span data-ttu-id="bdaf6-104">本主题基于[AdventureWorks 销售](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832)概念模型。</span><span class="sxs-lookup"><span data-stu-id="bdaf6-104">This topic is based on the [AdventureWorks Sales](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) conceptual model.</span></span> <span data-ttu-id="bdaf6-105">AdventureWorks 销售模型将在 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 文档的与任务相关的所有主题中使用。</span><span class="sxs-lookup"><span data-stu-id="bdaf6-105">The AdventureWorks Sales Model is used throughout the task-related topics in the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] documentation.</span></span> <span data-ttu-id="bdaf6-106">本主题假定你已配置[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]和定义 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="bdaf6-106">This topic assumes that you have already configured the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] and defined the AdventureWorks Sales Model.</span></span> <span data-ttu-id="bdaf6-107">有关详细信息，请参阅[如何： 手动定义模型和映射文件](http://msdn.microsoft.com/library/d4fd6864-f2a1-48f0-aa32-1e318775a99a)。</span><span class="sxs-lookup"><span data-stu-id="bdaf6-107">For more information, see [How to: Manually Define the Model and Mapping Files](http://msdn.microsoft.com/library/d4fd6864-f2a1-48f0-aa32-1e318775a99a).</span></span> <span data-ttu-id="bdaf6-108">本主题中的过程也包括在[如何： 手动配置实体框架项目](http://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)。</span><span class="sxs-lookup"><span data-stu-id="bdaf6-108">The procedures in this topic are also included in [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bdaf6-109">如果在 [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] 项目中使用[!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)]向导，则该向导将自动生成 .edmx 文件并将该项目配置为使用[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bdaf6-109">If you use the [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] Wizard in a [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] project, it automatically generates an .edmx file and configures the project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="bdaf6-110">有关详细信息，请参阅[如何： 使用实体数据模型向导](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)</span><span class="sxs-lookup"><span data-stu-id="bdaf6-110">For more information, see [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)</span></span>  
  
### <a name="to-define-the-entity-framework-connection-string"></a><span data-ttu-id="bdaf6-111">定义实体框架连接字符串</span><span class="sxs-lookup"><span data-stu-id="bdaf6-111">To define the Entity Framework connection string</span></span>  
  
-   <span data-ttu-id="bdaf6-112">打开项目的应用程序配置文件 (app.config) 并添加以下连接字符串：</span><span class="sxs-lookup"><span data-stu-id="bdaf6-112">Open the project's application configuration file (app.config) and add the following connection string:</span></span>  
  
  
  
     <span data-ttu-id="bdaf6-113">如果你的项目不具有应用程序配置文件，则可以添加一个，方法是选择**添加新项**从**项目**菜单上，选择**常规**类别中，选择**应用程序配置文件**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="bdaf6-113">If your project does not have an application configuration file, you can add one by selecting **Add New Item** from the **Project** menu, selecting the **General** category, selecting **Application Configuration File**, and then clicking **Add**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdaf6-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="bdaf6-114">See Also</span></span>  
 [<span data-ttu-id="bdaf6-115">快速入门</span><span class="sxs-lookup"><span data-stu-id="bdaf6-115">Quickstart</span></span>](http://msdn.microsoft.com/library/0bc534be-789f-4819-b9f6-76e51d961675)  
 [<span data-ttu-id="bdaf6-116">如何： 创建新的.edmx 文件</span><span class="sxs-lookup"><span data-stu-id="bdaf6-116">How to: Create a New .edmx File</span></span>](http://msdn.microsoft.com/library/beb8189e-e51c-4051-839c-9902c224abf2)  
 [<span data-ttu-id="bdaf6-117">ADO.NET 实体数据模型工具</span><span class="sxs-lookup"><span data-stu-id="bdaf6-117">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
