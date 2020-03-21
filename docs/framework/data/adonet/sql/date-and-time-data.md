---
title: 日期和时间数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6f5ff56a-a57e-49d7-8ae9-bbed697e42e3
ms.openlocfilehash: d7a016b8911cee3091dec24bc26d1f1965f54749
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148759"
---
# <a name="date-and-time-data"></a><span data-ttu-id="73ff4-102">日期和时间数据</span><span class="sxs-lookup"><span data-stu-id="73ff4-102">Date and Time Data</span></span>
<span data-ttu-id="73ff4-103">SQL Server 2008 引入了新数据类型，用于处理日期和时间信息。</span><span class="sxs-lookup"><span data-stu-id="73ff4-103">SQL Server 2008 introduces new data types for handling date and time information.</span></span> <span data-ttu-id="73ff4-104">新数据类型包括独立的日期和时间类型，以及具有更大范围、精度且时区感知的扩展数据类型。</span><span class="sxs-lookup"><span data-stu-id="73ff4-104">The new data types include separate types for date and time, and expanded data types with greater range, precision, and time-zone awareness.</span></span> <span data-ttu-id="73ff4-105">从 .NET Framework 3.5 Service Pack (SP) 1 开始，适用于 SQL Server 的 .NET Framework 数据提供程序 (<xref:System.Data.SqlClient>) 完全支持 SQL Server 2008 数据库引擎的所有新功能。</span><span class="sxs-lookup"><span data-stu-id="73ff4-105">Starting with the .NET Framework version 3.5 Service Pack (SP) 1, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides full support for all the new features of the SQL Server 2008 Database Engine.</span></span> <span data-ttu-id="73ff4-106">您必须安装 .NET Framework 3.5 SP1（或更高版本）才能将这些新功能与 SqlClient 一起使用。</span><span class="sxs-lookup"><span data-stu-id="73ff4-106">You must install the .NET Framework 3.5 SP1 (or later) to use these new features with SqlClient.</span></span>  
  
 <span data-ttu-id="73ff4-107">SQL Server 2008 之前的 SQL Server 版本仅具有两种用于处理日期和时间值的数据类型：`datetime` 和 `smalldatetime`。</span><span class="sxs-lookup"><span data-stu-id="73ff4-107">Versions of SQL Server earlier than SQL Server 2008 only had two data types for working with date and time values: `datetime` and `smalldatetime`.</span></span> <span data-ttu-id="73ff4-108">这两种数据类型都同时包含日期值和时间值，难以仅使用日期值或仅使用时间值。</span><span class="sxs-lookup"><span data-stu-id="73ff4-108">Both of these data types contain both the date value and a time value, which makes it difficult to work with only date or only time values.</span></span> <span data-ttu-id="73ff4-109">此外，这些数据类型只支持在 1753 年英国引入公历之后的日期。</span><span class="sxs-lookup"><span data-stu-id="73ff4-109">Also, these data types only support dates that occur after the introduction of the Gregorian calendar in England in 1753.</span></span> <span data-ttu-id="73ff4-110">另一个限制是，这些旧数据类型无法感知时区，这使得处理来自多个时区的数据变得困难。</span><span class="sxs-lookup"><span data-stu-id="73ff4-110">Another limitation is that these older data types are not time-zone aware, which makes it difficult to work with data that originates from multiple time zones.</span></span>  
  
 <span data-ttu-id="73ff4-111">SQL Server 联机丛书中有关于 SQL Server 数据类型的完整文档。</span><span class="sxs-lookup"><span data-stu-id="73ff4-111">Complete documentation for SQL Server data types is available in SQL Server Books Online.</span></span> <span data-ttu-id="73ff4-112">下表列出了有关日期和时间数据的因版本而异的入门级主题。</span><span class="sxs-lookup"><span data-stu-id="73ff4-112">The following table lists the version-specific entry-level topics for date and time data.</span></span>  
  
 <span data-ttu-id="73ff4-113">**SQL 服务器文档**</span><span class="sxs-lookup"><span data-stu-id="73ff4-113">**SQL Server documentation**</span></span>  
  
1. <span data-ttu-id="73ff4-114">[使用日期和时间数据](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="73ff4-114">[Using Date and Time Data](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))</span></span>  
  
## <a name="datetime-data-types-introduced-in-sql-server-2008"></a><span data-ttu-id="73ff4-115">SQL Server 2008 中引入的日期/时间数据类型</span><span class="sxs-lookup"><span data-stu-id="73ff4-115">Date/Time Data Types Introduced in SQL Server 2008</span></span>  
 <span data-ttu-id="73ff4-116">下表介绍了新日期和时间数据类型。</span><span class="sxs-lookup"><span data-stu-id="73ff4-116">The following table describes the new date and time data types.</span></span>  
  
