---
title: "示例提供程序中的 SQL 生成"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 58a49f7bf5d385466810a3c59bda748ef66d5840
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="sql-generation-in-the-sample-provider"></a>示例提供程序中的 SQL 生成
[实体框架示例提供程序](http://go.microsoft.com/fwlink/?LinkId=180616)演示的 ADO.NET 数据提供程序支持的新组件[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]。  它使用 SQL Server 2005 数据库，并实现为 System.Data.SqlClient ADO.NET 2.0 数据提供程序的一个包装。  
  
 该示例提供程序的 SQL 生成模块（位于 SQL Generation 文件夹下，不包括 DmlSqlGenerator.cs 文件）采用一个输入 DbQueryCommandTree，并且生成单个 SQL SELECT 语句。  
  
## <a name="in-this-section"></a>本节内容  
 本节包括下列主题：  
  
 [体系结构和设计](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [演练： SQL 生成](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a>另请参阅  
 [SQL 生成](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
