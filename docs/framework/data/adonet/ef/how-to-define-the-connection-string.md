---
title: 如何：定义连接字符串
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 7fb722acbb13b3502d004978581701cc70118ff8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61606097"
---
# <a name="how-to-define-the-connection-string"></a><span data-ttu-id="0ce4b-102">如何：定义连接字符串</span><span class="sxs-lookup"><span data-stu-id="0ce4b-102">How to: Define the Connection String</span></span>

<span data-ttu-id="0ce4b-103">本主题介绍如何定义在连接到概念模型时使用的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="0ce4b-103">This topic shows how to define the connection string that is used when connecting to a conceptual model.</span></span> <span data-ttu-id="0ce4b-104">本主题基于[AdventureWorks 销售](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100))概念模型。</span><span class="sxs-lookup"><span data-stu-id="0ce4b-104">This topic is based on the [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) conceptual model.</span></span> <span data-ttu-id="0ce4b-105">AdventureWorks 销售模型将在 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 文档的与任务相关的所有主题中使用。</span><span class="sxs-lookup"><span data-stu-id="0ce4b-105">The AdventureWorks Sales Model is used throughout the task-related topics in the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] documentation.</span></span> <span data-ttu-id="0ce4b-106">本主题假定你已配置[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]和定义 AdventureWorks 销售模型。</span><span class="sxs-lookup"><span data-stu-id="0ce4b-106">This topic assumes that you have already configured the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] and defined the AdventureWorks Sales Model.</span></span> <span data-ttu-id="0ce4b-107">有关详细信息，请参阅[如何：手动定义模型和映射文件](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="0ce4b-107">For more information, see [How to: Manually Define the Model and Mapping Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span></span> <span data-ttu-id="0ce4b-108">本主题中的过程也包括在[如何：手动配置实体框架项目](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="0ce4b-108">The procedures in this topic are also included in [How to: Manually Configure an Entity Framework Project](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="0ce4b-109">如果您使用[!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)]向导在 Visual Studio 项目中，会自动生成.edmx 文件和配置项目以使用[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0ce4b-109">If you use the [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] Wizard in a Visual Studio project, it automatically generates an .edmx file and configures the project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="0ce4b-110">有关详细信息，请参阅[如何：使用实体数据模型向导](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0ce4b-110">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))</span></span>

## <a name="to-define-the-entity-framework-connection-string"></a><span data-ttu-id="0ce4b-111">定义实体框架连接字符串</span><span class="sxs-lookup"><span data-stu-id="0ce4b-111">To define the Entity Framework connection string</span></span>

- <span data-ttu-id="0ce4b-112">打开项目的应用程序配置文件 (app.config) 并添加以下连接字符串：</span><span class="sxs-lookup"><span data-stu-id="0ce4b-112">Open the project's application configuration file (app.config) and add the following connection string:</span></span>

```xml
<connectionStrings>
    <add name="AdventureWorksEntities" 
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

<span data-ttu-id="0ce4b-113">如果你的项目不具有应用程序配置文件，则可以添加一个通过选择**添加新项**从**项目**菜单中，选择**常规**类别中，选择**应用程序配置文件**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="0ce4b-113">If your project does not have an application configuration file, you can add one by selecting **Add New Item** from the **Project** menu, selecting the **General** category, selecting **Application Configuration File**, and then clicking **Add**.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ce4b-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ce4b-114">See also</span></span>

- <span data-ttu-id="0ce4b-115">[快速入门](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0ce4b-115">[Quickstart](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span></span>
- <span data-ttu-id="0ce4b-116">[如何：创建新的.edmx 文件](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0ce4b-116">[How to: Create a New .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span></span>
- <span data-ttu-id="0ce4b-117">[ADO.NET 实体数据模型工具](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0ce4b-117">[ADO.NET Entity Data Model  Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