|<span data-ttu-id="73ff4-117">SQL Server 数据类型</span><span class="sxs-lookup"><span data-stu-id="73ff4-117">SQL Server data type</span></span>|<span data-ttu-id="73ff4-118">说明</span><span class="sxs-lookup"><span data-stu-id="73ff4-118">Description</span></span>|  
|--------------------------|-----------------|  
|`date`|<span data-ttu-id="73ff4-119">`date` 数据类型的范围从 01 年 1 月 1 日 9999 年 12 月 31 日，精确到 1 天。</span><span class="sxs-lookup"><span data-stu-id="73ff4-119">The `date` data type has a range of January 1, 01 through December 31, 9999 with an accuracy of 1 day.</span></span> <span data-ttu-id="73ff4-120">默认值为 January 1, 1900。</span><span class="sxs-lookup"><span data-stu-id="73ff4-120">The default value is January 1, 1900.</span></span> <span data-ttu-id="73ff4-121">存储大小为 3 个字节。</span><span class="sxs-lookup"><span data-stu-id="73ff4-121">The storage size is 3 bytes.</span></span>|  
|`time`|<span data-ttu-id="73ff4-122">`time` 数据类型仅采用 24 小时制存储时间值。</span><span class="sxs-lookup"><span data-stu-id="73ff4-122">The `time` data type stores time values only, based on a 24-hour clock.</span></span> <span data-ttu-id="73ff4-123">`time` 数据类型介于 00:00:00.0000000 到 23:59:59.9999999 范围之间，准确度为 100 纳秒。</span><span class="sxs-lookup"><span data-stu-id="73ff4-123">The `time` data type has a range of 00:00:00.0000000 through 23:59:59.9999999 with an accuracy of 100 nanoseconds.</span></span> <span data-ttu-id="73ff4-124">默认值为 00:00:00.0000000（午夜）。</span><span class="sxs-lookup"><span data-stu-id="73ff4-124">The default value is 00:00:00.0000000 (midnight).</span></span> <span data-ttu-id="73ff4-125">`time` 数据类型支持用户定义的小数秒精度，存储大小根据指定的精度在 3 字节到 6 字节之间变化。</span><span class="sxs-lookup"><span data-stu-id="73ff4-125">The `time` data type supports user-defined fractional second precision, and the storage size varies from 3 to 6 bytes, based on the precision specified.</span></span>|  
|`datetime2`|<span data-ttu-id="73ff4-126">`datetime2` 数据类型将 `date` 和 `time` 数据类型的范围和精度合并为一个数据类型。</span><span class="sxs-lookup"><span data-stu-id="73ff4-126">The `datetime2` data type combines the range and precision of the `date` and `time` data types into a single data type.</span></span><br /><br /> <span data-ttu-id="73ff4-127">默认值和字符串文本格式与 `date` 和 `time` 数据类型中定义的相同。</span><span class="sxs-lookup"><span data-stu-id="73ff4-127">The default values and string literal formats are the same as those defined in the `date` and `time` data types.</span></span>|  
|`datetimeoffset`|<span data-ttu-id="73ff4-128">`datetimeoffset` 数据类型具有 `datetime2` 的所有功能，并添加了时区偏移量。</span><span class="sxs-lookup"><span data-stu-id="73ff4-128">The `datetimeoffset` data type has all the features of `datetime2` with an additional time zone offset.</span></span> <span data-ttu-id="73ff4-129">时区偏移量表示为 [+&#124;-] HH:MM。</span><span class="sxs-lookup"><span data-stu-id="73ff4-129">The time zone offset is represented as [+&#124;-] HH:MM.</span></span> <span data-ttu-id="73ff4-130">HH 是两位数，介于 00 和 14 范围之间，表示时区偏移量中的小时数。</span><span class="sxs-lookup"><span data-stu-id="73ff4-130">HH is 2 digits ranging from 00 to 14 that represent the number of hours in the time zone offset.</span></span> <span data-ttu-id="73ff4-131">MM 是两位数，范围为 00 到 59，表示时区偏移量中的额外分钟数。</span><span class="sxs-lookup"><span data-stu-id="73ff4-131">MM is 2 digits ranging from 00 to 59 that represent the number of additional minutes in the time zone offset.</span></span> <span data-ttu-id="73ff4-132">时间格式支持到 100 毫微秒。</span><span class="sxs-lookup"><span data-stu-id="73ff4-132">Time formats are supported to 100 nanoseconds.</span></span> <span data-ttu-id="73ff4-133">必需符号 + 或 - 指明是在 UTC（协调世界时或格林威治标准时间）中加上还是减去时区偏移来获得本地时间。</span><span class="sxs-lookup"><span data-stu-id="73ff4-133">The mandatory + or - sign indicates whether the time zone offset is added or subtracted from UTC (Universal Time Coordinate or Greenwich Mean Time) to obtain the local time.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="73ff4-134">要详细了解如何使用 `Type System Version`，请参阅 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>。</span><span class="sxs-lookup"><span data-stu-id="73ff4-134">For more information about using the `Type System Version` keyword, see <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>  
  
## <a name="date-format-and-date-order"></a><span data-ttu-id="73ff4-135">日期格式和日期顺序</span><span class="sxs-lookup"><span data-stu-id="73ff4-135">Date Format and Date Order</span></span>  
 <span data-ttu-id="73ff4-136">SQL Server 如何分析日期和时间值不仅取决于类型系统版本和服务器版本，还取决于服务器的默认语言和格式设置。</span><span class="sxs-lookup"><span data-stu-id="73ff4-136">How SQL Server parses date and time values depends not only on the type system version and server version, but also on the server's default language and format settings.</span></span> <span data-ttu-id="73ff4-137">如果日期格式使用一种语言，而查询是通过使用不同语言和日期格式设置的连接执行的，那么可能无法识别采用日期格式的日期字符串。</span><span class="sxs-lookup"><span data-stu-id="73ff4-137">A date string that works for the date formats of one language might be unrecognizable if the query is executed by a connection that uses a different language and date format setting.</span></span>  
  
 <span data-ttu-id="73ff4-138">Transact-SQL SET LANGUAGE 语句隐式设置确定日期部分顺序的 DATEFORMAT。</span><span class="sxs-lookup"><span data-stu-id="73ff4-138">The Transact-SQL SET LANGUAGE statement implicitly sets the DATEFORMAT that determines the order of the date parts.</span></span> <span data-ttu-id="73ff4-139">可以通过按 MDY、DMY、YMD、YDM、MYD 或 DYM 顺序对日期部分进行排序，对连接使用 SET DATEFORMAT Transact-SQL 语句来区分日期值。</span><span class="sxs-lookup"><span data-stu-id="73ff4-139">You can use the SET DATEFORMAT Transact-SQL statement on a connection to disambiguate date values by ordering the date parts in MDY, DMY, YMD, YDM, MYD, or DYM order.</span></span>  
  
 <span data-ttu-id="73ff4-140">如果你没有为连接指定任何 DATEFORMAT，SQL Server 会使用与连接关联的默认语言。</span><span class="sxs-lookup"><span data-stu-id="73ff4-140">If you do not specify any DATEFORMAT for the connection, SQL Server uses the default language associated with the connection.</span></span> <span data-ttu-id="73ff4-141">例如，为日期字符串“01/02/03”在语言设置为美式英语的服务器上解析为 MDY（2003 年 1 月 2 日），而在语言设置为英式英语的服务器上则解析为 DMY（2003 年 2 月 1 日）。</span><span class="sxs-lookup"><span data-stu-id="73ff4-141">For example, a date string of '01/02/03' would be interpreted as MDY (January 2, 2003) on a server with a language setting of United States English, and as DMY (February 1, 2003) on a server with a language setting of British English.</span></span> <span data-ttu-id="73ff4-142">年份是由 SQL Server 的临界年份规则确定的，此规则定义了用于指定世纪值的临界日期。</span><span class="sxs-lookup"><span data-stu-id="73ff4-142">The year is determined by using SQL Server's cutoff year rule, which defines the cutoff date for assigning the century value.</span></span> <span data-ttu-id="73ff4-143">有关详细信息，请参阅[两位数字的年截止选项](/sql/database-engine/configure-windows/configure-the-two-digit-year-cutoff-server-configuration-option)。</span><span class="sxs-lookup"><span data-stu-id="73ff4-143">For more information, see [two digit year cutoff Option](/sql/database-engine/configure-windows/configure-the-two-digit-year-cutoff-server-configuration-option).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="73ff4-144">从字符串格式转换为 `date`、`time`、`datetime2` 或 `datetimeoffset` 时，不支持使用 YDM 日期格式。</span><span class="sxs-lookup"><span data-stu-id="73ff4-144">The YDM date format is not supported when converting from a string format to `date`, `time`, `datetime2`, or `datetimeoffset`.</span></span>  
  
 <span data-ttu-id="73ff4-145">有关 SQL Server 如何解释日期和时间数据的详细信息，请参阅[使用日期和时间数据](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))。</span><span class="sxs-lookup"><span data-stu-id="73ff4-145">For more information about how SQL Server interprets date and time data, see [Using Date and Time Data](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms180878(v=sql.100)).</span></span>  
  
