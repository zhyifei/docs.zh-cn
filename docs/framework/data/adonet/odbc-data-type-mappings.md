---
title: "ODBC 数据类型映射"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 43c35d32-831d-480f-a150-78f7e869d17f
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 82c4a84f1aee5872a899d8d42a06d22abc10b603
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="odbc-data-type-mappings"></a>ODBC 数据类型映射
下表显示了针对适用于 ADO 的 .NET Framework 数据提供程序 ([!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]) 中的数据类型推断出的 <xref:System.Data.Odbc> 类型。 另外，还列出了 <xref:System.Data.Odbc.OdbcDataReader> 的类型化访问器方法。  
  
|ODBC 类型|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 类型|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 类型化访问器|  
|---------------|----------------------------------------------------------------------|--------------------------------------------------------------------------------|  
|SQL_BIGINT|Int64|GetInt64()|  
|SQL_BINARY|Byte[]|GetBytes()|  
|SQL_BIT|Boolean|GetBoolean()|  
|SQL_CHAR|String<br /><br /> Char[]|GetString()<br /><br /> GetChars()|  
|SQL_DECIMAL|Decimal|GetDecimal()|  
|SQL_DOUBLE|Double|GetDouble()|  
|SQL_GUID|Guid|GetGuid()|  
|SQL_INTEGER|Int32|GetInt32()|  
|SQL_LONG_VARCHAR|String<br /><br /> Char[]|GetString()<br /><br /> GetChars()|  
|SQL_LONGVARBINARY|Byte[]|GetBytes()|  
|SQL_NUMERIC|Decimal|GetDecimal()|  
|SQL_REAL|Single|GetFloat()|  
|SQL_SMALLINT|Int16|GetInt16()|  
|SQL_TINYINT|Byte|GetByte()|  
|SQL_TYPE_TIMES|DateTime|GetDateTime()|  
|SQL_TYPE_TIMESTAMP|DateTime|GetDateTime()|  
|SQL_VARBINARY|Byte[]|GetBytes()|  
|SQL_WCHAR|String<br /><br /> Char[]|GetString()<br /><br /> GetChars()|  
|SQL_WLONGVARCHAR|String<br /><br /> Char[]|GetString()<br /><br /> GetChars()|  
|SQL_WVARCHAR|String<br /><br /> Char[]|GetString()<br /><br /> GetChars()|  
  
## <a name="see-also"></a>另请参阅  
 [在 ADO.NET 中检索和修改数据](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
