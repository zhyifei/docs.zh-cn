---
title: 编写实体框架数据提供程序
ms.date: 03/30/2017
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
ms.openlocfilehash: 29aa8cb1c6b31d9ada6b01860d76bcf03d37416c
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854158"
---
# <a name="writing-an-entity-framework-data-provider"></a>编写实体框架数据提供程序
本部分讨论如何编写实体框架提供程序以支持除 SQL Server 之外的数据源。 实体框架包含支持 SQL Server 的访问接口。  
  
## <a name="introducing-the-entity-framework-provider-model"></a>实体框架提供程序模型简介  
 实体框架是独立于数据库的，你可以使用 ADO.NET 提供程序模型来编写提供程序，以便连接到一组不同的数据源。  
  
 实体框架数据提供程序（通过使用 ADO.NET 数据提供程序模型构建）具有下列功能：  
  
- 将实体数据模型 (EDM) 基元类型映射到提供程序类型。  
  
- 公开提供程序特定的函数。  
  
- 为给定的 DbQueryCommandTree 生成特定于提供程序的命令，以支持实体框架查询。  
  
- 为给定 DbModificationCommandTree 生成特定于提供程序的更新命令，以支持通过实体框架更新。  
  
- 公开存储架构定义的映射文件以支持基于数据库的模型生成。  
  
- 通过概念模型公开元数据（例如，表和视图）。  
  
 ![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](./media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")  
  
## <a name="sample"></a>示例  
 有关支持除 SQL Server 之外的数据源的实体框架提供程序的示例，请参阅[实体框架示例提供程序](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0)。  
  
## <a name="in-this-section"></a>本节内容  
 [SQL 生成](sql-generation.md)  
  
 [修改 SQL 生成](modification-sql-generation.md)  
  
 [提供程序清单规范](provider-manifest-specification.md)  
  
## <a name="see-also"></a>请参阅

- [使用数据提供程序](working-with-data-providers.md)
