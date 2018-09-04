---
title: 示例提供程序中的 SQL 生成
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: cba1cec6d7ef0fdf8d4d4cf6c8e44fb325cf6447
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43556200"
---
# <a name="sql-generation-in-the-sample-provider"></a>示例提供程序中的 SQL 生成
[实体框架示例提供程序](https://go.microsoft.com/fwlink/?LinkId=180616)演示了 ADO.NET 数据提供程序支持的新组件[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]。  它使用 SQL Server 2005 数据库，并实现为 System.Data.SqlClient ADO.NET 2.0 数据提供程序的一个包装。  
  
 该示例提供程序的 SQL 生成模块（位于 SQL Generation 文件夹下，不包括 DmlSqlGenerator.cs 文件）采用一个输入 DbQueryCommandTree，并且生成单个 SQL SELECT 语句。  
  
## <a name="in-this-section"></a>本节内容  
 本节包括下列主题：  
  
 [体系结构和设计](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [演练：SQL 生成](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a>请参阅  
 [SQL 生成](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
