---
title: "Oracle 的 .NET Framework 数据提供程序的系统需求"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 054f76b9-1737-43f0-8160-84a00a387217
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: cb21a71a548766ee5439c6a558ea7f23d1f45364
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="system-requirements-for-the-net-framework-data-provider-for-oracle"></a>Oracle 的 .NET Framework 数据提供程序的系统需求
Oracle .NET Framework 数据提供程序需要 Microsoft 数据访问组件 (MDAC) 2.6 版或更高版本。 建议使用 MDAC 2.8 SP1。  
  
 还必须安装 Oracle 8i Release 3 (8.1.7) 客户端或更高版本。  
  
 Oracle 9i 版本之前的 Oracle 客户端软件无法访问 UTF16 数据库，因为 UTF16 是 Oracle 9i 中的一项新功能。 要使用此功能，必须将客户端软件升级到 Oracle 9i 或更高版本。  
  
## <a name="working-with-the-data-provider-for-oracle-and-unicode-data"></a>使用 Oracle 数据提供程序和 Unicode 数据  
 下表列出在使用 Oracle .NET Framework 数据提供程序和 Oracle 客户端库时，应考虑的与 Unicode 有关的问题。 有关更多信息，请参见 Oracle 文档。  
  
### <a name="setting-the-unicode-value-in-a-connection-string-attribute"></a>在连接字符串属性中设置 Unicode 值  
 在使用 Oracle 时，可以使用连接字符串属性  
  
```  
Unicode=True   
```  
  
 在 UTF-16 模式下初始化 Oracle 客户端库。 这样可以使 Oracle 客户端库接受 UTF-16（与 UCS-2 非常类似），而不是多字节字符串。 这样，Oracle 数据提供程序始终可以使用任何 Oracle 代码页，不需要进行其他转换工作。 只有使用 Oracle 9i 客户端与包含备选字符集 AL16UTF16 的 Oracle 9i 数据库进行通信时，此配置才有效。 当 Oracle 9i 客户端与 Oracle 9i 服务器进行通信时，其他资源所需转换 Unicode **CommandText**为相应的多字节字符的值设置为 Oracle9i 服务器使用。 如果确定已通过将 `Unicode=True` 添加到连接字符串中而拥有了安全的配置，则可以避免此问题。  
  
### <a name="mixing-versions-of-oracle-client-and-oracle-server"></a>混合版本的 Oracle 客户端和 Oracle 服务器  
 Oracle 8i 客户端无法访问**NCHAR**， **NVARCHAR2**，或**NCLOB**时服务器的国家字符集指定为 AL16UTF16 的 Oracle 9i 数据库中的数据 (默认设置对于 Oracle 9i）。 因为直到 Oracle 9i 才引入对 UTF-16 字符集的支持，Oracle 8i 客户端无法读取。  
  
### <a name="working-with-utf-8-data"></a>使用 UTF-8 数据  
 要设置备选字符集，将注册表项 HKEY_LOCAL_MACHINE\SOFTWARE\ORACLE\HOMEID\NLS_LANG 设置为 UTF8。 有关更多信息，请参见适合您的平台的 Oracle 安装说明。 默认设置为安装 Oracle 客户端软件所使用的语言的主要字符集。 如果设置的语言与所连接的数据库的国家语言字符集不匹配，将使参数和列绑定使用主要数据库字符集发送或接收数据，而不是使用国家字符集。  
  
### <a name="oraclelob-can-only-update-full-characters"></a>OracleLob 只能更新完整字符。  
 出于可用性原因，<xref:System.Data.OracleClient.OracleLob>对象继承自.NET Framework 流的类，并提供**ReadByte**和**WriteByte**方法。 它还实现方法，如**CopyTo**和**擦除**，则该工作上的 Oracle 部分**LOB**对象。 与此相反，Oracle 客户端软件提供大量的 Api 来使用字符**LOB**s (**CLOB**和**NCLOB**)。 但是，这些 API 只适用于完整字符。 因为这一区别，Oracle 数据提供程序实现支持**读取**和**ReadByte**以便以便方式使用 utf-16 数据。 但是，其他方法的**OracleLob**对象只允许完整字符操作。  
  
## <a name="see-also"></a>请参阅  
 [Oracle 和 ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