## <a name="datetime-data-types-and-parameters"></a><span data-ttu-id="73ff4-146">日期/时间数据类型和参数</span><span class="sxs-lookup"><span data-stu-id="73ff4-146">Date/Time Data Types and Parameters</span></span>  
 <span data-ttu-id="73ff4-147">为了支持新日期和时间数据类型，已向 <xref:System.Data.SqlDbType> 中添加了下列枚举。</span><span class="sxs-lookup"><span data-stu-id="73ff4-147">The following enumerations have been added to <xref:System.Data.SqlDbType> to support the new date and time data types.</span></span>  
  
- `SqlDbType.Date`  
  
- `SqlDbType.Time`  
  
- `SqlDbType.DateTime2`  
  
- `SqlDbType.DateTimeOffSet`  

<span data-ttu-id="73ff4-148">通过使用 <xref:System.Data.SqlDbType> 枚举之一，可以指定 <xref:System.Data.SqlClient.SqlParameter> 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="73ff4-148">You can specify the data type of a <xref:System.Data.SqlClient.SqlParameter> by using one of the preceding <xref:System.Data.SqlDbType> enumerations.</span></span>

> [!NOTE]
> <span data-ttu-id="73ff4-149">无法将 `SqlParameter` 的 `DbType` 属性设置为 `SqlDbType.Date`。</span><span class="sxs-lookup"><span data-stu-id="73ff4-149">You cannot set the `DbType` property of a `SqlParameter` to `SqlDbType.Date`.</span></span>

 <span data-ttu-id="73ff4-150">也可以采用通用的方式通过将 `SqlParameter` 对象的 <xref:System.Data.SqlClient.SqlParameter.DbType%2A> 属性设置为特定的 <xref:System.Data.DbType> 枚举值来指定 <xref:System.Data.SqlClient.SqlParameter> 的类型。</span><span class="sxs-lookup"><span data-stu-id="73ff4-150">You can also specify the type of a <xref:System.Data.SqlClient.SqlParameter> generically by setting the <xref:System.Data.SqlClient.SqlParameter.DbType%2A> property of a `SqlParameter` object to a particular <xref:System.Data.DbType> enumeration value.</span></span> <span data-ttu-id="73ff4-151"><xref:System.Data.DbType> 中已添加了下面的枚举值，以支持 `datetime2` 和 `datetimeoffset` 数据类型：</span><span class="sxs-lookup"><span data-stu-id="73ff4-151">The following enumeration values have been added to <xref:System.Data.DbType> to support the `datetime2` and `datetimeoffset` data types:</span></span>  
  
- <span data-ttu-id="73ff4-152">DbType.DateTime2</span><span class="sxs-lookup"><span data-stu-id="73ff4-152">DbType.DateTime2</span></span>  
  
