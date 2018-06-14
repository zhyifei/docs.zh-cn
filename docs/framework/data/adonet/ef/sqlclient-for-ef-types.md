---
title: 用于实体框架的 SqlClient 类型
ms.date: 03/30/2017
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
ms.openlocfilehash: f5b471cea4f26c06e8af77298c256bff97ef21de
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766538"
---
# <a name="sqlclient-for-entity-frameworktypes"></a>用于实体框架的 SqlClient 类型
SQL Server .NET Framework        (SqlClient)                                                                                       
  
 下表说明 SQL Server 2008 中，类型[!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)]，和[!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)]数据库和这些类型如何映射到概念模型类型。 在 SQL Server 的较新版本中引入的某些新类型在 SQL Server 早期版本中不受支持。 下表中注明了这些类型。  
  
|提供程序类型<br /><br /> name|提供程序类型<br /><br /> 特性|`EDMSimpleType`<br /><br /> name|方面|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|无|`Edm.Boolean`|不可用|  
|`tinyint`|不可用|`Edm.Byte`|不可用|  
|`smallint`|不可用|`Edm.Int16`|不可用|  
|`int`|不可用|`Edm.Int32`|不可用|  
|`bigint`|不可用|`Edm.Int64`|不可用|  
|`float`|不可用|`Edm.Double`|不可用|  
|`real`|不可用|`Edm.Double`|不可用|  
|`decimal`|n/a|`Edm.Decimal`|精度：<br /><br /> -最低： 1<br /><br /> -最大： 38<br /><br /> -默认： 18<br /><br /> -常量： False<br /><br /> 缩放：<br /><br /> -最小值： 0<br /><br /> -最大： 38<br /><br /> 的默认值： 0<br /><br /> -常量： False|  
|`numeric`|n/a|`Edm.Decimal`|精度：<br /><br /> -最低： 1<br /><br /> -最大： 38<br /><br /> -默认： 18<br /><br /> -常量： False<br /><br /> 缩放：<br /><br /> -最小值： 0<br /><br /> -最大： 38<br /><br /> 的默认值： 0<br /><br /> -常量： False|  
|`smallmoney`|n/a|`Edm.Decimal`|精度：<br /><br /> -默认： 10<br /><br /> -常量： True<br /><br /> 缩放：<br /><br /> 的默认值： 4<br /><br /> -常量： True|  
|`money`|n/a|`Edm.Decimal`|精度：<br /><br /> -默认： 19<br /><br /> -常量： True<br /><br /> 缩放：<br /><br /> 的默认值： 4<br /><br /> -常量： True|  
|`binary`|n/a|`Edm.Binary`|MaxLength:<br /><br /> -最低： 1<br /><br /> -最大： 8000<br /><br /> -默认： 8000<br /><br /> -常量： False<br /><br /> FixedLength:<br /><br /> 的默认值： True<br /><br /> -常量： True|  
|`varbinary`|n/a|`Edm.Binary`|MaxLength:<br /><br /> -最低： 1<br /><br /> -最大： 8000<br /><br /> -默认： 8000<br /><br /> -常量： False<br /><br /> FixedLength:<br /><br /> 的默认值： False<br /><br /> -常量： True|  
|`varbinary(max)`<br /><br /> 注意： 在不支持此类型[!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)]。|n/a|`Edm.Binary`|MaxLength:<br /><br /> -默认： 214748364780<br /><br /> -常量： True<br /><br /> FixedLength:<br /><br /> 的默认值： False<br /><br /> -常量： True|  
|`image`|n/a|`Edm.Binary`|MaxLength:<br /><br /> -默认： 2147483647<br /><br /> -常量： True<br /><br /> FixedLength:<br /><br /> 的默认值： False<br /><br /> -常量： True|  
|`timestamp`|n/a|`Edm.Binary`|MaxLength:<br /><br /> 的默认值： 8<br /><br /> -常量： True<br /><br /> FixedLength:<br /><br /> 的默认值： True<br /><br /> -常量： True|  
|`rowversion`|n/a|`Edm.Binary`|MaxLength:<br /><br /> 的默认值： 8<br /><br /> -常量： True<br /><br /> FixedLength:<br /><br /> 的默认值： True<br /><br /> -常量： True|  
|`smalldatetime`|n/a|`Edm.DateTime`|精度：<br /><br /> 的默认值： 0<br /><br /> -常量： True|  
|`datetime`|n/a|`Edm.DateTime`|精度：<br /><br /> -默认： 3<br /><br /> -常量： True|  
|`date`<br /><br /> 注意： 在 SQL Server 2005 和 SQL Server 2000 中不支持此类型。|n/a|`Edm.DateTime`|精度：<br /><br /> 的默认值： 0<br /><br /> -常量： False|  
|`time`<br /><br /> 注意： 在 SQL Server 2005 和 SQL Server 2000 中不支持此类型。|n/a|`Edm.Time`|精度：<br /><br /> 的默认值： 7<br /><br /> -常量： False|  
|`datetime2`<br /><br /> 注意： 在 SQL Server 2005 和 SQL Server 2000 中不支持此类型。|n/a|`Edm.DateTime`|精度：<br /><br /> 的默认值： 7<br /><br /> -常量： False|  
|`datetimeoffset`<br /><br /> 注意： 在 SQL Server 2005 和 SQL Server 2000 中不支持此类型。|n/a|`Edm.DateTimeOffset`|精度：<br /><br /> 的默认值： 7<br /><br /> -常量： False|  
|`nvarchar`<br /><br /> 注意： 在不支持此类型[!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)]。|n/a|`Edm.String`|MaxLength:<br /><br /> -最低： 1<br /><br /> -最大： 4000<br /><br /> -默认： 4000<br /><br /> -常量： False<br /><br /> Unicode:<br /><br /> 的默认值： True<br /><br /> -常量： True<br /><br /> FixedLength:<br /><br /> 的默认值： False<br /><br /> -常量： True|  
|`varchar`<br /><br /> 注意： 在不支持此类型[!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)]。|n/a|`Edm.String`|MaxLength:<br /><br /> -最低： 1<br /><br /> -最大： 8000<br /><br /> -默认： 8000<br /><br /> -常量： False<br /><br /> Unicode:<br /><br /> 的默认值： False<br /><br /> -常量： True<br /><br /> FixedLength:<br /><br /> 的默认值： False<br /><br /> -常量： True|  
|`char`|n/a|`Edm.String`|MaxLength:<br /><br /> -最低： 1<br /><br /> -最大： 8000<br /><br /> -默认： 8000<br /><br /> -常量： False<br /><br /> Unicode:<br /><br /> 的默认值： False<br /><br /> -常量： True<br /><br /> FixedLength:<br /><br /> 的默认值： True<br /><br /> -常量： True|  
|`nchar`|n/a|`Edm.String`|MaxLength:<br /><br /> -最低： 1<br /><br /> -最大： 4000<br /><br /> -默认： 4000<br /><br /> -常量： False<br /><br /> Unicode:<br /><br /> 的默认值： True<br /><br /> -常量： True<br /><br /> FixedLength:<br /><br /> 的默认值： True<br /><br /> -常量： True|  
|`varchar`(`max`)|n/a|`Edm.String`|MaxLength:<br /><br /> -默认： 2147483647<br /><br /> -常量： True<br /><br /> Unicode:<br /><br /> 的默认值： False<br /><br /> -常量： True<br /><br /> FixedLength:<br /><br /> 的默认值： False<br /><br /> -常量： True|  
|`nvarchar`(`max`)|n/a|`Edm.String`|MaxLength:<br /><br /> -默认： 1073741823<br /><br /> -常量： True<br /><br /> Unicode:<br /><br /> 的默认值： True<br /><br /> -常量： True<br /><br /> FixedLength:<br /><br /> 的默认值： False<br /><br /> -常量： True|  
|`ntext`|可比较相等： False<br /><br /> 可比较顺序： False|`Edm.String`|MaxLength:<br /><br /> -默认： 1073741823<br /><br /> -常量： True<br /><br /> Unicode:<br /><br /> 的默认值： False<br /><br /> -常量： True<br /><br /> FixedLength:<br /><br /> 的默认值： False<br /><br /> -常量： True|  
|`text`|可比较相等： False<br /><br /> 可比较顺序： False|`Edm.String`|MaxLength:<br /><br /> -默认： 2147483647<br /><br /> -常量： True<br /><br /> Unicode:<br /><br /> 的默认值： False<br /><br /> -常量： True<br /><br /> FixedLength:<br /><br /> 的默认值： False<br /><br /> -常量： True|  
|`Unique`<br /><br /> `identifier`|可比较相等： True<br /><br /> 可比较顺序： True|`Edm.Guid`|n/a|  
|`xml`|可比较相等： False<br /><br /> 可比较顺序： False|`Edm.String`|MaxLength:<br /><br /> -默认： 1073741823<br /><br /> -常量： True<br /><br /> Unicode:<br /><br /> 的默认值： True<br /><br /> -常量： True<br /><br /> FixedLength:<br /><br /> 的默认值： False<br /><br /> -常量： True|  
  
## <a name="see-also"></a>请参阅  
 [CSDL、SSDL 和 MSL 规范](../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
