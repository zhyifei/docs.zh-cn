---
title: 如何：生成 EntityConnection 连接字符串
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5bd1a748-3df7-4d0a-a607-14f25e3175e9
ms.openlocfilehash: 335c85d5234df4dd00d0ee65b2077996411081b3
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335675"
---
# <a name="how-to-build-an-entityconnection-connection-string"></a>如何：生成 EntityConnection 连接字符串
本主题提供有关如何生成 <xref:System.Data.EntityClient.EntityConnection> 的示例。  
  
### <a name="to-run-the-code-in-this-example"></a>运行本示例中的代码  
  
1. 添加[AdventureWorks 销售模型](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)到你的项目和配置项目以使用[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]。 有关详细信息，请参阅[如何：使用实体数据模型向导](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))。  
  
2. 在应用程序的代码页中，添加以下 `using` 语句（在 Visual Basic 中为 `Imports`）：  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>示例  
 以下示例初始化基础提供程序的 <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType>，然后初始化 <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType> 对象并将此对象传递给 <xref:System.Data.EntityClient.EntityConnection> 的构造函数。  
  
 [!code-csharp[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#buildingconnectionstringwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#buildingconnectionstringwithentitycommand)]  
  
## <a name="see-also"></a>请参阅

- [如何：将 EntityConnection 与对象上下文](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738461(v=vs.100))
- [用于实体框架的 EntityClient 提供程序](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