- <span data-ttu-id="73ff4-153">DbType.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="73ff4-153">DbType.DateTimeOffset</span></span>  
  
 <span data-ttu-id="73ff4-154">这些新枚举补充了早期版本的 .NET Framework 中存在的 `Date`、`Time` 和 `DateTime` 枚举。</span><span class="sxs-lookup"><span data-stu-id="73ff4-154">These new enumerations supplement the `Date`, `Time`, and `DateTime` enumerations, which existed in earlier versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="73ff4-155">某一参数对象的 .NET Framework 数据提供程序类型是从该参数对象的 .NET Framework 类型或该参数对象的 `DbType` 推断而来的。</span><span class="sxs-lookup"><span data-stu-id="73ff4-155">The .NET Framework data provider type of a parameter object is inferred from the .NET Framework type of the value of the parameter object, or from the `DbType` of the parameter object.</span></span> <span data-ttu-id="73ff4-156">没有引入新 <xref:System.Data.SqlTypes> 数据类型来支持新日期和时间数据类型。</span><span class="sxs-lookup"><span data-stu-id="73ff4-156">No new <xref:System.Data.SqlTypes> data types have been introduced to support the new date and time data types.</span></span> <span data-ttu-id="73ff4-157">下表介绍了 SQL Server 2008 日期和时间数据类型与 CLR 数据类型之间的映射。</span><span class="sxs-lookup"><span data-stu-id="73ff4-157">The following table describes the mappings between the SQL Server 2008 date and time data types and the CLR data types.</span></span>  
  
|<span data-ttu-id="73ff4-158">SQL Server 数据类型</span><span class="sxs-lookup"><span data-stu-id="73ff4-158">SQL Server data type</span></span>|<span data-ttu-id="73ff4-159">.NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="73ff4-159">.NET Framework type</span></span>|<span data-ttu-id="73ff4-160">System.Data.SqlDbType</span><span class="sxs-lookup"><span data-stu-id="73ff4-160">System.Data.SqlDbType</span></span>|<span data-ttu-id="73ff4-161">System.Data.DbType</span><span class="sxs-lookup"><span data-stu-id="73ff4-161">System.Data.DbType</span></span>|  
|--------------------------|-------------------------|---------------------------|------------------------|  
|<span data-ttu-id="73ff4-162">date</span><span class="sxs-lookup"><span data-stu-id="73ff4-162">date</span></span>|<span data-ttu-id="73ff4-163">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="73ff4-163">System.DateTime</span></span>|<span data-ttu-id="73ff4-164">Date</span><span class="sxs-lookup"><span data-stu-id="73ff4-164">Date</span></span>|<span data-ttu-id="73ff4-165">Date</span><span class="sxs-lookup"><span data-stu-id="73ff4-165">Date</span></span>|  
|<span data-ttu-id="73ff4-166">time</span><span class="sxs-lookup"><span data-stu-id="73ff4-166">time</span></span>|<span data-ttu-id="73ff4-167">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="73ff4-167">System.TimeSpan</span></span>|<span data-ttu-id="73ff4-168">时间</span><span class="sxs-lookup"><span data-stu-id="73ff4-168">Time</span></span>|<span data-ttu-id="73ff4-169">时间</span><span class="sxs-lookup"><span data-stu-id="73ff4-169">Time</span></span>|  
|<span data-ttu-id="73ff4-170">datetime2</span><span class="sxs-lookup"><span data-stu-id="73ff4-170">datetime2</span></span>|<span data-ttu-id="73ff4-171">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="73ff4-171">System.DateTime</span></span>|<span data-ttu-id="73ff4-172">DateTime2</span><span class="sxs-lookup"><span data-stu-id="73ff4-172">DateTime2</span></span>|<span data-ttu-id="73ff4-173">DateTime2</span><span class="sxs-lookup"><span data-stu-id="73ff4-173">DateTime2</span></span>|  
|<span data-ttu-id="73ff4-174">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="73ff4-174">datetimeoffset</span></span>|<span data-ttu-id="73ff4-175">System.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="73ff4-175">System.DateTimeOffset</span></span>|<span data-ttu-id="73ff4-176">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="73ff4-176">DateTimeOffset</span></span>|<span data-ttu-id="73ff4-177">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="73ff4-177">DateTimeOffset</span></span>|  
|<span data-ttu-id="73ff4-178">datetime</span><span class="sxs-lookup"><span data-stu-id="73ff4-178">datetime</span></span>|<span data-ttu-id="73ff4-179">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="73ff4-179">System.DateTime</span></span>|<span data-ttu-id="73ff4-180">DateTime</span><span class="sxs-lookup"><span data-stu-id="73ff4-180">DateTime</span></span>|<span data-ttu-id="73ff4-181">DateTime</span><span class="sxs-lookup"><span data-stu-id="73ff4-181">DateTime</span></span>|  
|<span data-ttu-id="73ff4-182">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="73ff4-182">smalldatetime</span></span>|<span data-ttu-id="73ff4-183">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="73ff4-183">System.DateTime</span></span>|<span data-ttu-id="73ff4-184">DateTime</span><span class="sxs-lookup"><span data-stu-id="73ff4-184">DateTime</span></span>|<span data-ttu-id="73ff4-185">DateTime</span><span class="sxs-lookup"><span data-stu-id="73ff4-185">DateTime</span></span>|  
  
### <a name="sqlparameter-properties"></a><span data-ttu-id="73ff4-186">SqlParameter 属性</span><span class="sxs-lookup"><span data-stu-id="73ff4-186">SqlParameter Properties</span></span>  
 <span data-ttu-id="73ff4-187">下表介绍了与日期和时间数据类型相关的 `SqlParameter` 属性。</span><span class="sxs-lookup"><span data-stu-id="73ff4-187">The following table describes `SqlParameter` properties that are relevant to date and time data types.</span></span>  
  
