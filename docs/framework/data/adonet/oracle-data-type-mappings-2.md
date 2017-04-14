---
title: "Oracle 数据类型映射 | Microsoft Docs"
ms.custom: ""
ms.date: "02/15/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d2521bcc-0051-4f35-8be3-e8723edeaf6f
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
---
# Oracle 数据类型映射
下表显示了针对适用于 Oracle 的 .NET Framework 数据提供程序 \([!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\) 的数据类型推断出的 <xref:System.Data.OracleClient> 类型。 另外，还列出了 <xref:System.Data.OracleClient.OracleDataReader> 的类型化访问器方法。  
  
|Oracle 类型|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 类型|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 类型化访问器|OracleType 类型化访问器|  
|---------------|--------------------------------------------------------------------|------------------------------------------------------------------------|-----------------------|  
|BFILE|Byte\[\]|GetBytes\(\)|GetOracleBFile\(\)|  
|BLOB|Byte\[\]|GetBytes\(\)|GetOracleLob\(\)|  
|CHAR|String<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|CLOB|String<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleLob\(\)|  
|DATE|DateTime|GetDateTime\(\)|GetOracleDateTime\(\)|  
|FLOAT|Decimal|GetDecimal\(\)|GetOracleNumber\(\) \*\*|  
|INTEGER|Decimal|GetDecimal\(\)|GetOracleNumber\(\) \*\*|  
|INTERVAL YEAR TO MONTH \*|Int32|GetInt32\(\)|GetOracleMonthSpan\(\)|  
|INTERVAL DAY TO SECOND \*|TimeSpan|GetTimeSpan\(\)|GetOracleTimeSpan\(\)|  
|LONG|String<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|LONG RAW|Byte\[\]|GetBytes\(\)|GetOracleBinary\(\)|  
|NCHAR|String<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|NCLOB|String<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleLob\(\)|  
|NUMBER|Decimal|GetDecimal\(\)|GetOracleNumber\(\) \*\*|  
|NVARCHAR2|String<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|RAW|Byte\[\]|GetBytes\(\)|GetOracleBinary\(\)|  
|REF CURSOR||||  
|ROWID|String<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|TIMESTAMP \*|DateTime|GetDateTime\(\)|GetOracleDateTime\(\)|  
|TIMESTAMP WITH LOCAL TIME ZONE \*|DateTime|GetDateTime\(\)|GetOracleDateTime\(\)|  
|TIMESTAMP WITH TIME ZONE \*|DateTime|GetDateTime\(\)|GetOracleDateTime\(\)|  
|UNSIGNED INTEGER|Decimal|GetDecimal\(\)|GetOracleNumber\(\) \*\*|  
|VARCHAR2|String<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
  
 \* 指定的 Oracle 类型仅在对客户端和服务器同时使用 Oracle 9i 软件时可用。  
  
 \*\* Oracle NUMBER 最多允许 38 个有效位。[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] `decimal` 类型最多允许 28 个有效位。 将 Oracle NUMBER 读入 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] `decimal` 类型会导致 `OverflowException`，因为 NUMBER 值超出了 28 位。 如果要从 `OracleDataReader` 读出 Oracle NUMBER 值，我们建议您调用 `GetOracleNumber` 类型化访问器方法以将 Oracle NUMBER 值作为 `OracleNumber` 返回。 如果要填充 `DataSet`，则可以使用 `FillError` 事件确定是否发生了 `OverflowException` 以及是否采取了相应的措施（若发生）。 有关 `FillError` 事件的信息，请参阅[处理 DataAdapter 事件](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)。  
  
## 请参阅  
 [Oracle 和 ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)   
 [在 ADO.NET 中检索和修改数据](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [ADO.NET 托管提供程序和 DataSet 开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)