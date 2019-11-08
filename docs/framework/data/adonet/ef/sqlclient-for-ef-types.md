---
title: 用于实体框架的 SqlClient 类型
ms.date: 03/30/2017
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
ms.openlocfilehash: d132583bba2520d37693be6c4b085cfa514003e0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73737843"
---
# <a name="sqlclient-for-entity-frameworktypes"></a>用于实体框架的 SqlClient 类型
SQL Server .NET Framework        (SqlClient)  
  
 下表描述了 SQL Server 2008、SQL Server 2005 和 SQL Server 2000 数据库的类型以及这些类型如何映射到概念模型类型。 在 SQL Server 的较新版本中引入的某些新类型在 SQL Server 早期版本中不受支持。 下表中注明了这些类型。  
  
|提供程序类型<br /><br /> NAME|提供程序类型<br /><br /> 特性|`EDMSimpleType`<br /><br /> NAME|方面|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|不可用|`Edm.Boolean`|不可用|  
|`tinyint`|不可用|`Edm.Byte`|不可用|  
|`smallint`|不可用|`Edm.Int16`|不可用|  
|`int`|不可用|`Edm.Int32`|不可用|  
|`bigint`|不可用|`Edm.Int64`|不可用|  
|`float`|不可用|`Edm.Double`|不可用|  
|`real`|不可用|`Edm.Double`|不可用|  
|`decimal`|不可用|`Edm.Decimal`|Precision<br /><br /> -最小值：1<br /><br /> -最大值：38<br /><br /> -默认值：18<br /><br /> -常量： False<br /><br /> 纵向<br /><br /> -最小值：0<br /><br /> -最大值：38<br /><br /> -默认值：0<br /><br /> -常量： False|  
|`numeric`|不可用|`Edm.Decimal`|Precision<br /><br /> -最小值：1<br /><br /> -最大值：38<br /><br /> -默认值：18<br /><br /> -常量： False<br /><br /> 纵向<br /><br /> -最小值：0<br /><br /> -最大值：38<br /><br /> -默认值：0<br /><br /> -常量： False|  
|`smallmoney`|不可用|`Edm.Decimal`|Precision<br /><br /> -默认值：10<br /><br /> -常量： True<br /><br /> 纵向<br /><br /> -默认值：4<br /><br /> -常量： True|  
|`money`|不可用|`Edm.Decimal`|Precision<br /><br /> -默认值：19<br /><br /> -常量： True<br /><br /> 纵向<br /><br /> -默认值：4<br /><br /> -常量： True|  
|`binary`|不可用|`Edm.Binary`|长度<br /><br /> -最小值：1<br /><br /> -最大值：8000<br /><br /> -默认值：8000<br /><br /> -常量： False<br /><br /> FixedLength<br /><br /> -默认值： True<br /><br /> -常量： True|  
|`varbinary`|不可用|`Edm.Binary`|长度<br /><br /> -最小值：1<br /><br /> -最大值：8000<br /><br /> -默认值：8000<br /><br /> -常量： False<br /><br /> FixedLength<br /><br /> -默认值： False<br /><br /> -常量： True|  
|`varbinary(max)`<br /><br /> 注意： SQL Server 2000 不支持此类型。|不可用|`Edm.Binary`|长度<br /><br /> -默认值：214748364780<br /><br /> -常量： True<br /><br /> FixedLength<br /><br /> -默认值： False<br /><br /> -常量： True|  
|`image`|不可用|`Edm.Binary`|长度<br /><br /> -默认值：2147483647<br /><br /> -常量： True<br /><br /> FixedLength<br /><br /> -默认值： False<br /><br /> -常量： True|  
|`timestamp`|不可用|`Edm.Binary`|长度<br /><br /> -默认值：8<br /><br /> -常量： True<br /><br /> FixedLength<br /><br /> -默认值： True<br /><br /> -常量： True|  
|`rowversion`|不可用|`Edm.Binary`|长度<br /><br /> -默认值：8<br /><br /> -常量： True<br /><br /> FixedLength<br /><br /> -默认值： True<br /><br /> -常量： True|  
|`smalldatetime`|不可用|`Edm.DateTime`|Precision<br /><br /> -默认值：0<br /><br /> -常量： True|  
|`datetime`|不可用|`Edm.DateTime`|Precision<br /><br /> -默认值：3<br /><br /> -常量： True|  
|`date`<br /><br /> 注意： SQL Server 2005 和 SQL Server 2000 不支持此类型。|不可用|`Edm.DateTime`|Precision<br /><br /> -默认值：0<br /><br /> -常量： False|  
|`time`<br /><br /> 注意： SQL Server 2005 和 SQL Server 2000 不支持此类型。|不可用|`Edm.Time`|Precision<br /><br /> -默认值：7<br /><br /> -常量： False|  
|`datetime2`<br /><br /> 注意： SQL Server 2005 和 SQL Server 2000 不支持此类型。|不可用|`Edm.DateTime`|Precision<br /><br /> -默认值：7<br /><br /> -常量： False|  
|`datetimeoffset`<br /><br /> 注意： SQL Server 2005 和 SQL Server 2000 不支持此类型。|不可用|`Edm.DateTimeOffset`|Precision<br /><br /> -默认值：7<br /><br /> -常量： False|  
|`nvarchar`<br /><br /> 注意： SQL Server 2000 不支持此类型。|不可用|`Edm.String`|长度<br /><br /> -最小值：1<br /><br /> -最大值：4000<br /><br /> -默认值：4000<br /><br /> -常量： False<br /><br /> Unicode：<br /><br /> -默认值： True<br /><br /> -常量： True<br /><br /> FixedLength<br /><br /> -默认值： False<br /><br /> -常量： True|  
|`varchar`<br /><br /> 注意： SQL Server 2000 不支持此类型。|不可用|`Edm.String`|长度<br /><br /> -最小值：1<br /><br /> -最大值：8000<br /><br /> -默认值：8000<br /><br /> -常量： False<br /><br /> Unicode：<br /><br /> -默认值： False<br /><br /> -常量： True<br /><br /> FixedLength<br /><br /> -默认值： False<br /><br /> -常量： True|  
|`char`|不可用|`Edm.String`|长度<br /><br /> -最小值：1<br /><br /> -最大值：8000<br /><br /> -默认值：8000<br /><br /> -常量： False<br /><br /> Unicode：<br /><br /> -默认值： False<br /><br /> -常量： True<br /><br /> FixedLength<br /><br /> -默认值： True<br /><br /> -常量： True|  
|`nchar`|不可用|`Edm.String`|长度<br /><br /> -最小值：1<br /><br /> -最大值：4000<br /><br /> -默认值：4000<br /><br /> -常量： False<br /><br /> Unicode：<br /><br /> -默认值： True<br /><br /> -常量： True<br /><br /> FixedLength<br /><br /> -默认值： True<br /><br /> -常量： True|  
|`varchar`(`max`)|不可用|`Edm.String`|长度<br /><br /> -默认值：2147483647<br /><br /> -常量： True<br /><br /> Unicode：<br /><br /> -默认值： False<br /><br /> -常量： True<br /><br /> FixedLength<br /><br /> -默认值： False<br /><br /> -常量： True|  
|`nvarchar`(`max`)|不可用|`Edm.String`|长度<br /><br /> -默认值：1073741823<br /><br /> -常量： True<br /><br /> Unicode：<br /><br /> -默认值： True<br /><br /> -常量： True<br /><br /> FixedLength<br /><br /> -默认值： False<br /><br /> -常量： True|  
|`ntext`|相等可比较： False<br /><br /> 可比较顺序： False|`Edm.String`|长度<br /><br /> -默认值：1073741823<br /><br /> -常量： True<br /><br /> Unicode：<br /><br /> -默认值： False<br /><br /> -常量： True<br /><br /> FixedLength<br /><br /> -默认值： False<br /><br /> -常量： True|  
|`text`|相等可比较： False<br /><br /> 可比较顺序： False|`Edm.String`|长度<br /><br /> -默认值：2147483647<br /><br /> -常量： True<br /><br /> Unicode：<br /><br /> -默认值： False<br /><br /> -常量： True<br /><br /> FixedLength<br /><br /> -默认值： False<br /><br /> -常量： True|  
|`Unique`<br /><br /> `identifier`|相等比较： True<br /><br /> 可比较顺序： True|`Edm.Guid`|不可用|  
|`xml`|相等可比较： False<br /><br /> 可比较顺序： False|`Edm.String`|长度<br /><br /> -默认值：1073741823<br /><br /> -常量： True<br /><br /> Unicode：<br /><br /> -默认值： True<br /><br /> -常量： True<br /><br /> FixedLength<br /><br /> -默认值： False<br /><br /> -常量： True|  
  
## <a name="see-also"></a>请参阅

- [CSDL、SSDL 和 MSL 规范](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
