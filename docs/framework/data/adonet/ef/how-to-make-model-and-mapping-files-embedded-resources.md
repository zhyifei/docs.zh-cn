---
title: 如何：创建模型及映射文件嵌入资源
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: c88e0c09742d76c7508d7d782eabbe46035d3501
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251449"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a>如何：创建模型及映射文件嵌入资源
[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]利用，你可以将模型和映射文件部署为应用程序的嵌入资源。 包含嵌入模型和映射文件的程序集必须加载到实体连接所在的应用程序域中。 有关详细信息，请参阅[连接字符串](connection-strings.md)。 默认情况下，实体数据模型工具嵌入模型和映射文件。 手动定义模型和映射文件时，请使用下面的过程以确保文件作为嵌入资源与[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]应用程序一起部署。  
  
> [!NOTE]
> 若要维护嵌入资源，每次修改模型和映射文件时都必须重复此过程。  
  
### <a name="to-embed-model-and-mapping-files"></a>嵌入模型和映射文件  
  
1. 在**解决方案资源管理器**中，选择概念（csdl）文件。  
  
2. 在 "**属性**" 窗格中，将 "**生成操作**" 设置为 "**嵌入资源**"。  
  
3. 对存储文件 (.ssdl) 和映射文件 (.msl) 重复步骤 1 和步骤 2。  
  
4. 在**解决方案资源管理器**中，双击 app.config 文件，然后根据以下格式之一修改`Metadata` `connectionString`属性中的参数：  
  
    - `Metadata=` `res://<assemblyFullName>/<resourceName>;`  
  
    - `Metadata=` `res://*/<resourceName>;`  
  
    - `Metadata=res://*;`  
  
     有关详细信息，请参阅[连接字符串](connection-strings.md)。  
  
## <a name="example"></a>示例  
 下面的连接字符串引用[AdventureWorks 销售模型](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)的嵌入模型和映射文件。 该连接字符串存储在项目的 App.config 文件中。  

## <a name="see-also"></a>请参阅

- [建模和映射](modeling-and-mapping.md)
- [如何：定义连接字符串](how-to-define-the-connection-string.md)
- [如何：生成 EntityConnection 连接字符串](how-to-build-an-entityconnection-connection-string.md)
- [ADO.NET 实体数据模型工具](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