|<span data-ttu-id="73ff4-188">properties</span><span class="sxs-lookup"><span data-stu-id="73ff4-188">Property</span></span>|<span data-ttu-id="73ff4-189">说明</span><span class="sxs-lookup"><span data-stu-id="73ff4-189">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.IsNullable%2A>|<span data-ttu-id="73ff4-190">获取或设置值是否可为空。</span><span class="sxs-lookup"><span data-stu-id="73ff4-190">Gets or sets whether a value is nullable.</span></span> <span data-ttu-id="73ff4-191">将空参数值发送到服务器时，必须指定 <xref:System.DBNull>，而不是 `null`（在 Visual Basic 中为 `Nothing`）。</span><span class="sxs-lookup"><span data-stu-id="73ff4-191">When you send a null parameter value to the server, you must specify <xref:System.DBNull>, rather than `null` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="73ff4-192">有关数据库 null 的详细信息，请参阅[处理空值](handling-null-values.md)。</span><span class="sxs-lookup"><span data-stu-id="73ff4-192">For more information about database nulls, see [Handling Null Values](handling-null-values.md).</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Precision%2A>|<span data-ttu-id="73ff4-193">获取或设置用于表示该值的最大位数。</span><span class="sxs-lookup"><span data-stu-id="73ff4-193">Gets or sets the maximum number of digits used to represent the value.</span></span> <span data-ttu-id="73ff4-194">对于日期和时间数据类型，此设置将被忽略。</span><span class="sxs-lookup"><span data-stu-id="73ff4-194">This setting is ignored for date and time data types.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Scale%2A>|<span data-ttu-id="73ff4-195">获取或设置要将 `Time`、`DateTime2` 和 `DateTimeOffset` 值的时间部分解析到的小数位数。</span><span class="sxs-lookup"><span data-stu-id="73ff4-195">Gets or sets the number of decimal places to which the time portion of the value is resolved for `Time`, `DateTime2`,and `DateTimeOffset`.</span></span> <span data-ttu-id="73ff4-196">默认值为 0；也就是说，实际确定位数是根据值推断出来并发送到服务器的。</span><span class="sxs-lookup"><span data-stu-id="73ff4-196">The default value is 0, which means that the actual scale is inferred from the value and sent to the server.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|<span data-ttu-id="73ff4-197">对于日期和时间数据类型，此属性将被忽略。</span><span class="sxs-lookup"><span data-stu-id="73ff4-197">Ignored for date and time data types.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|<span data-ttu-id="73ff4-198">获取或设置参数值。</span><span class="sxs-lookup"><span data-stu-id="73ff4-198">Gets or sets the parameter value.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|<span data-ttu-id="73ff4-199">获取或设置参数值。</span><span class="sxs-lookup"><span data-stu-id="73ff4-199">Gets or sets the parameter value.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="73ff4-200">小于零或大于等于 24 小时的时间值会导致 <xref:System.ArgumentException> 抛出。</span><span class="sxs-lookup"><span data-stu-id="73ff4-200">Time values that are less than zero or greater than or equal to 24 hours will throw an <xref:System.ArgumentException>.</span></span>  
  
