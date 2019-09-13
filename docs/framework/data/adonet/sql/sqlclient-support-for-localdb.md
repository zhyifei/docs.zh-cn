---
title: SqlClient 对 LocalDB 的支持
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: d02524cd5901adeca7bc36d6fd13c7abdc46c69b
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894399"
---
# <a name="sqlclient-support-for-localdb"></a>SqlClient 对 LocalDB 的支持
从 SQL Server 代码名称 Denali 开始，将提供 SQL Server 的轻型版本（称为 LocalDB）。 本主题讨论如何连接到 LocalDB 数据库。  
  
## <a name="remarks"></a>备注  
 有关 LocalDB 的详细信息，包括如何安装 LocalDB 和配置 LocalDB 实例，请参阅 SQL Server 联机丛书。  
  
 以下汇总了使用 LocalDB 可以执行的操作：  
  
- 使用 sqllocaldb.exe 或 app.config 文件创建和启动 LocalDB 实例。  
  
- 使用 sqlcmd.exe 添加和修改 LocalDB 实例中的数据库。 例如 `sqlcmd -S (localdb)\myinst`。  
  
- 使用 `AttachDBFilename` 连接字符串关键字将数据库添加到 LocalDB 实例。 使用 `AttachDBFilename`时，如果不使用 `Database` 连接字符串关键字指定数据库的名称，则在应用程序关闭时，将从 LocalDB 实例中删除数据库。  
  
- 在连接字符串中指定 LocalDB 实例。 例如，如果实例名称是 `myInstance`，连接字符串将包括：  
  
    `server=(localdb)\\myInstance`  
  
 连接到 LocalDB 数据库时，不允许`User Instance=True` 。  
  
 可以从 [Microsoft SQL Server 2012 功能包](https://www.microsoft.com/download/en/details.aspx?id=29065)下载 LocalDB。 如果你将使用 sqlcmd 来修改 LocalDB 实例中的数据，则你将需要来自 SQL Server 2012 的 sqlcmd，也可以从 SQL Server 2012 功能包获取它。  
  
## <a name="programmatically-create-a-named-instance"></a>以编程方式创建命名实例  
 应用程序可以创建命名实例并指定数据库，如下所示：  
  
- 在 app.config 文件中指定要创建的 LocalDB 实例，如下所示。  实例版本号应与 LocalDB 安装的版本号相同。  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <configSections>  
        <section  
        name="system.data.localdb"  
        type="System.Data.LocalDBConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/>  
      </configSections>  
      <system.data.localdb>  
        <localdbinstances>  
          <add name="myInstance" version="11.0" />  
        </localdbinstances>  
      </system.data.localdb>  
    </configuration>  
    ```  
  
- 使用 `server` 连接字符串关键字指定实例名称。  `server` 连接字符串关键字中指定的实例名称必须与 app.config 文件中指定的名称匹配。  
  
- 使用 `AttachDBFilename` 连接字符串关键字来指定 .MDF 文件。  
  
## <a name="see-also"></a>请参阅

- [SQL Server 功能和 ADO.NET](sql-server-features-and-adonet.md)
- [ADO.NET 概述](../ado-net-overview.md)
