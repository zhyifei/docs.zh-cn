---
title: 用于实体框架的 SqlClient 类型
ms.date: 03/30/2017
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
ms.openlocfilehash: af3a4eea08dd3f4e1a134fcb66d92bc4a3b077c7
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248383"
---
# <a name="sqlclient-for-entity-frameworktypes"></a>用于实体框架的 SqlClient 类型
SQL Server .NET Framework        (SqlClient)  
  
 下表描述了 SQL Server 2008、SQL Server 2005 和 SQL Server 2000 数据库的类型以及这些类型如何映射到概念模型类型。 在 SQL Server 的较新版本中引入的某些新类型在 SQL Server 早期版本中不受支持。 下表中注明了这些类型。  
  
|提供程序类型<br /><br /> NAME|提供程序类型<br /><br /> 特性|`EDMSimpleType`<br /><br /> NAME|方面|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|n/a|`Edm.Boolean`|不可用|  
|`tinyint`|不可用|`Edm.Byte`|不可用|  
|`smallint`|不可用|`Edm.Int16`|不可用|  
|`int`|不可用|`Edm.Int32`|不可用|  
|`bigint`|不可用|`Edm.Int64`|不可用|  
|`float`|不可用|`Edm.Double`|不可用|  
|`real`|不可用|`Edm.Double`|不可用|  
|`decimal`|n/a|`Edm.Decimal`|Precision<br /><br /> 短1<br /><br /> 最佳38<br /><br /> 缺省值18<br /><br /> 常量False<br /><br /> 缩放：<br /><br /> 短0<br /><br /> 最佳38<br /><br /> 缺省值0<br /><br /> 常量False|  
|`numeric`|n/a|`Edm.Decimal`|Precision<br /><br /> 短1<br /><br /> 最佳38<br /><br /> 缺省值18<br /><br /> 常量False<br /><br /> 缩放：<br /><br /> 短0<br /><br /> 最佳38<br /><br /> 缺省值0<br /><br /> 常量False|  
|`smallmoney`|n/a|`Edm.Decimal`|Precision<br /><br /> 缺省值10<br /><br /> 常量True<br /><br /> 缩放：<br /><br /> 缺省值4<br /><br /> 常量True|  
|`money`|n/a|`Edm.Decimal`|Precision<br /><br /> 缺省值19<br /><br /> 常量True<br /><br /> 缩放：<br /><br /> 缺省值4<br /><br /> 常量True|  
|`binary`|n/a|`Edm.Binary`|长度<br /><br /> 短1<br /><br /> 最佳8000<br /><br /> 缺省值8000<br /><br /> 常量False<br /><br /> FixedLength<br /><br /> 缺省值True<br /><br /> 常量True|  
|`varbinary`|n/a|`Edm.Binary`|长度<br /><br /> 短1<br /><br /> 最佳8000<br /><br /> 缺省值8000<br /><br /> 常量False<br /><br /> FixedLength<br /><br /> 缺省值False<br /><br /> 常量True|  
|`varbinary(max)`<br /><br /> 注意:SQL Server 2000 不支持此类型。|n/a|`Edm.Binary`|长度<br /><br /> 缺省值214748364780<br /><br /> 常量True<br /><br /> FixedLength<br /><br /> 缺省值False<br /><br /> 常量True|  
|`image`|n/a|`Edm.Binary`|长度<br /><br /> 缺省值2147483647<br /><br /> 常量True<br /><br /> FixedLength<br /><br /> 缺省值False<br /><br /> 常量True|  
|`timestamp`|n/a|`Edm.Binary`|长度<br /><br /> 缺省值8<br /><br /> 常量True<br /><br /> FixedLength<br /><br /> 缺省值True<br /><br /> 常量True|  
|`rowversion`|n/a|`Edm.Binary`|长度<br /><br /> 缺省值8<br /><br /> 常量True<br /><br /> FixedLength<br /><br /> 缺省值True<br /><br /> 常量True|  
|`smalldatetime`|n/a|`Edm.DateTime`|Precision<br /><br /> 缺省值0<br /><br /> 常量True|  
|`datetime`|n/a|`Edm.DateTime`|Precision<br /><br /> 缺省值3<br /><br /> 常量True|  
|`date`<br /><br /> 注意:SQL Server 2005 和 SQL Server 2000 不支持此类型。|n/a|`Edm.DateTime`|Precision<br /><br /> 缺省值0<br /><br /> 常量False|  
|`time`<br /><br /> 注意:SQL Server 2005 和 SQL Server 2000 不支持此类型。|n/a|`Edm.Time`|Precision<br /><br /> 缺省值7<br /><br /> 常量False|  
|`datetime2`<br /><br /> 注意:SQL Server 2005 和 SQL Server 2000 不支持此类型。|n/a|`Edm.DateTime`|Precision<br /><br /> 缺省值7<br /><br /> 常量False|  
|`datetimeoffset`<br /><br /> 注意:SQL Server 2005 和 SQL Server 2000 不支持此类型。|n/a|`Edm.DateTimeOffset`|Precision<br /><br /> 缺省值7<br /><br /> 常量False|  
|`nvarchar`<br /><br /> 注意:SQL Server 2000 不支持此类型。|n/a|`Edm.String`|长度<br /><br /> 短1<br /><br /> 最佳4000<br /><br /> 缺省值4000<br /><br /> 常量False<br /><br /> Unicode：<br /><br /> 缺省值True<br /><br /> 常量True<br /><br /> FixedLength<br /><br /> 缺省值False<br /><br /> 常量True|  
|`varchar`<br /><br /> 注意:SQL Server 2000 不支持此类型。|n/a|`Edm.String`|长度<br /><br /> 短1<br /><br /> 最佳8000<br /><br /> 缺省值8000<br /><br /> 常量False<br /><br /> Unicode：<br /><br /> 缺省值False<br /><br /> 常量True<br /><br /> FixedLength<br /><br /> 缺省值False<br /><br /> 常量True|  
|`char`|n/a|`Edm.String`|长度<br /><br /> 短1<br /><br /> 最佳8000<br /><br /> 缺省值8000<br /><br /> 常量False<br /><br /> Unicode：<br /><br /> 缺省值False<br /><br /> 常量True<br /><br /> FixedLength<br /><br /> 缺省值True<br /><br /> 常量True|  
|`nchar`|n/a|`Edm.String`|长度<br /><br /> 短1<br /><br /> 最佳4000<br /><br /> 缺省值4000<br /><br /> 常量False<br /><br /> Unicode：<br /><br /> 缺省值True<br /><br /> 常量True<br /><br /> FixedLength<br /><br /> 缺省值True<br /><br /> 常量True|  
|`varchar`(`max`)|n/a|`Edm.String`|长度<br /><br /> 缺省值2147483647<br /><br /> 常量True<br /><br /> Unicode：<br /><br /> 缺省值False<br /><br /> 常量True<br /><br /> FixedLength<br /><br /> 缺省值False<br /><br /> 常量True|  
|`nvarchar`(`max`)|n/a|`Edm.String`|长度<br /><br /> 缺省值1073741823<br /><br /> 常量True<br /><br /> Unicode：<br /><br /> 缺省值True<br /><br /> 常量True<br /><br /> FixedLength<br /><br /> 缺省值False<br /><br /> 常量True|  
|`ntext`|同等可比较：False<br /><br /> 可比较顺序：False|`Edm.String`|长度<br /><br /> 缺省值1073741823<br /><br /> 常量True<br /><br /> Unicode：<br /><br /> 缺省值False<br /><br /> 常量True<br /><br /> FixedLength<br /><br /> 缺省值False<br /><br /> 常量True|  
|`text`|同等可比较：False<br /><br /> 可比较顺序：False|`Edm.String`|长度<br /><br /> 缺省值2147483647<br /><br /> 常量True<br /><br /> Unicode：<br /><br /> 缺省值False<br /><br /> 常量True<br /><br /> FixedLength<br /><br /> 缺省值False<br /><br /> 常量True|  
|`Unique`<br /><br /> `identifier`|同等可比较：True<br /><br /> 可比较顺序：True|`Edm.Guid`|n/a|  
|`xml`|同等可比较：False<br /><br /> 可比较顺序：False|`Edm.String`|长度<br /><br /> 缺省值1073741823<br /><br /> 常量True<br /><br /> Unicode：<br /><br /> 缺省值True<br /><br /> 常量True<br /><br /> FixedLength<br /><br /> 缺省值False<br /><br /> 常量True|  
  
## <a name="see-also"></a>请参阅

- [CSDL、SSDL 和 MSL 规范](./language-reference/csdl-ssdl-and-msl-specifications.md)