### <a name="creating-parameters"></a><span data-ttu-id="73ff4-201">创建参数</span><span class="sxs-lookup"><span data-stu-id="73ff4-201">Creating Parameters</span></span>  
 <span data-ttu-id="73ff4-202">可以通过以下方法来创建 <xref:System.Data.SqlClient.SqlParameter> 对象：使用相应的构造函数；或者通过调用 <xref:System.Data.SqlClient.SqlCommand> 的 <xref:System.Data.SqlClient.SqlCommand.Parameters%2A> 方法将其添加到 `Add`<xref:System.Data.SqlClient.SqlParameterCollection> 集合。</span><span class="sxs-lookup"><span data-stu-id="73ff4-202">You can create a <xref:System.Data.SqlClient.SqlParameter> object by using its constructor, or by adding it to a <xref:System.Data.SqlClient.SqlCommand><xref:System.Data.SqlClient.SqlCommand.Parameters%2A> collection by calling the `Add` method of the <xref:System.Data.SqlClient.SqlParameterCollection>.</span></span> <span data-ttu-id="73ff4-203">`Add` 方法需要使用构造函数参数或现有参数对象作为输入。</span><span class="sxs-lookup"><span data-stu-id="73ff4-203">The `Add` method will take as input either constructor arguments or an existing parameter object.</span></span>  
  
 <span data-ttu-id="73ff4-204">本主题接下来的几个部分举例介绍了如何指定日期和时间参数。</span><span class="sxs-lookup"><span data-stu-id="73ff4-204">The next sections in this topic provide examples of how to specify date and time parameters.</span></span> <span data-ttu-id="73ff4-205">有关使用参数的其他示例，请参阅[配置参数和参数数据类型](../configuring-parameters-and-parameter-data-types.md)和[数据适配器参数](../dataadapter-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="73ff4-205">For additional examples of working with parameters, see [Configuring Parameters and Parameter Data Types](../configuring-parameters-and-parameter-data-types.md) and [DataAdapter Parameters](../dataadapter-parameters.md).</span></span>  
  
### <a name="date-example"></a><span data-ttu-id="73ff4-206">date 示例</span><span class="sxs-lookup"><span data-stu-id="73ff4-206">Date Example</span></span>  
 <span data-ttu-id="73ff4-207">下面的代码片段展示了如何指定 `date` 参数。</span><span class="sxs-lookup"><span data-stu-id="73ff4-207">The following code fragment demonstrates how to specify a `date` parameter.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@Date";  
parameter.SqlDbType = SqlDbType.Date;  
parameter.Value = "2007/12/1";  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Date"  
parameter.SqlDbType = SqlDbType.Date  
parameter.Value = "2007/12/1"  
```  
  
### <a name="time-example"></a><span data-ttu-id="73ff4-208">time 示例</span><span class="sxs-lookup"><span data-stu-id="73ff4-208">Time Example</span></span>  
 <span data-ttu-id="73ff4-209">下面的代码片段展示了如何指定 `time` 参数。</span><span class="sxs-lookup"><span data-stu-id="73ff4-209">The following code fragment demonstrates how to specify a `time` parameter.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@time";  
parameter.SqlDbType = SqlDbType.Time;  
parameter.Value = DateTime.Parse("23:59:59").TimeOfDay;  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Time"  
parameter.SqlDbType = SqlDbType.Time  
parameter.Value = DateTime.Parse("23:59:59").TimeOfDay;  
```  
  
### <a name="datetime2-example"></a><span data-ttu-id="73ff4-210">datetime2 示例</span><span class="sxs-lookup"><span data-stu-id="73ff4-210">Datetime2 Example</span></span>  
 <span data-ttu-id="73ff4-211">下面的代码片段展示了如何指定同时包含日期和时间部分的 `datetime2` 参数。</span><span class="sxs-lookup"><span data-stu-id="73ff4-211">The following code fragment demonstrates how to specify a `datetime2` parameter with both the date and time parts.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@Datetime2";  
parameter.SqlDbType = SqlDbType.DateTime2;  
parameter.Value = DateTime.Parse("1666-09-02 1:00:00");  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Datetime2"  
parameter.SqlDbType = SqlDbType.DateTime2  
parameter.Value = DateTime.Parse("1666-09-02 1:00:00");  
```  
  
### <a name="datetimeoffset-example"></a><span data-ttu-id="73ff4-212">DateTimeOffSet 示例</span><span class="sxs-lookup"><span data-stu-id="73ff4-212">DateTimeOffSet Example</span></span>  
 <span data-ttu-id="73ff4-213">下面的代码片段展示了如何指定包含日期、时间和时区偏移 0 的 `DateTimeOffSet` 参数。</span><span class="sxs-lookup"><span data-stu-id="73ff4-213">The following code fragment demonstrates how to specify a `DateTimeOffSet` parameter with a date, a time, and a time zone offset of 0.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@DateTimeOffSet";  
parameter.SqlDbType = SqlDbType.DateTimeOffSet;  
parameter.Value = DateTimeOffset.Parse("1666-09-02 1:00:00+0");  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@DateTimeOffSet"  
parameter.SqlDbType = SqlDbType.DateTimeOffSet  
parameter.Value = DateTimeOffset.Parse("1666-09-02 1:00:00+0");  
```  
  
### <a name="addwithvalue"></a><span data-ttu-id="73ff4-214">AddWithValue</span><span class="sxs-lookup"><span data-stu-id="73ff4-214">AddWithValue</span></span>  
 <span data-ttu-id="73ff4-215">也可以使用 <xref:System.Data.SqlClient.SqlCommand> 的 `AddWithValue` 方法来提供参数，如下面的代码片段所示。</span><span class="sxs-lookup"><span data-stu-id="73ff4-215">You can also supply parameters by using the `AddWithValue` method of a <xref:System.Data.SqlClient.SqlCommand>, as shown in the following code fragment.</span></span> <span data-ttu-id="73ff4-216">不过，`AddWithValue` 方法不允许为参数指定 <xref:System.Data.SqlClient.SqlParameter.DbType%2A> 或 <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A>。</span><span class="sxs-lookup"><span data-stu-id="73ff4-216">However, the `AddWithValue` method does not allow you to specify the <xref:System.Data.SqlClient.SqlParameter.DbType%2A> or <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> for the parameter.</span></span>  
  
```csharp  
command.Parameters.AddWithValue(
    "@date", DateTimeOffset.Parse("16660902"));  
```  
  
```vb  
command.Parameters.AddWithValue( _  
    "@date", DateTimeOffset.Parse("16660902"))  
```  
  
 <span data-ttu-id="73ff4-217">`@date` 参数可映射到服务器上的 `date`、`datetime` 或 `datetime2` 数据类型。</span><span class="sxs-lookup"><span data-stu-id="73ff4-217">The `@date` parameter could map to a `date`, `datetime`, or `datetime2` data type on the server.</span></span> <span data-ttu-id="73ff4-218">使用新 `datetime` 数据类型时，必须将参数的 <xref:System.Data.SqlDbType> 属性显式设置为实例的数据类型。</span><span class="sxs-lookup"><span data-stu-id="73ff4-218">When working with the new `datetime` data types, you must explicitly set the parameter's <xref:System.Data.SqlDbType> property to the data type of the instance.</span></span> <span data-ttu-id="73ff4-219">使用 <xref:System.Data.SqlDbType.Variant> 或隐式提供参数值可能会导致与 `datetime` 和 `smalldatetime` 数据类型出现向后兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="73ff4-219">Using <xref:System.Data.SqlDbType.Variant> or implicitly supplying parameter values can cause problems with backward compatibility with the `datetime` and `smalldatetime` data types.</span></span>  
  
 <span data-ttu-id="73ff4-220">下表展示了哪些 `SqlDbTypes` 是根据哪些 CLR 类型推断出来的：</span><span class="sxs-lookup"><span data-stu-id="73ff4-220">The following table shows which `SqlDbTypes` are inferred from which CLR types:</span></span>  
  
|<span data-ttu-id="73ff4-221">CLR 类型</span><span class="sxs-lookup"><span data-stu-id="73ff4-221">CLR type</span></span>|<span data-ttu-id="73ff4-222">Inferred SqlDbType</span><span class="sxs-lookup"><span data-stu-id="73ff4-222">Inferred SqlDbType</span></span>|  
|--------------|------------------------|  
|<span data-ttu-id="73ff4-223">DateTime</span><span class="sxs-lookup"><span data-stu-id="73ff4-223">DateTime</span></span>|<span data-ttu-id="73ff4-224">SqlDbType.DateTime</span><span class="sxs-lookup"><span data-stu-id="73ff4-224">SqlDbType.DateTime</span></span>|  
|<span data-ttu-id="73ff4-225">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="73ff4-225">TimeSpan</span></span>|<span data-ttu-id="73ff4-226">SqlDbType.Time</span><span class="sxs-lookup"><span data-stu-id="73ff4-226">SqlDbType.Time</span></span>|  
|<span data-ttu-id="73ff4-227">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="73ff4-227">DateTimeOffset</span></span>|<span data-ttu-id="73ff4-228">SqlDbType.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="73ff4-228">SqlDbType.DateTimeOffset</span></span>|  
  
## <a name="retrieving-date-and-time-data"></a><span data-ttu-id="73ff4-229">检索日期和时间数据</span><span class="sxs-lookup"><span data-stu-id="73ff4-229">Retrieving Date and Time Data</span></span>  
 <span data-ttu-id="73ff4-230">下表说明用于检索 SQL Server 2008 日期和时间值的方法。</span><span class="sxs-lookup"><span data-stu-id="73ff4-230">The following table describes methods that are used to retrieve SQL Server 2008 date and time values.</span></span>  
  
|<span data-ttu-id="73ff4-231">SqlClient 方法</span><span class="sxs-lookup"><span data-stu-id="73ff4-231">SqlClient method</span></span>|<span data-ttu-id="73ff4-232">说明</span><span class="sxs-lookup"><span data-stu-id="73ff4-232">Description</span></span>|  
|----------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|<span data-ttu-id="73ff4-233">以 <xref:System.DateTime> 结构形式检索指定的列值。</span><span class="sxs-lookup"><span data-stu-id="73ff4-233">Retrieves the specified column value as a <xref:System.DateTime> structure.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTimeOffset%2A>|<span data-ttu-id="73ff4-234">以 <xref:System.DateTimeOffset> 结构形式检索指定的列值。</span><span class="sxs-lookup"><span data-stu-id="73ff4-234">Retrieves the specified column value as a <xref:System.DateTimeOffset> structure.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>|<span data-ttu-id="73ff4-235">返回作为字段的基础提供程序专用类型的类型。</span><span class="sxs-lookup"><span data-stu-id="73ff4-235">Returns the type that is the underlying provider-specific type for the field.</span></span> <span data-ttu-id="73ff4-236">对于新日期和时间类型，返回与 `GetFieldType` 相同的类型。</span><span class="sxs-lookup"><span data-stu-id="73ff4-236">Returns the same types as `GetFieldType` for new date and time types.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>|<span data-ttu-id="73ff4-237">获取指定列的值。</span><span class="sxs-lookup"><span data-stu-id="73ff4-237">Retrieves the value of the specified column.</span></span> <span data-ttu-id="73ff4-238">对于新日期和时间类型，返回与 `GetValue` 相同的类型。</span><span class="sxs-lookup"><span data-stu-id="73ff4-238">Returns the same types as `GetValue` for the new date and time types.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>|<span data-ttu-id="73ff4-239">检索指定数组中的值。</span><span class="sxs-lookup"><span data-stu-id="73ff4-239">Retrieves the values in the specified array.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|<span data-ttu-id="73ff4-240">检索列值作为 <xref:System.Data.SqlTypes.SqlString>。</span><span class="sxs-lookup"><span data-stu-id="73ff4-240">Retrieves the column value as a <xref:System.Data.SqlTypes.SqlString>.</span></span> <span data-ttu-id="73ff4-241">如果数据无法表示为 `SqlString`，则会导致 <xref:System.InvalidCastException> 抛出。</span><span class="sxs-lookup"><span data-stu-id="73ff4-241">An <xref:System.InvalidCastException> occurs if the data cannot be expressed as a `SqlString`.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>|<span data-ttu-id="73ff4-242">检索列数据作为默认 `SqlDbType`。</span><span class="sxs-lookup"><span data-stu-id="73ff4-242">Retrieves column data as its default `SqlDbType`.</span></span> <span data-ttu-id="73ff4-243">对于新日期和时间类型，返回与 `GetValue` 相同的类型。</span><span class="sxs-lookup"><span data-stu-id="73ff4-243">Returns the same types as `GetValue` for the new date and time types.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>|<span data-ttu-id="73ff4-244">检索指定数组中的值。</span><span class="sxs-lookup"><span data-stu-id="73ff4-244">Retrieves the values in the specified array.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A>|<span data-ttu-id="73ff4-245">如果 Type System Version 设置为 SQL Server 2005，则以字符串形式检索列值。</span><span class="sxs-lookup"><span data-stu-id="73ff4-245">Retrieves the column value as a string if the Type System Version is set to SQL Server 2005.</span></span> <span data-ttu-id="73ff4-246">如果数据无法表示为字符串，则会导致 <xref:System.InvalidCastException> 抛出。</span><span class="sxs-lookup"><span data-stu-id="73ff4-246">An <xref:System.InvalidCastException> occurs if the data cannot be expressed as a string.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetTimeSpan%2A>|<span data-ttu-id="73ff4-247">以 <xref:System.TimeSpan> 结构形式检索指定的列值。</span><span class="sxs-lookup"><span data-stu-id="73ff4-247">Retrieves the specified column value as a <xref:System.TimeSpan> structure.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>|<span data-ttu-id="73ff4-248">检索指定列值作为基础 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="73ff4-248">Retrieves the specified column value as its underlying CLR type.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>|<span data-ttu-id="73ff4-249">检索数组中的列值。</span><span class="sxs-lookup"><span data-stu-id="73ff4-249">Retrieves column values in an array.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>|<span data-ttu-id="73ff4-250">返回描述结果集的元数据的 <xref:System.Data.DataTable>。</span><span class="sxs-lookup"><span data-stu-id="73ff4-250">Returns a <xref:System.Data.DataTable> that describes the metadata of the result set.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="73ff4-251">正在 SQL Server 中执行的代码不支持新日期和时间 `SqlDbTypes`。</span><span class="sxs-lookup"><span data-stu-id="73ff4-251">The new date and time `SqlDbTypes` are not supported for code that is executing in-process in SQL Server.</span></span> <span data-ttu-id="73ff4-252">如果将其中一种类型传递给服务器，则会导致异常抛出。</span><span class="sxs-lookup"><span data-stu-id="73ff4-252">An exception will be raised if one of these types is passed to the server.</span></span>  
  
## <a name="specifying-date-and-time-values-as-literals"></a><span data-ttu-id="73ff4-253">作为文字指定日期和时间值</span><span class="sxs-lookup"><span data-stu-id="73ff4-253">Specifying Date and Time Values as Literals</span></span>  
 <span data-ttu-id="73ff4-254">可以使用各种不同的文本字符串格式来指定日期和时间数据类型，随后 SQL Server 在运行时进行评估，并将它们转换为内部日期/时间结构。</span><span class="sxs-lookup"><span data-stu-id="73ff4-254">You can specify date and time data types by using a variety of different literal string formats, which SQL Server then evaluates at run time, converting them to internal date/time structures.</span></span> <span data-ttu-id="73ff4-255">SQL Server 识别用单引号 (') 括起来的日期和时间数据。</span><span class="sxs-lookup"><span data-stu-id="73ff4-255">SQL Server recognizes date and time data that is enclosed in single quotation marks (').</span></span> <span data-ttu-id="73ff4-256">下面的示例展示了一些格式：</span><span class="sxs-lookup"><span data-stu-id="73ff4-256">The following examples demonstrate some formats:</span></span>  
  
- <span data-ttu-id="73ff4-257">字母日期格式，如 `'October 15, 2006'`。</span><span class="sxs-lookup"><span data-stu-id="73ff4-257">Alphabetic date formats, such as `'October 15, 2006'`.</span></span>  
  
- <span data-ttu-id="73ff4-258">数字日期格式，如 `'10/15/2006'`。</span><span class="sxs-lookup"><span data-stu-id="73ff4-258">Numeric date formats, such as `'10/15/2006'`.</span></span>  
  
- <span data-ttu-id="73ff4-259">如果使用的是 ISO 标准日期格式，未分隔的字符串格式 `'20061015'`（举个例子）就会解析为 2006 年 10 月 15 日。</span><span class="sxs-lookup"><span data-stu-id="73ff4-259">Unseparated string formats, such as `'20061015'`, which would be interpreted as October 15, 2006 if you are using the ISO standard date format.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="73ff4-260">SQL Server 联机丛书中有关于所有文本字符串格式以及日期和时间数据类型的其他功能的完整文档。</span><span class="sxs-lookup"><span data-stu-id="73ff4-260">You can find complete documentation for all of the literal string formats and other features of the date and time data types in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="73ff4-261">小于零或大于等于 24 小时的时间值会导致 <xref:System.ArgumentException> 抛出。</span><span class="sxs-lookup"><span data-stu-id="73ff4-261">Time values that are less than zero or greater than or equal to 24 hours will throw an <xref:System.ArgumentException>.</span></span>  
  
## <a name="resources-in-sql-server-books-online"></a><span data-ttu-id="73ff4-262">SQL Server 联机丛书中的资源</span><span class="sxs-lookup"><span data-stu-id="73ff4-262">Resources in SQL Server Books Online</span></span>  
 <span data-ttu-id="73ff4-263">有关在 SQL Server 中使用日期和时间值的详细信息，请参阅 SQL Server 联机手册中的以下资源。</span><span class="sxs-lookup"><span data-stu-id="73ff4-263">For more information about working with date and time values in SQL Server, see the following resources in SQL Server Books Online.</span></span>  
  
|<span data-ttu-id="73ff4-264">主题</span><span class="sxs-lookup"><span data-stu-id="73ff4-264">Topic</span></span>|<span data-ttu-id="73ff4-265">说明</span><span class="sxs-lookup"><span data-stu-id="73ff4-265">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="73ff4-266">日期和时间数据类型及函数 (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="73ff4-266">Date and Time Data Types and Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql)|<span data-ttu-id="73ff4-267">概述所有 Transact-SQL 日期和时间数据类型和函数。</span><span class="sxs-lookup"><span data-stu-id="73ff4-267">Provides an overview of all Transact-SQL date and time data types and functions.</span></span>|  
|<span data-ttu-id="73ff4-268">[使用日期和时间数据](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="73ff4-268">[Using Date and Time Data](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))</span></span>|<span data-ttu-id="73ff4-269">提供日期和时间数据类型和函数的相关信息以及使用示例。</span><span class="sxs-lookup"><span data-stu-id="73ff4-269">Provides information about the date and time data types and functions, and examples of using them.</span></span>|  
|[<span data-ttu-id="73ff4-270">数据类型（转算-SQL）</span><span class="sxs-lookup"><span data-stu-id="73ff4-270">Data Types (Transact-SQL)</span></span>](/sql/t-sql/data-types/data-types-transact-sql)|<span data-ttu-id="73ff4-271">描述 SQL Server 中的系统数据类型。</span><span class="sxs-lookup"><span data-stu-id="73ff4-271">Describes system data types in SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="73ff4-272">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73ff4-272">See also</span></span>

- [<span data-ttu-id="73ff4-273">SQL Server 数据类型映射</span><span class="sxs-lookup"><span data-stu-id="73ff4-273">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="73ff4-274">配置参数和参数数据类型</span><span class="sxs-lookup"><span data-stu-id="73ff4-274">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="73ff4-275">SQL 服务器数据类型和ADO.NET</span><span class="sxs-lookup"><span data-stu-id="73ff4-275">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)
- [<span data-ttu-id="73ff4-276">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="73ff4-276">ADO.NET Overview</span></span>](../ado-net-overview.md)
