---
title: "SQL Server 函数映射的规范化概念模型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a2631bc-a426-4c0a-ba8d-26d9c80d39e2
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a186c37506441dde814ca52970c60f0f816ba53e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="conceptual-model-canonical-to-sql-server-functions-mapping"></a>SQL Server 函数映射的规范化概念模型
本主题介绍概念模型规范函数如何映射到相应的 SQL Server 函数。  
  
## <a name="date-and-time-functions"></a>日期和时间函数  
 下表介绍了日期和时间函数映射：  
  
|规范函数|SQL Server 函数|  
|-------------------------|--------------------------|  
|[AddDays(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(day, number, date)`|  
|[AddHours(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(hour, number, date)`|  
|[AddMicroseconds(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(microsecond, number, date)`|  
|[AddMilliseconds(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(millisecond, number, date)`|  
|[AddMinutes(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(minute, number, date)`|  
|[AddMonths(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(month, number, date)`|  
|[AddNanoseconds(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(nanosecond, number, date)`|  
|[AddSeconds(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(second, number, date)`|  
|[AddYears(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEADD(year, number, date)`|  
|[CreateDateTime （年、 月、 日、 小时、 分钟、 秒）](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|对于 SQL Server 2000 和 SQL Server 2005，在服务器上创建 `datetime` 带格式的值。 对于 SQL Server 2008 及更高版本，在服务器上创建 `datetime2` 值。|  
|[CreateDateTimeOffset （年、 月、 日、 小时、 分钟、 秒、 tzoffset）](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|在服务器上创建 `datetimeoffset` 带格式的值。<br /><br /> 在 SQL Server 2000 或 SQL Server 2005 中不受支持。|  
|[CreateTime （小时、 分钟、 秒）](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|在服务器上创建 `time` 带格式的值。<br /><br /> 在 SQL Server 2000 或 SQL Server 2005 中不受支持。|  
|[CurrentDateTime()](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`SysDateTime()`（在 SQLServer 2008 中）。<br /><br /> `GetDate()`（在 SQLServer 2000 和 SQLServer 2005 中）。|  
|[CurrentDateTimeOffset()](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`SysDateTimeOffset()`（在 SQL Server 2008 中）。<br /><br /> 在 SQL Server 2000 或 SQL Server 2005 中不受支持。|  
|[CurrentUtcDateTime()](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`SysUtcDateTime()`（在 SQLServer 2008 中）。 `GetUtcDate()`（在 SQL Server 2000 和 SQL Server 2005 中）。|  
|[DayOfYear(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(dayofyear, expression)`|  
|[Day(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(day, expression)`|  
|[DiffDays （startExpression，endExpression）](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(day, startdate, enddate)`|  
|[DiffHours （startExpression，endExpression）](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(hour, startdate, enddate)`|  
|[DiffMicroseconds （startExpression，endExpression）](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(microsecond, startdate, enddate)`|  
|[DiffMilliseconds （startExpression，endExpression）](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(millisecond, startdate, enddate)`|  
|[DiffMinutes （startExpression，endExpression）](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(minute, startdate, enddate)`|  
|[DiffNanoseconds （startExpression，endExpression）](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(nanosecond, startdate, enddate)`|  
|[DiffSeconds （startExpression，endExpression）](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(second, startdate, enddate)`|  
|[DiffYears （startExpression，endExpression）](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(year, startdate, enddate)`|  
|[GetTotalOffsetMinutes(DateTimeOffset)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(tzoffset, expression)`|  
|[Hour(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(hour, expression)`|  
|[Millisecond(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(millisecond, expression)`|  
|[Minute(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(minute, expression)`|  
|[Month(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(month, expression)`|  
|[Second(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(second, expression)`|  
|[Truncate(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|对于 SQL Server 2000 和 SQL Server 2005，被截断的`datetime`在服务器上创建带格式的值。 对于 SQL Server 2008 和更高版本，被截断`datetime2`或`datetimeoffset`在服务器上创建值。|  
|[Year(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)|`DatePart(YEAR, expression)`|  
  
## <a name="aggregate-functions"></a>聚合函数  
 下表介绍了聚合函数映射：  
  
|规范函数|SQL Server 函数|  
|-------------------------|--------------------------|  
|[Avg(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`AVG(expression)`|  
|[BigCount(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`BIGCOUNT(expression)`|  
|[Count(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`COUNT(expression)`|  
|[Min(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`MIN(expression)`|  
|[Max(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`MAX(expression)`|  
|[StDev(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`STDEV(expression)`|  
|[StDevP(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`STDEVP(expression)`|  
|[Sum(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`SUM(expression)`|  
|[Var(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`VAR(expression)`|  
|[VarP(expression)](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)|`VARP(expression)`|  
  
## <a name="math-functions"></a>数学函数  
 下表介绍了数学函数映射：  
  
|规范函数|SQL Server 函数|  
|-------------------------|--------------------------|  
|[Abs(value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`ABS(value)`|  
|[Ceiling(value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`CEILING(value)`|  
|[Floor(value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`FLOOR(value)`|  
|[Power(value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`POWER(value, exponent)`|  
|[Round(value)](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`ROUND(value, digits, 0)`|  
|[截断](../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)|`ROUND(value , digits, 1)`|  
  
## <a name="string-functions"></a>字符串函数  
 下表介绍了字符串函数映射：  
  
|规范函数|SQL Server 函数|  
|-------------------------|--------------------------|  
|[Contains(string, target)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Concat （string1，string2）](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|string1 + string2|  
|[EndsWith （字符串、 目标）](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(REVERSE(target), REVERSE(string)) = 1`<br /><br /> **请注意**`CHARINDEX`函数返回`false`如果`string`固定的长度字符串列中存储和`target`为常量。 在这种情况下，将搜索整个字符串，包括任何填充尾随空格。 一种可行的解决方法是在将字符串传递给 `EndsWith` 函数前，将数据裁剪为固定长度字符串，如下面的示例所示：`EndsWith(TRIM(string), target)`|  
|[IndexOf （目标、 string2）](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(target, string2)`|  
|[左 （string1，长度）](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LEFT(string1, length)`|  
|[长度 （字符串）](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LEN(string)`|  
|[LTrim(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LTRIM(string)`|  
|[右键 （string1，长度）](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`RIGHT (string1, length)`|  
|[Trim(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LTRIM(RTRIM(string))`|  
|[替换 （string1，string2，string3）](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`REPLACE(string1, string2, string3)`|  
|[反向 （字符串）](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`REVERSE (string)`|  
|[RTrim(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`RTRIM(string)`|  
|[StartsWith （字符串、 目标）](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[子字符串 （字符串、 开始、 长度）](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`SUBSTRING(string, start, length)`|  
|[ToLower(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`LOWER(string)`|  
|[ToUpper(string)](../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)|`UPPER(string)`|  
  
## <a name="bitwise-functions"></a>位函数  
 下表介绍了位函数映射：  
  
|规范函数|SQL Server 函数|  
|-------------------------|--------------------------|  
|[BitWiseAnd （value1，value2）](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|value1 & value2|  
|[BitWiseNot （值）](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|~value|  
|[BitWiseOr （value1，value2）](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|value1 &#124;value2|  
|[BitWiseXor （value1，value2）](../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)|value1 ^ value2|
