---
title: SQL Server Compact 与 LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: b5a1a12018bd85cf313c1841e6b67ab2edf67b4a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792531"
---
# <a name="sql-server-compact-and-linq-to-sql"></a>SQL Server Compact 与 LINQ to SQL
SQL Server Compact 是随 Visual Studio 一起安装的默认数据库。 有关详细信息，请参阅[Using SQL Server Compact （Visual Studio）](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110))。  
  
 本主题概述了使用情况、配置、功能集和[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]支持范围的主要区别。  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a>SQL Server Compact 相对于 LINQ to SQL 的特性  
 默认情况下，为所有 Visual Studio 版本安装 SQL Server Compact，因此在开发计算机[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]上可用于的。 但是，部署使用 SQL Server Compact 和[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]的应用程序不同于 SQL Server 应用程序的应用程序。 SQL Server Compact 不是 .NET Framework 的一部分，因此必须与应用程序一起打包或单独从 Microsoft 网站下载。  
  
 请注意下列特性：  
  
- SQL Server Compact 打包为可直接对数据库文件（扩展名为 .sdf）使用的 DLL。  
  
- SQL Server Compact 在与客户端应用程序相同的进程中运行。 因此，与 SQL Server Compact 通信相比，可以大大提高与 SQL Server 通信的效率。 另一方面，SQL Server Compact 需要托管代码与非托管代码之间的互操作性，以及其助理成本。  
  
- SQL Server Compact DLL 的大小很小。 这一特征减小了应用程序的总大小。  
  
- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 运行时和 SQLMetal 命令行工具支持 SQL Server Compact。  
  
- 对象关系设计器不支持 SQL Server Compact。  
  
## <a name="feature-set"></a>功能集  
 SQL Server Compact 功能集比 SQL Server 功能集简单得多，这种方法可影响[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]应用程序：  
  
- SQL Server Compact 不支持存储过程或视图。  
  
- SQL Server Compact 仅支持部分数据类型和 SQL 函数。  
  
- SQL Server Compact 仅支持部分 SQL 构造。  
  
- SQL Server Compact 仅提供具有最基本功能的优化器。 有些查询可能会超时。  
  
- SQL Server Compact 不支持部分信任。  
  
## <a name="see-also"></a>请参阅

- [引用](reference.md)
