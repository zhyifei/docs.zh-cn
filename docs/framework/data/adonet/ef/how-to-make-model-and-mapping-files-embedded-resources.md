---
title: 如何：创建模型及映射文件嵌入资源
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: 7827ecce0fe7f5c21291d3ba2edd925c6a8e5960
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826520"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="441fd-102">如何：创建模型及映射文件嵌入资源</span><span class="sxs-lookup"><span data-stu-id="441fd-102">How to: Make Model and Mapping Files Embedded Resources</span></span>
<span data-ttu-id="441fd-103">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] ，你可以为应用程序的嵌入资源部署模型和映射文件。</span><span class="sxs-lookup"><span data-stu-id="441fd-103">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="441fd-104">包含嵌入模型和映射文件的程序集必须加载到实体连接所在的应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="441fd-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="441fd-105">有关详细信息，请参阅[连接字符串](../../../../../docs/framework/data/adonet/ef/connection-strings.md)。</span><span class="sxs-lookup"><span data-stu-id="441fd-105">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span> <span data-ttu-id="441fd-106">默认情况下，[!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)]工具嵌入模型和映射文件。</span><span class="sxs-lookup"><span data-stu-id="441fd-106">By default, the [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] tools embed the model and mapping files.</span></span> <span data-ttu-id="441fd-107">手动定义模型和映射文件时，请使用下面的过程以确保文件作为嵌入资源与[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]应用程序一起部署。</span><span class="sxs-lookup"><span data-stu-id="441fd-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="441fd-108">若要维护嵌入资源，每次修改模型和映射文件时都必须重复此过程。</span><span class="sxs-lookup"><span data-stu-id="441fd-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="441fd-109">嵌入模型和映射文件</span><span class="sxs-lookup"><span data-stu-id="441fd-109">To embed model and mapping files</span></span>  
  
1.  <span data-ttu-id="441fd-110">在中**解决方案资源管理器**，选择的概念 (.csdl) 文件。</span><span class="sxs-lookup"><span data-stu-id="441fd-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2.  <span data-ttu-id="441fd-111">在中**属性**窗格中，设置**生成操作**到**嵌入的资源**。</span><span class="sxs-lookup"><span data-stu-id="441fd-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3.  <span data-ttu-id="441fd-112">对存储文件 (.ssdl) 和映射文件 (.msl) 重复步骤 1 和步骤 2。</span><span class="sxs-lookup"><span data-stu-id="441fd-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4.  <span data-ttu-id="441fd-113">在中**解决方案资源管理器**，双击 App.config 文件，然后修改`Metadata`中的参数`connectionString`属性基于以下格式之一：</span><span class="sxs-lookup"><span data-stu-id="441fd-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    -   <span data-ttu-id="441fd-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="441fd-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span></span>  
  
    -   <span data-ttu-id="441fd-115">`Metadata=` `res://*/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="441fd-115">`Metadata=` `res://*/<resourceName>;`</span></span>  
  
    -   `Metadata=res://*;`  
  
     <span data-ttu-id="441fd-116">有关详细信息，请参阅[连接字符串](../../../../../docs/framework/data/adonet/ef/connection-strings.md)。</span><span class="sxs-lookup"><span data-stu-id="441fd-116">For more information, see [Connection Strings](../../../../../docs/framework/data/adonet/ef/connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="441fd-117">示例</span><span class="sxs-lookup"><span data-stu-id="441fd-117">Example</span></span>  
 <span data-ttu-id="441fd-118">下面的连接字符串引用嵌入的模型和映射文件[AdventureWorks 销售模型](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)。</span><span class="sxs-lookup"><span data-stu-id="441fd-118">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="441fd-119">该连接字符串存储在项目的 App.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="441fd-119">This connection string is stored in the project's App.config file.</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="441fd-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="441fd-120">See also</span></span>
- [<span data-ttu-id="441fd-121">建模和映射</span><span class="sxs-lookup"><span data-stu-id="441fd-121">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [<span data-ttu-id="441fd-122">如何：定义连接字符串</span><span class="sxs-lookup"><span data-stu-id="441fd-122">How to: Define the Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)
- [<span data-ttu-id="441fd-123">如何：生成 EntityConnection 连接字符串</span><span class="sxs-lookup"><span data-stu-id="441fd-123">How to: Build an EntityConnection Connection String</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)
- <span data-ttu-id="441fd-124">[ADO.NET 实体数据模型工具](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="441fd-124">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
