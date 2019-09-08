---
title: ODBC 数据类型映射
ms.date: 03/30/2017
ms.assetid: 43c35d32-831d-480f-a150-78f7e869d17f
ms.openlocfilehash: 6611ca35ab5e5b44fa9adacfe25593bb4a5b9c44
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783512"
---
# <a name="odbc-data-type-mappings"></a>ODBC 数据类型映射
下表显示了针对 ODBC 的 .NET Framework 数据提供程序（<xref:System.Data.Odbc>）中的数据类型的推断 .NET Framework 类型。 另外，还列出了 <xref:System.Data.Odbc.OdbcDataReader> 的类型化访问器方法。  
  
|ODBC 类型|.NET Framework 类型|.NET Framework 类型化访问器|  
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
  
## <a name="see-also"></a>请参阅

- [在 ADO.NET 中检索和修改数据](retrieving-and-modifying-data.md)
- [ADO.NET 概述](ado-net-overview.md)
