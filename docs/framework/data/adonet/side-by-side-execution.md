---
title: ADO.NET 中的并行执行
ms.date: 03/30/2017
ms.assetid: 9f9ba96d-9f89-4f65-bb2f-6860879f4393
ms.openlocfilehash: 377af3c72b0a9a8eb26c8713d98f114803f08356
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583619"
---
# <a name="side-by-side-execution-in-adonet"></a>ADO.NET 中的并行执行
.NET Framework 中的并行执行是在具有多个版本的安装，以独占方式使用为其编译应用程序的版本的.NET Framework 的计算机上执行应用程序的功能。 有关配置通过并行执行的详细信息，请参阅[-并行执行](../../../../docs/framework/deployment/side-by-side-execution.md)。  
  
 编译使用.NET Framework 的一个版本的应用程序可以运行不同版本的.NET Framework 上。 但是，我们建议你编译的.NET Framework 中，每个已安装版本的应用程序的版本，并单独运行这些。 在任一方案中，您都应该知道各版本之间 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 中的更改，这些更改可能影响应用程序的向前或向后兼容性。  
  
## <a name="forward-compatibility-and-backward-compatibility"></a>向前兼容性和向后兼容性  
 向前兼容性表示应用程序可以使用.NET Framework 的早期版本进行编译，但将仍在更高版本的.NET framework 上成功运行。 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 针对.NET Framework 1.1 版编写的代码是与更高版本向前兼容。  
  
 向后兼容性表示应用程序编译为.NET Framework 的较新版本，但仍会继续而不丧失任何功能的.NET framework 的早期版本上运行。 当然，这不会对.NET Framework 的新版本中引入的功能。  
  
## <a name="the-net-framework-data-provider-for-odbc"></a>ODBC .NET Framework 数据提供程序  
 从版本 1.1 中，用于 ODBC 的.NET Framework 数据提供程序 (<xref:System.Data.Odbc>) 是作为.NET Framework 的一部分包含在内。 ODBC 数据提供程序是用.NET Framework 1.0 版开发人员从 Web 下载[数据访问和存储开发人员中心](https://go.microsoft.com/fwlink/?linkid=4173)。 适用于 ODBC 下载.NET Framework 数据提供程序的命名空间是**Microsoft.Data.Odbc**。  
  
 如果必须针对.NET Framework 版本使用 ODBC 数据提供程序连接到数据源，1.0 开发的应用程序，并且你想要在.NET Framework 1.1 版或更高版本上运行该应用程序，则必须更新 ODBC dat 的命名空间提供者**System.Data.Odbc**。 您然后必须重新编译它为.NET Framework 的较新版本。  
  
 如果必须为使用 ODBC 数据提供程序连接到数据源，.NET Framework 2.0 或更高版本开发的应用程序，并且你想要在.NET Framework 1.0 版上运行该应用程序，必须下载该 ODBC 数据提供程序并安装它在.NET Framework 1.0 版的系统。 然后必须更改到 ODBC 数据提供程序的命名空间**Microsoft.Data.Odbc**，并重新编译.NET Framework 1.0 版的应用程序。  
  
## <a name="the-net-framework-data-provider-for-oracle"></a>Oracle .NET Framework 数据提供程序  
 从版本 1.1，适用于 Oracle 的.NET Framework 数据提供程序开始 (<xref:System.Data.OracleClient>) 是作为.NET Framework 的一部分包含在内。 数据提供程序是用.NET Framework 1.0 版开发人员从 Web 下载[数据访问和存储开发人员中心](https://go.microsoft.com/fwlink/?linkid=4173)。  
  
 如果必须为使用的数据提供程序连接到您的数据源，.NET Framework 2.0 或更高版本开发的应用程序，并且你想要在.NET Framework 1.0 版上运行该应用程序，必须下载数据提供程序并将其安装在.NET Framework 1.0 版的系统。  
  
## <a name="code-access-security"></a>代码访问安全性  
 在.NET Framework 1.0 版的.NET Framework 数据提供程序 (<xref:System.Data.SqlClient>， <xref:System.Data.OleDb>) 所需运行具有 FullTrust 权限。 如果尝试在具有 FullTrust 权限会导致小于的区域中使用.NET Framework 数据提供程序从.NET Framework 1.0 版<xref:System.Security.SecurityException>。  
  
 但是，从.NET Framework 2.0 版开始，所有.NET Framework 数据提供程序可在部分信任的区域。 此外，新的安全功能已添加到.NET Framework 1.1 版中的.NET Framework 数据提供程序。 通过该功能可以限制特定安全区域中可以使用的连接字符串。 您也可以对特定安全区域禁用空白密码。 有关更多信息，请参见 [Code Access Security and ADO.NET](../../../../docs/framework/data/adonet/code-access-security.md)。  
  
 由于安装.NET Framework 的每个具有独立的 Security.config 文件，没有使用的安全设置任何兼容性问题。 但是，如果应用程序所依赖的其他安全功能[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]包含在.NET Framework 1.1 及更高版本中，您将无法再将其分发到 1.0 版的系统。  
  
## <a name="sqlcommand-execution"></a>SqlCommand 执行  
 从.NET Framework 1.1 版中，方法开始的<xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>执行命令的数据源已更改。  
  
 在.NET Framework 1.0 版中，<xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>的上下文中执行的所有命令**sp_executesql**存储过程。 因此，影响连接状态的命令（例如，SET NOCOUNT ON）只应用于当前命令的执行。 对于在连接打开时执行的任何后续命令，连接状态不会被修改。  
  
 在.NET Framework 1.1 及更高版本，版本<xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>仅的上下文中执行命令**sp_executesql**存储过程，当命令含有参数，从而提高性能。 因此，如果非参数化命令中包含影响连接状态的命令，会修改在连接打开时执行的所有后续命令的连接状态。  
  
 请考虑下面这个在 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> 调用中执行的批命令。  
  
```sql
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
```  
  
 在.NET Framework 1.1 及更高版本中，NOCOUNT 将保持该连接打开时执行的任何后续命令为 ON。 在.NET Framework 1.0 版中，NOCOUNT 为只在当前命令执行。  
  
 如果所依赖的行为，此更改会影响你的应用程序的向前和向后兼容<xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>两个版本的.NET Framework。  
  
 对于.NET Framework 的早期版本和更高版本运行的应用程序，可以编写代码以确保该行为是不考虑版本运行相同。 如果要确保某个命令修改所有后续命令的连接状态，建议您使用 <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> 来执行该命令。 如果要确保某个命令不修改所有后续命令的连接，建议您在命令中包括用于重置连接状态的命令。 例如：  
  
```sql
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
SET NOCOUNT OFF;  
```  
  
## <a name="see-also"></a>请参阅

- [ADO.NET 概述](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [在 ADO.NET 中检索和修改数据](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [ADO.NET 托管提供程序和数据集开发人员中心](https://go.microsoft.com/fwlink/?LinkId=217917)
