---
title: 如何：创建模型及映射文件嵌入资源
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: 53817498f6d772c308888c5e994fb25239c4ed61
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949748"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="833f3-102">如何：创建模型及映射文件嵌入资源</span><span class="sxs-lookup"><span data-stu-id="833f3-102">How to: Make Model and Mapping Files Embedded Resources</span></span>
<span data-ttu-id="833f3-103">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]利用, 你可以将模型和映射文件部署为应用程序的嵌入资源。</span><span class="sxs-lookup"><span data-stu-id="833f3-103">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="833f3-104">包含嵌入模型和映射文件的程序集必须加载到实体连接所在的应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="833f3-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="833f3-105">有关详细信息，请参阅[连接字符串](../../../../../docs/framework/data/adonet/ef/connection-strings.md)。</span><span class="sxs-lookup"><span data-stu-id="833f3-105">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span> <span data-ttu-id="833f3-106">默认情况下, 实体数据模型工具嵌入模型和映射文件。</span><span class="sxs-lookup"><span data-stu-id="833f3-106">By default, the Entity Data Model tools embed the model and mapping files.</span></span> <span data-ttu-id="833f3-107">手动定义模型和映射文件时，请使用下面的过程以确保文件作为嵌入资源与[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]应用程序一起部署。</span><span class="sxs-lookup"><span data-stu-id="833f3-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="833f3-108">若要维护嵌入资源，每次修改模型和映射文件时都必须重复此过程。</span><span class="sxs-lookup"><span data-stu-id="833f3-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="833f3-109">嵌入模型和映射文件</span><span class="sxs-lookup"><span data-stu-id="833f3-109">To embed model and mapping files</span></span>  
  
1. <span data-ttu-id="833f3-110">在**解决方案资源管理器**中, 选择概念 (csdl) 文件。</span><span class="sxs-lookup"><span data-stu-id="833f3-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2. <span data-ttu-id="833f3-111">在 "**属性**" 窗格中, 将 "**生成操作**" 设置为 "**嵌入资源**"。</span><span class="sxs-lookup"><span data-stu-id="833f3-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3. <span data-ttu-id="833f3-112">对存储文件 (.ssdl) 和映射文件 (.msl) 重复步骤 1 和步骤 2。</span><span class="sxs-lookup"><span data-stu-id="833f3-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4. <span data-ttu-id="833f3-113">在**解决方案资源管理器**中, 双击 app.config 文件, 然后根据以下格式之一修改`Metadata` `connectionString`属性中的参数:</span><span class="sxs-lookup"><span data-stu-id="833f3-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    - <span data-ttu-id="833f3-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="833f3-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span></span>  
  
    - <span data-ttu-id="833f3-115">`Metadata=` `res://*/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="833f3-115">`Metadata=` `res://*/<resourceName>;`</span></span>  
  
    - `Metadata=res://*;`  
  
     <span data-ttu-id="833f3-116">有关详细信息，请参阅[连接字符串](../../../../../docs/framework/data/adonet/ef/connection-strings.md)。</span><span class="sxs-lookup"><span data-stu-id="833f3-116">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="833f3-117">示例</span><span class="sxs-lookup"><span data-stu-id="833f3-117">Example</span></span>  
 <span data-ttu-id="833f3-118">下面的连接字符串引用[AdventureWorks 销售模型](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)的嵌入模型和映射文件。</span><span class="sxs-lookup"><span data-stu-id="833f3-118">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="833f3-119">该连接字符串存储在项目的 App.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="833f3-119">This connection string is stored in the project's App.config file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="833f3-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="833f3-120">See also</span></span>

- [<span data-ttu-id="833f3-121">建模和映射</span><span class="sxs-lookup"><span data-stu-id="833f3-121">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [<span data-ttu-id="833f3-122">如何：定义连接字符串</span><span class="sxs-lookup"><span data-stu-id="833f3-122">How to: Define the Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)
- [<span data-ttu-id="833f3-123">如何：生成 EntityConnection 连接字符串</span><span class="sxs-lookup"><span data-stu-id="833f3-123">How to: Build an EntityConnection Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)
- <span data-ttu-id="833f3-124">[ADO.NET 实体数据模型工具](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="833f3-124">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
