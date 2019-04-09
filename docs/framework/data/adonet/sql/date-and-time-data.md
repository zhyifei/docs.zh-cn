---
title: 日期和时间数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6f5ff56a-a57e-49d7-8ae9-bbed697e42e3
ms.openlocfilehash: a4bbed1f115ef5cfb6b7b63156f2d84b071cf224
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127109"
---
# <a name="date-and-time-data"></a><span data-ttu-id="e46e8-102">日期和时间数据</span><span class="sxs-lookup"><span data-stu-id="e46e8-102">Date and Time Data</span></span>
<span data-ttu-id="e46e8-103">SQL Server 2008 引入了用于处理日期和时间信息的新数据类型。</span><span class="sxs-lookup"><span data-stu-id="e46e8-103">SQL Server 2008 introduces new data types for handling date and time information.</span></span> <span data-ttu-id="e46e8-104">新的数据类型包括单独的日期和时间类型以及具有更大范围、更高精度和更强时区感知能力的扩展数据类型。</span><span class="sxs-lookup"><span data-stu-id="e46e8-104">The new data types include separate types for date and time, and expanded data types with greater range, precision, and time-zone awareness.</span></span> <span data-ttu-id="e46e8-105">从 .NET Framework 3.5 Service Pack (SP) 1 开始，适用于 SQL Server 的 .NET Framework 数据提供程序 (<xref:System.Data.SqlClient>) 完全支持 SQL Server 2008 数据库引擎的所有新功能。</span><span class="sxs-lookup"><span data-stu-id="e46e8-105">Starting with the .NET Framework version 3.5 Service Pack (SP) 1, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides full support for all the new features of the SQL Server 2008 Database Engine.</span></span> <span data-ttu-id="e46e8-106">您必须安装 .NET Framework 3.5 SP1（或更高版本）才能将这些新功能与 SqlClient 一起使用。</span><span class="sxs-lookup"><span data-stu-id="e46e8-106">You must install the .NET Framework 3.5 SP1 (or later) to use these new features with SqlClient.</span></span>  
  
 <span data-ttu-id="e46e8-107">SQL Server 2008 之前的 SQL Server 版本仅具有两种用于处理日期和时间值的数据类型：`datetime` 和 `smalldatetime`。</span><span class="sxs-lookup"><span data-stu-id="e46e8-107">Versions of SQL Server earlier than SQL Server 2008 only had two data types for working with date and time values: `datetime` and `smalldatetime`.</span></span> <span data-ttu-id="e46e8-108">这两种数据类型同时包含日期值和时间值，因而难以仅使用日期值或仅使用时间值。</span><span class="sxs-lookup"><span data-stu-id="e46e8-108">Both of these data types contain both the date value and a time value, which makes it difficult to work with only date or only time values.</span></span> <span data-ttu-id="e46e8-109">此外，这些数据类型仅支持自 1753 年英国引入公历日历以来的日期。</span><span class="sxs-lookup"><span data-stu-id="e46e8-109">Also, these data types only support dates that occur after the introduction of the Gregorian calendar in England in 1753.</span></span> <span data-ttu-id="e46e8-110">另一个限制是这些旧的数据类型无法识别时区，因此难以使用来自多个时区的数据。</span><span class="sxs-lookup"><span data-stu-id="e46e8-110">Another limitation is that these older data types are not time-zone aware, which makes it difficult to work with data that originates from multiple time zones.</span></span>  
  
 <span data-ttu-id="e46e8-111">有关 SQL Server 数据类型的完整文档可从 SQL Server 联机丛书中获得。</span><span class="sxs-lookup"><span data-stu-id="e46e8-111">Complete documentation for SQL Server data types is available in SQL Server Books Online.</span></span> <span data-ttu-id="e46e8-112">下表列出了有关日期和时间数据的因版本而异的入门级主题。</span><span class="sxs-lookup"><span data-stu-id="e46e8-112">The following table lists the version-specific entry-level topics for date and time data.</span></span>  
  
 **<span data-ttu-id="e46e8-113">SQL Server 联机丛书</span><span class="sxs-lookup"><span data-stu-id="e46e8-113">SQL Server Books Online</span></span>**  
  
1.  [<span data-ttu-id="e46e8-114">Using Date and Time Data（使用日期和时间数据）</span><span class="sxs-lookup"><span data-stu-id="e46e8-114">Using Date and Time Data</span></span>](https://go.microsoft.com/fwlink/?LinkID=98361)  
  
## <a name="datetime-data-types-introduced-in-sql-server-2008"></a><span data-ttu-id="e46e8-115">SQL Server 2008 中引入的日期/时间数据类型</span><span class="sxs-lookup"><span data-stu-id="e46e8-115">Date/Time Data Types Introduced in SQL Server 2008</span></span>  
 <span data-ttu-id="e46e8-116">下表描述了新的日期和时间数据类型。</span><span class="sxs-lookup"><span data-stu-id="e46e8-116">The following table describes the new date and time data types.</span></span>  
  
|<span data-ttu-id="e46e8-117">SQL Server 数据类型</span><span class="sxs-lookup"><span data-stu-id="e46e8-117">SQL Server data type</span></span>|<span data-ttu-id="e46e8-118">描述</span><span class="sxs-lookup"><span data-stu-id="e46e8-118">Description</span></span>|  
|--------------------------|-----------------|  
|`date`|<span data-ttu-id="e46e8-119">`date` 数据类型的范围从 01 年 1 月 1 日到 9999 年 12 月 31 日，精度为 1 天。</span><span class="sxs-lookup"><span data-stu-id="e46e8-119">The `date` data type has a range of January 1, 01 through December 31, 9999 with an accuracy of 1 day.</span></span> <span data-ttu-id="e46e8-120">默认值为 1900 年 1月 1日。</span><span class="sxs-lookup"><span data-stu-id="e46e8-120">The default value is January 1, 1900.</span></span> <span data-ttu-id="e46e8-121">存储大小为 3 字节。</span><span class="sxs-lookup"><span data-stu-id="e46e8-121">The storage size is 3 bytes.</span></span>|  
|`time`|<span data-ttu-id="e46e8-122">`time` 数据类型仅存储时间值，并且采用 24 小时制。</span><span class="sxs-lookup"><span data-stu-id="e46e8-122">The `time` data type stores time values only, based on a 24-hour clock.</span></span> <span data-ttu-id="e46e8-123">`time` 数据类型的范围从 00:00:00.0000000 到 23:59:59.9999999，精确到 100 毫微秒。</span><span class="sxs-lookup"><span data-stu-id="e46e8-123">The `time` data type has a range of 00:00:00.0000000 through 23:59:59.9999999 with an accuracy of 100 nanoseconds.</span></span> <span data-ttu-id="e46e8-124">默认值为 00:00:00.0000000（午夜）。</span><span class="sxs-lookup"><span data-stu-id="e46e8-124">The default value is 00:00:00.0000000 (midnight).</span></span> <span data-ttu-id="e46e8-125">`time` 数据类型支持用户定义的小数秒精度，存储大小根据指定的精度在 3 字节到 6 字节之间变化。</span><span class="sxs-lookup"><span data-stu-id="e46e8-125">The `time` data type supports user-defined fractional second precision, and the storage size varies from 3 to 6 bytes, based on the precision specified.</span></span>|  
|`datetime2`|<span data-ttu-id="e46e8-126">`datetime2` 数据类型将 `date` 和 `time` 数据类型的范围和精度组合成单个数据类型。</span><span class="sxs-lookup"><span data-stu-id="e46e8-126">The `datetime2` data type combines the range and precision of the `date` and `time` data types into a single data type.</span></span><br /><br /> <span data-ttu-id="e46e8-127">默认值和字符串格式与 `date` 和 `time` 数据类型中定义的相同。</span><span class="sxs-lookup"><span data-stu-id="e46e8-127">The default values and string literal formats are the same as those defined in the `date` and `time` data types.</span></span>|  
|`datetimeoffset`|<span data-ttu-id="e46e8-128">`datetimeoffset` 数据类型具有 `datetime2` 的所有功能，并附加了时区偏移量。</span><span class="sxs-lookup"><span data-stu-id="e46e8-128">The `datetimeoffset` data type has all the features of `datetime2` with an additional time zone offset.</span></span> <span data-ttu-id="e46e8-129">时区偏移量表示为 [+&#124;-] hh: mm。</span><span class="sxs-lookup"><span data-stu-id="e46e8-129">The time zone offset is represented as [+&#124;-] HH:MM.</span></span> <span data-ttu-id="e46e8-130">HH 是范围从 00 到 14 的 2 位数，表示时区偏移量的小时数。</span><span class="sxs-lookup"><span data-stu-id="e46e8-130">HH is 2 digits ranging from 00 to 14 that represent the number of hours in the time zone offset.</span></span> <span data-ttu-id="e46e8-131">MM 是范围从 00 到 59 的 2 位数，表示时区偏移量的附加分钟数。</span><span class="sxs-lookup"><span data-stu-id="e46e8-131">MM is 2 digits ranging from 00 to 59 that represent the number of additional minutes in the time zone offset.</span></span> <span data-ttu-id="e46e8-132">时间格式支持的精度为 100 毫微秒。</span><span class="sxs-lookup"><span data-stu-id="e46e8-132">Time formats are supported to 100 nanoseconds.</span></span> <span data-ttu-id="e46e8-133">必需的 + 或 - 符号指示在 UTC（通用协调时间或格林尼治标准时间）中是加上还是减去时区偏移量以获取本地时间。</span><span class="sxs-lookup"><span data-stu-id="e46e8-133">The mandatory + or - sign indicates whether the time zone offset is added or subtracted from UTC (Universal Time Coordinate or Greenwich Mean Time) to obtain the local time.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="e46e8-134">有关使用 `Type System Version` 关键字的更多信息，请参见 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>。</span><span class="sxs-lookup"><span data-stu-id="e46e8-134">For more information about using the `Type System Version` keyword, see <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>  
  
## <a name="date-format-and-date-order"></a><span data-ttu-id="e46e8-135">日期格式和日期顺序</span><span class="sxs-lookup"><span data-stu-id="e46e8-135">Date Format and Date Order</span></span>  
 <span data-ttu-id="e46e8-136">SQL Server 分析日期和时间值的方式不仅依赖于类型系统版本和服务器版本，还依赖于服务器的默认语言和格式设置。</span><span class="sxs-lookup"><span data-stu-id="e46e8-136">How SQL Server parses date and time values depends not only on the type system version and server version, but also on the server's default language and format settings.</span></span> <span data-ttu-id="e46e8-137">如果由使用不同语言和日期格式设置的连接执行查询，则可能无法识别仅适用于一种语言的日期格式的日期字符串。</span><span class="sxs-lookup"><span data-stu-id="e46e8-137">A date string that works for the date formats of one language might be unrecognizable if the query is executed by a connection that uses a different language and date format setting.</span></span>  
  
 <span data-ttu-id="e46e8-138">Transact-SQL SET LANGUAGE 语句隐式设置可确定日期各个部分的顺序的 DATEFORMAT。</span><span class="sxs-lookup"><span data-stu-id="e46e8-138">The Transact-SQL SET LANGUAGE statement implicitly sets the DATEFORMAT that determines the order of the date parts.</span></span> <span data-ttu-id="e46e8-139">可以对连接使用 SET DATEFORMAT Transact-SQL 语句，通过按 MDY、DMY、YMD、YDM、MYD 或 DYM 顺序对日期的各个部分进行排序来消除日期值的歧义。</span><span class="sxs-lookup"><span data-stu-id="e46e8-139">You can use the SET DATEFORMAT Transact-SQL statement on a connection to disambiguate date values by ordering the date parts in MDY, DMY, YMD, YDM, MYD, or DYM order.</span></span>  
  
 <span data-ttu-id="e46e8-140">如果没有为连接指定任何 DATEFORMAT，则 SQL Server 将使用与连接关联的默认语言。</span><span class="sxs-lookup"><span data-stu-id="e46e8-140">If you do not specify any DATEFORMAT for the connection, SQL Server uses the default language associated with the connection.</span></span> <span data-ttu-id="e46e8-141">例如，在使用美国英语语言设置的服务器上，日期字符串“01/02/03”将解释为 MDY（2003 年 1 月 2 日），而在使用英国英语语言设置的服务器上，将解释为 DMY（2003 年 2 月 1 日）。</span><span class="sxs-lookup"><span data-stu-id="e46e8-141">For example, a date string of '01/02/03' would be interpreted as MDY (January 2, 2003) on a server with a language setting of United States English, and as DMY (February 1, 2003) on a server with a language setting of British English.</span></span> <span data-ttu-id="e46e8-142">年份是通过使用 SQL Server 的截止年份规则确定的，该规则定义用于分配世纪值的截止日期。</span><span class="sxs-lookup"><span data-stu-id="e46e8-142">The year is determined by using SQL Server's cutoff year rule, which defines the cutoff date for assigning the century value.</span></span> <span data-ttu-id="e46e8-143">有关详细信息，请参阅[two digit year cutoff 选项](https://go.microsoft.com/fwlink/?LinkId=120473)SQL Server 联机丛书中。</span><span class="sxs-lookup"><span data-stu-id="e46e8-143">For more information, see [two digit year cutoff Option](https://go.microsoft.com/fwlink/?LinkId=120473) in SQL Server Books Online.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e46e8-144">从字符串格式转换为 `date`、`time`、`datetime2` 或 `datetimeoffset` 时不支持 YDM 日期格式。</span><span class="sxs-lookup"><span data-stu-id="e46e8-144">The YDM date format is not supported when converting from a string format to `date`, `time`, `datetime2`, or `datetimeoffset`.</span></span>  
  
 <span data-ttu-id="e46e8-145">有关 SQL Server 如何解释日期和时间数据的详细信息，请参阅[使用日期和时间数据](https://go.microsoft.com/fwlink/?LinkID=98361)SQL Server 2008 联机丛书中。</span><span class="sxs-lookup"><span data-stu-id="e46e8-145">For more information about how SQL Server interprets date and time data, see [Using Date and Time Data](https://go.microsoft.com/fwlink/?LinkID=98361) in SQL Server 2008 Books Online.</span></span>  
  
## <a name="datetime-data-types-and-parameters"></a><span data-ttu-id="e46e8-146">日期/时间数据类型和参数</span><span class="sxs-lookup"><span data-stu-id="e46e8-146">Date/Time Data Types and Parameters</span></span>  
 <span data-ttu-id="e46e8-147"><xref:System.Data.SqlDbType> 中已添加了下面的枚举，以支持新的日期和时间数据类型。</span><span class="sxs-lookup"><span data-stu-id="e46e8-147">The following enumerations have been added to <xref:System.Data.SqlDbType> to support the new date and time data types.</span></span>  
  
-   `SqlDbType.Date`  
  
-   `SqlDbType.Time`  
  
-   `SqlDbType.DateTime2`  
  
-   `SqlDbType.DateTimeOffSet`  

<span data-ttu-id="e46e8-148">可以指定的数据类型<xref:System.Data.SqlClient.SqlParameter>使用前面的某个<xref:System.Data.SqlDbType>枚举。</span><span class="sxs-lookup"><span data-stu-id="e46e8-148">You can specify the data type of a <xref:System.Data.SqlClient.SqlParameter> by using one of the preceding <xref:System.Data.SqlDbType> enumerations.</span></span> 

> [!NOTE]
> <span data-ttu-id="e46e8-149">不能设置`DbType`的属性`SqlParameter`到`SqlDbType.Date`。</span><span class="sxs-lookup"><span data-stu-id="e46e8-149">You cannot set the `DbType` property of a `SqlParameter` to `SqlDbType.Date`.</span></span>

 <span data-ttu-id="e46e8-150">也可以通过将 <xref:System.Data.SqlClient.SqlParameter> 对象的 <xref:System.Data.SqlClient.SqlParameter.DbType%2A> 属性设置为特定的 `SqlParameter` 枚举值，按照通常的方式来指定 <xref:System.Data.DbType> 的类型。</span><span class="sxs-lookup"><span data-stu-id="e46e8-150">You can also specify the type of a <xref:System.Data.SqlClient.SqlParameter> generically by setting the <xref:System.Data.SqlClient.SqlParameter.DbType%2A> property of a `SqlParameter` object to a particular <xref:System.Data.DbType> enumeration value.</span></span> <span data-ttu-id="e46e8-151"><xref:System.Data.DbType> 中已添加了下面的枚举值，以支持 `datetime2` 和 `datetimeoffset` 数据类型：</span><span class="sxs-lookup"><span data-stu-id="e46e8-151">The following enumeration values have been added to <xref:System.Data.DbType> to support the `datetime2` and `datetimeoffset` data types:</span></span>  
  
-   <span data-ttu-id="e46e8-152">DbType.DateTime2</span><span class="sxs-lookup"><span data-stu-id="e46e8-152">DbType.DateTime2</span></span>  
  
-   <span data-ttu-id="e46e8-153">DbType.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="e46e8-153">DbType.DateTimeOffset</span></span>  
  
 <span data-ttu-id="e46e8-154">这些新枚举补充了早期版本的 .NET Framework 中存在的 `Date`、`Time` 和 `DateTime` 枚举。</span><span class="sxs-lookup"><span data-stu-id="e46e8-154">These new enumerations supplement the `Date`, `Time`, and `DateTime` enumerations, which existed in earlier versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="e46e8-155">某一参数对象的 .NET Framework 数据提供程序类型是从该参数对象的 .NET Framework 类型或该参数对象的 `DbType` 推断而来的。</span><span class="sxs-lookup"><span data-stu-id="e46e8-155">The .NET Framework data provider type of a parameter object is inferred from the .NET Framework type of the value of the parameter object, or from the `DbType` of the parameter object.</span></span> <span data-ttu-id="e46e8-156">没有引入新的 <xref:System.Data.SqlTypes> 数据类型来支持新的日期和时间数据类型。</span><span class="sxs-lookup"><span data-stu-id="e46e8-156">No new <xref:System.Data.SqlTypes> data types have been introduced to support the new date and time data types.</span></span> <span data-ttu-id="e46e8-157">下表说明 SQL Server 2008 日期和时间数据类型和 CLR 数据类型之间的映射。</span><span class="sxs-lookup"><span data-stu-id="e46e8-157">The following table describes the mappings between the SQL Server 2008 date and time data types and the CLR data types.</span></span>  
  
|<span data-ttu-id="e46e8-158">SQL Server 数据类型</span><span class="sxs-lookup"><span data-stu-id="e46e8-158">SQL Server data type</span></span>|<span data-ttu-id="e46e8-159">.NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="e46e8-159">.NET Framework type</span></span>|<span data-ttu-id="e46e8-160">System.Data.SqlDbType</span><span class="sxs-lookup"><span data-stu-id="e46e8-160">System.Data.SqlDbType</span></span>|<span data-ttu-id="e46e8-161">System.Data.DbType</span><span class="sxs-lookup"><span data-stu-id="e46e8-161">System.Data.DbType</span></span>|  
|--------------------------|-------------------------|---------------------------|------------------------|  
|<span data-ttu-id="e46e8-162">date</span><span class="sxs-lookup"><span data-stu-id="e46e8-162">date</span></span>|<span data-ttu-id="e46e8-163">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="e46e8-163">System.DateTime</span></span>|<span data-ttu-id="e46e8-164">日期</span><span class="sxs-lookup"><span data-stu-id="e46e8-164">Date</span></span>|<span data-ttu-id="e46e8-165">日期</span><span class="sxs-lookup"><span data-stu-id="e46e8-165">Date</span></span>|  
|<span data-ttu-id="e46e8-166">时间</span><span class="sxs-lookup"><span data-stu-id="e46e8-166">time</span></span>|<span data-ttu-id="e46e8-167">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="e46e8-167">System.TimeSpan</span></span>|<span data-ttu-id="e46e8-168">时间</span><span class="sxs-lookup"><span data-stu-id="e46e8-168">Time</span></span>|<span data-ttu-id="e46e8-169">时间</span><span class="sxs-lookup"><span data-stu-id="e46e8-169">Time</span></span>|  
|<span data-ttu-id="e46e8-170">datetime2</span><span class="sxs-lookup"><span data-stu-id="e46e8-170">datetime2</span></span>|<span data-ttu-id="e46e8-171">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="e46e8-171">System.DateTime</span></span>|<span data-ttu-id="e46e8-172">DateTime2</span><span class="sxs-lookup"><span data-stu-id="e46e8-172">DateTime2</span></span>|<span data-ttu-id="e46e8-173">DateTime2</span><span class="sxs-lookup"><span data-stu-id="e46e8-173">DateTime2</span></span>|  
|<span data-ttu-id="e46e8-174">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="e46e8-174">datetimeoffset</span></span>|<span data-ttu-id="e46e8-175">System.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="e46e8-175">System.DateTimeOffset</span></span>|<span data-ttu-id="e46e8-176">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="e46e8-176">DateTimeOffset</span></span>|<span data-ttu-id="e46e8-177">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="e46e8-177">DateTimeOffset</span></span>|  
|<span data-ttu-id="e46e8-178">datetime</span><span class="sxs-lookup"><span data-stu-id="e46e8-178">datetime</span></span>|<span data-ttu-id="e46e8-179">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="e46e8-179">System.DateTime</span></span>|<span data-ttu-id="e46e8-180">DateTime</span><span class="sxs-lookup"><span data-stu-id="e46e8-180">DateTime</span></span>|<span data-ttu-id="e46e8-181">DateTime</span><span class="sxs-lookup"><span data-stu-id="e46e8-181">DateTime</span></span>|  
|<span data-ttu-id="e46e8-182">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="e46e8-182">smalldatetime</span></span>|<span data-ttu-id="e46e8-183">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="e46e8-183">System.DateTime</span></span>|<span data-ttu-id="e46e8-184">DateTime</span><span class="sxs-lookup"><span data-stu-id="e46e8-184">DateTime</span></span>|<span data-ttu-id="e46e8-185">DateTime</span><span class="sxs-lookup"><span data-stu-id="e46e8-185">DateTime</span></span>|  
  
### <a name="sqlparameter-properties"></a><span data-ttu-id="e46e8-186">SqlParameter 属性</span><span class="sxs-lookup"><span data-stu-id="e46e8-186">SqlParameter Properties</span></span>  
 <span data-ttu-id="e46e8-187">下表描述了与日期和时间数据类型相关的 `SqlParameter` 属性。</span><span class="sxs-lookup"><span data-stu-id="e46e8-187">The following table describes `SqlParameter` properties that are relevant to date and time data types.</span></span>  
  
|<span data-ttu-id="e46e8-188">属性</span><span class="sxs-lookup"><span data-stu-id="e46e8-188">Property</span></span>|<span data-ttu-id="e46e8-189">描述</span><span class="sxs-lookup"><span data-stu-id="e46e8-189">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.IsNullable%2A>|<span data-ttu-id="e46e8-190">获取或设置值是否可以为 null。</span><span class="sxs-lookup"><span data-stu-id="e46e8-190">Gets or sets whether a value is nullable.</span></span> <span data-ttu-id="e46e8-191">在向服务器发送 null 参数值时，必须指定 <xref:System.DBNull> 而非 `null`（在 Visual Basic 中为 `Nothing`）。</span><span class="sxs-lookup"><span data-stu-id="e46e8-191">When you send a null parameter value to the server, you must specify <xref:System.DBNull>, rather than `null` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="e46e8-192">有关数据库 null 值的详细信息，请参阅 [Handling Null Values](../../../../../docs/framework/data/adonet/sql/handling-null-values.md)。</span><span class="sxs-lookup"><span data-stu-id="e46e8-192">For more information about database nulls, see [Handling Null Values](../../../../../docs/framework/data/adonet/sql/handling-null-values.md).</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Precision%2A>|<span data-ttu-id="e46e8-193">获取或设置用来表示值的最大位数。</span><span class="sxs-lookup"><span data-stu-id="e46e8-193">Gets or sets the maximum number of digits used to represent the value.</span></span> <span data-ttu-id="e46e8-194">对于日期和时间数据类型，忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="e46e8-194">This setting is ignored for date and time data types.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Scale%2A>|<span data-ttu-id="e46e8-195">获取或设置的值的时间部分是解析为的小数位数`Time`， `DateTime2`，和`DateTimeOffset`。</span><span class="sxs-lookup"><span data-stu-id="e46e8-195">Gets or sets the number of decimal places to which the time portion of the value is resolved for `Time`, `DateTime2`,and `DateTimeOffset`.</span></span> <span data-ttu-id="e46e8-196">默认值为 0。这意味着实际小数位数从值推断出来并发送给服务器。</span><span class="sxs-lookup"><span data-stu-id="e46e8-196">The default value is 0, which means that the actual scale is inferred from the value and sent to the server.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|<span data-ttu-id="e46e8-197">对于日期和时间数据类型，忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="e46e8-197">Ignored for date and time data types.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|<span data-ttu-id="e46e8-198">获取或设置参数值。</span><span class="sxs-lookup"><span data-stu-id="e46e8-198">Gets or sets the parameter value.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|<span data-ttu-id="e46e8-199">获取或设置参数值。</span><span class="sxs-lookup"><span data-stu-id="e46e8-199">Gets or sets the parameter value.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="e46e8-200">小于 0 或大于等于 24 小时的时间值将引发 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="e46e8-200">Time values that are less than zero or greater than or equal to 24 hours will throw an <xref:System.ArgumentException>.</span></span>  
  
### <a name="creating-parameters"></a><span data-ttu-id="e46e8-201">创建参数</span><span class="sxs-lookup"><span data-stu-id="e46e8-201">Creating Parameters</span></span>  
 <span data-ttu-id="e46e8-202">您可以创建<xref:System.Data.SqlClient.SqlParameter>对象使用其构造函数，或将其添加到<xref:System.Data.SqlClient.SqlCommand><xref:System.Data.SqlClient.SqlCommand.Parameters%2A>集合通过调用`Add`方法的<xref:System.Data.SqlClient.SqlParameterCollection>。</span><span class="sxs-lookup"><span data-stu-id="e46e8-202">You can create a <xref:System.Data.SqlClient.SqlParameter> object by using its constructor, or by adding it to a <xref:System.Data.SqlClient.SqlCommand><xref:System.Data.SqlClient.SqlCommand.Parameters%2A> collection by calling the `Add` method of the <xref:System.Data.SqlClient.SqlParameterCollection>.</span></span> <span data-ttu-id="e46e8-203">`Add` 方法将采用构造函数自变量或现有的参数对象用作输入。</span><span class="sxs-lookup"><span data-stu-id="e46e8-203">The `Add` method will take as input either constructor arguments or an existing parameter object.</span></span>  
  
 <span data-ttu-id="e46e8-204">本主题中的以下各部分提供了如何指定日期和时间参数的示例。</span><span class="sxs-lookup"><span data-stu-id="e46e8-204">The next sections in this topic provide examples of how to specify date and time parameters.</span></span> <span data-ttu-id="e46e8-205">使用参数的其他示例，请参阅[配置参数和参数数据类型](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)并[DataAdapter 参数](../../../../../docs/framework/data/adonet/dataadapter-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="e46e8-205">For additional examples of working with parameters, see [Configuring Parameters and Parameter Data Types](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md) and [DataAdapter Parameters](../../../../../docs/framework/data/adonet/dataadapter-parameters.md).</span></span>  
  
### <a name="date-example"></a><span data-ttu-id="e46e8-206">date 示例</span><span class="sxs-lookup"><span data-stu-id="e46e8-206">Date Example</span></span>  
 <span data-ttu-id="e46e8-207">下面的代码段演示如何指定 `date` 参数。</span><span class="sxs-lookup"><span data-stu-id="e46e8-207">The following code fragment demonstrates how to specify a `date` parameter.</span></span>  
  
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
  
### <a name="time-example"></a><span data-ttu-id="e46e8-208">time 示例</span><span class="sxs-lookup"><span data-stu-id="e46e8-208">Time Example</span></span>  
 <span data-ttu-id="e46e8-209">下面的代码段演示如何指定 `time` 参数。</span><span class="sxs-lookup"><span data-stu-id="e46e8-209">The following code fragment demonstrates how to specify a `time` parameter.</span></span>  
  
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
  
### <a name="datetime2-example"></a><span data-ttu-id="e46e8-210">datetime2 示例</span><span class="sxs-lookup"><span data-stu-id="e46e8-210">Datetime2 Example</span></span>  
 <span data-ttu-id="e46e8-211">下面的代码段演示如何指定同时具有日期和时间部分的 `datetime2` 参数。</span><span class="sxs-lookup"><span data-stu-id="e46e8-211">The following code fragment demonstrates how to specify a `datetime2` parameter with both the date and time parts.</span></span>  
  
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
  
### <a name="datetimeoffset-example"></a><span data-ttu-id="e46e8-212">DateTimeOffSet 示例</span><span class="sxs-lookup"><span data-stu-id="e46e8-212">DateTimeOffSet Example</span></span>  
 <span data-ttu-id="e46e8-213">下面的代码段演示如何指定具有日期、时间和偏移量为 0 的时区的 `DateTimeOffSet` 参数。</span><span class="sxs-lookup"><span data-stu-id="e46e8-213">The following code fragment demonstrates how to specify a `DateTimeOffSet` parameter with a date, a time, and a time zone offset of 0.</span></span>  
  
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
  
### <a name="addwithvalue"></a><span data-ttu-id="e46e8-214">AddWithValue</span><span class="sxs-lookup"><span data-stu-id="e46e8-214">AddWithValue</span></span>  
 <span data-ttu-id="e46e8-215">也可以通过使用 `AddWithValue` 的 <xref:System.Data.SqlClient.SqlCommand> 方法来提供参数，如下面的代码段所示。</span><span class="sxs-lookup"><span data-stu-id="e46e8-215">You can also supply parameters by using the `AddWithValue` method of a <xref:System.Data.SqlClient.SqlCommand>, as shown in the following code fragment.</span></span> <span data-ttu-id="e46e8-216">不过，不能使用 `AddWithValue` 方法为参数指定 <xref:System.Data.SqlClient.SqlParameter.DbType%2A> 或 <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A>。</span><span class="sxs-lookup"><span data-stu-id="e46e8-216">However, the `AddWithValue` method does not allow you to specify the <xref:System.Data.SqlClient.SqlParameter.DbType%2A> or <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> for the parameter.</span></span>  
  
```csharp  
command.Parameters.AddWithValue(   
    "@date", DateTimeOffset.Parse("16660902"));  
```  
  
```vb  
command.Parameters.AddWithValue( _  
    "@date", DateTimeOffset.Parse("16660902"))  
```  
  
 <span data-ttu-id="e46e8-217">`@date`参数可映射到`date`， `datetime`，或`datetime2`服务器上的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e46e8-217">The `@date` parameter could map to a `date`, `datetime`, or `datetime2` data type on the server.</span></span> <span data-ttu-id="e46e8-218">使用新的 `datetime` 数据类型时，必须将参数的 <xref:System.Data.SqlDbType> 属性显式设置为实例的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e46e8-218">When working with the new `datetime` data types, you must explicitly set the parameter's <xref:System.Data.SqlDbType> property to the data type of the instance.</span></span> <span data-ttu-id="e46e8-219">如果使用 <xref:System.Data.SqlDbType.Variant> 或隐式提供参数值，则会导致与 `datetime` 和 `smalldatetime` 数据类型的向后兼容问题。</span><span class="sxs-lookup"><span data-stu-id="e46e8-219">Using <xref:System.Data.SqlDbType.Variant> or implicitly supplying parameter values can cause problems with backward compatibility with the `datetime` and `smalldatetime` data types.</span></span>  
  
 <span data-ttu-id="e46e8-220">下表显示可从哪些 CLR 类型中推断出哪些 `SqlDbTypes`：</span><span class="sxs-lookup"><span data-stu-id="e46e8-220">The following table shows which `SqlDbTypes` are inferred from which CLR types:</span></span>  
  
|<span data-ttu-id="e46e8-221">CLR 类型</span><span class="sxs-lookup"><span data-stu-id="e46e8-221">CLR type</span></span>|<span data-ttu-id="e46e8-222">推断出的 SqlDbType</span><span class="sxs-lookup"><span data-stu-id="e46e8-222">Inferred SqlDbType</span></span>|  
|--------------|------------------------|  
|<span data-ttu-id="e46e8-223">DateTime</span><span class="sxs-lookup"><span data-stu-id="e46e8-223">DateTime</span></span>|<span data-ttu-id="e46e8-224">SqlDbType.DateTime</span><span class="sxs-lookup"><span data-stu-id="e46e8-224">SqlDbType.DateTime</span></span>|  
|<span data-ttu-id="e46e8-225">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="e46e8-225">TimeSpan</span></span>|<span data-ttu-id="e46e8-226">SqlDbType.Time</span><span class="sxs-lookup"><span data-stu-id="e46e8-226">SqlDbType.Time</span></span>|  
|<span data-ttu-id="e46e8-227">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="e46e8-227">DateTimeOffset</span></span>|<span data-ttu-id="e46e8-228">SqlDbType.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="e46e8-228">SqlDbType.DateTimeOffset</span></span>|  
  
## <a name="retrieving-date-and-time-data"></a><span data-ttu-id="e46e8-229">检索日期和时间数据</span><span class="sxs-lookup"><span data-stu-id="e46e8-229">Retrieving Date and Time Data</span></span>  
 <span data-ttu-id="e46e8-230">下表说明可用于检索 SQL Server 2008 日期和时间值的方法。</span><span class="sxs-lookup"><span data-stu-id="e46e8-230">The following table describes methods that are used to retrieve SQL Server 2008 date and time values.</span></span>  
  
|<span data-ttu-id="e46e8-231">SqlClient 方法</span><span class="sxs-lookup"><span data-stu-id="e46e8-231">SqlClient method</span></span>|<span data-ttu-id="e46e8-232">描述</span><span class="sxs-lookup"><span data-stu-id="e46e8-232">Description</span></span>|  
|----------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|<span data-ttu-id="e46e8-233">以 <xref:System.DateTime> 结构形式检索指定的列值。</span><span class="sxs-lookup"><span data-stu-id="e46e8-233">Retrieves the specified column value as a <xref:System.DateTime> structure.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTimeOffset%2A>|<span data-ttu-id="e46e8-234">以 <xref:System.DateTimeOffset> 结构形式检索指定的列值。</span><span class="sxs-lookup"><span data-stu-id="e46e8-234">Retrieves the specified column value as a <xref:System.DateTimeOffset> structure.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>|<span data-ttu-id="e46e8-235">返回作为该字段基础提供程序特定类型的类型。</span><span class="sxs-lookup"><span data-stu-id="e46e8-235">Returns the type that is the underlying provider-specific type for the field.</span></span> <span data-ttu-id="e46e8-236">返回新日期和时间类型的与 `GetFieldType` 相同的类型。</span><span class="sxs-lookup"><span data-stu-id="e46e8-236">Returns the same types as `GetFieldType` for new date and time types.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>|<span data-ttu-id="e46e8-237">检索指定列的值。</span><span class="sxs-lookup"><span data-stu-id="e46e8-237">Retrieves the value of the specified column.</span></span> <span data-ttu-id="e46e8-238">返回新日期和时间类型的与 `GetValue` 相同的类型。</span><span class="sxs-lookup"><span data-stu-id="e46e8-238">Returns the same types as `GetValue` for the new date and time types.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>|<span data-ttu-id="e46e8-239">检索指定数组中的值。</span><span class="sxs-lookup"><span data-stu-id="e46e8-239">Retrieves the values in the specified array.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|<span data-ttu-id="e46e8-240">以 <xref:System.Data.SqlTypes.SqlString> 形式检索列值。</span><span class="sxs-lookup"><span data-stu-id="e46e8-240">Retrieves the column value as a <xref:System.Data.SqlTypes.SqlString>.</span></span> <span data-ttu-id="e46e8-241">如果数据无法表示为 <xref:System.InvalidCastException>，则发生 `SqlString`。</span><span class="sxs-lookup"><span data-stu-id="e46e8-241">An <xref:System.InvalidCastException> occurs if the data cannot be expressed as a `SqlString`.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>|<span data-ttu-id="e46e8-242">检索列数据作为其默认 `SqlDbType`。</span><span class="sxs-lookup"><span data-stu-id="e46e8-242">Retrieves column data as its default `SqlDbType`.</span></span> <span data-ttu-id="e46e8-243">返回新日期和时间类型的与 `GetValue` 相同的类型。</span><span class="sxs-lookup"><span data-stu-id="e46e8-243">Returns the same types as `GetValue` for the new date and time types.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>|<span data-ttu-id="e46e8-244">检索指定数组中的值。</span><span class="sxs-lookup"><span data-stu-id="e46e8-244">Retrieves the values in the specified array.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A>|<span data-ttu-id="e46e8-245">如果 Type System Version 设置为 SQL Server 2005，则以字符串形式检索列值。</span><span class="sxs-lookup"><span data-stu-id="e46e8-245">Retrieves the column value as a string if the Type System Version is set to SQL Server 2005.</span></span> <span data-ttu-id="e46e8-246">如果数据无法表示为字符串，则发生 <xref:System.InvalidCastException>。</span><span class="sxs-lookup"><span data-stu-id="e46e8-246">An <xref:System.InvalidCastException> occurs if the data cannot be expressed as a string.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetTimeSpan%2A>|<span data-ttu-id="e46e8-247">以 <xref:System.TimeSpan> 结构形式检索指定的列值。</span><span class="sxs-lookup"><span data-stu-id="e46e8-247">Retrieves the specified column value as a <xref:System.TimeSpan> structure.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>|<span data-ttu-id="e46e8-248">检索指定的列值作为其基础 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="e46e8-248">Retrieves the specified column value as its underlying CLR type.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>|<span data-ttu-id="e46e8-249">检索数组中的列值。</span><span class="sxs-lookup"><span data-stu-id="e46e8-249">Retrieves column values in an array.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>|<span data-ttu-id="e46e8-250">返回一个 <xref:System.Data.DataTable>，说明结果集的元数据。</span><span class="sxs-lookup"><span data-stu-id="e46e8-250">Returns a <xref:System.Data.DataTable> that describes the metadata of the result set.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="e46e8-251">对于 SQL Server 中在进程内执行的代码，不支持新的日期和时间 `SqlDbTypes`。</span><span class="sxs-lookup"><span data-stu-id="e46e8-251">The new date and time `SqlDbTypes` are not supported for code that is executing in-process in SQL Server.</span></span> <span data-ttu-id="e46e8-252">如果将这些类型之一传递给服务器，则将引发异常。</span><span class="sxs-lookup"><span data-stu-id="e46e8-252">An exception will be raised if one of these types is passed to the server.</span></span>  
  
## <a name="specifying-date-and-time-values-as-literals"></a><span data-ttu-id="e46e8-253">作为文字指定日期和时间值</span><span class="sxs-lookup"><span data-stu-id="e46e8-253">Specifying Date and Time Values as Literals</span></span>  
 <span data-ttu-id="e46e8-254">可以通过使用各种不同的文字字符串格式指定日期和时间数据类型，然后 SQL Server 在运行时执行相关计算以将这些文字字符串转换为内部的日期/时间结构。</span><span class="sxs-lookup"><span data-stu-id="e46e8-254">You can specify date and time data types by using a variety of different literal string formats, which SQL Server then evaluates at run time, converting them to internal date/time structures.</span></span> <span data-ttu-id="e46e8-255">SQL Server 可识别用单引号 (') 括起来的日期和时间数据。</span><span class="sxs-lookup"><span data-stu-id="e46e8-255">SQL Server recognizes date and time data that is enclosed in single quotation marks (').</span></span> <span data-ttu-id="e46e8-256">下面的示例演示了一些格式：</span><span class="sxs-lookup"><span data-stu-id="e46e8-256">The following examples demonstrate some formats:</span></span>  
  
-   <span data-ttu-id="e46e8-257">字母日期格式，例如 `'October 15, 2006'`。</span><span class="sxs-lookup"><span data-stu-id="e46e8-257">Alphabetic date formats, such as `'October 15, 2006'`.</span></span>  
  
-   <span data-ttu-id="e46e8-258">数值日期格式，例如 `'10/15/2006'`。</span><span class="sxs-lookup"><span data-stu-id="e46e8-258">Numeric date formats, such as `'10/15/2006'`.</span></span>  
  
-   <span data-ttu-id="e46e8-259">未分隔的字符串格式，例如 `'20061015'`。如果您使用的是 ISO 标准日期格式，则该字符串将解释为 2006 年 10 月 15 日。</span><span class="sxs-lookup"><span data-stu-id="e46e8-259">Unseparated string formats, such as `'20061015'`, which would be interpreted as October 15, 2006 if you are using the ISO standard date format.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e46e8-260">在 SQL Server 联机丛书中，您可以找到有关日期和时间数据类型的所有文字字符串格式以及其他功能的完整文档。</span><span class="sxs-lookup"><span data-stu-id="e46e8-260">You can find complete documentation for all of the literal string formats and other features of the date and time data types in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="e46e8-261">小于 0 或大于等于 24 小时的时间值将引发 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="e46e8-261">Time values that are less than zero or greater than or equal to 24 hours will throw an <xref:System.ArgumentException>.</span></span>  
  
## <a name="resources-in-sql-server-2008-books-online"></a><span data-ttu-id="e46e8-262">SQL Server 2008 联机丛书中的资源</span><span class="sxs-lookup"><span data-stu-id="e46e8-262">Resources in SQL Server 2008 Books Online</span></span>  
 <span data-ttu-id="e46e8-263">有关如何在 SQL Server 2008 中使用日期和时间值的更多信息，请参见 SQL Server 2008 联机丛书中的以下资源。</span><span class="sxs-lookup"><span data-stu-id="e46e8-263">For more information about working with date and time values in SQL Server 2008, see the following resources in SQL Server 2008 Books Online.</span></span>  
  
|<span data-ttu-id="e46e8-264">主题</span><span class="sxs-lookup"><span data-stu-id="e46e8-264">Topic</span></span>|<span data-ttu-id="e46e8-265">描述</span><span class="sxs-lookup"><span data-stu-id="e46e8-265">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="e46e8-266">Date and Time Data Types and Functions (Transact-SQL)（日期和时间数据类型和函数 (Transact-SQL)）</span><span class="sxs-lookup"><span data-stu-id="e46e8-266">Date and Time Data Types and Functions (Transact-SQL)</span></span>](https://go.microsoft.com/fwlink/?LinkId=98360)|<span data-ttu-id="e46e8-267">概述所有 Transact-SQL 日期和时间数据类型和函数。</span><span class="sxs-lookup"><span data-stu-id="e46e8-267">Provides an overview of all Transact-SQL date and time data types and functions.</span></span>|  
|[<span data-ttu-id="e46e8-268">Using Date and Time Data（使用日期和时间数据）</span><span class="sxs-lookup"><span data-stu-id="e46e8-268">Using Date and Time Data</span></span>](https://go.microsoft.com/fwlink/?LinkId=98361)|<span data-ttu-id="e46e8-269">提供有关日期和时间数据类型和函数的信息及相应的用法示例。</span><span class="sxs-lookup"><span data-stu-id="e46e8-269">Provides information about the date and time data types and functions, and examples of using them.</span></span>|  
|[<span data-ttu-id="e46e8-270">Data Types (Transact-SQL)（数据类型 (Transact-SQL)）</span><span class="sxs-lookup"><span data-stu-id="e46e8-270">Data Types (Transact-SQL)</span></span>](https://go.microsoft.com/fwlink/?LinkId=98362)|<span data-ttu-id="e46e8-271">介绍 SQL Server 2008 中的系统数据类型。</span><span class="sxs-lookup"><span data-stu-id="e46e8-271">Describes system data types in SQL Server 2008.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e46e8-272">请参阅</span><span class="sxs-lookup"><span data-stu-id="e46e8-272">See also</span></span>

- [<span data-ttu-id="e46e8-273">SQL Server 数据类型映射</span><span class="sxs-lookup"><span data-stu-id="e46e8-273">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)
- [<span data-ttu-id="e46e8-274">配置参数和参数数据类型</span><span class="sxs-lookup"><span data-stu-id="e46e8-274">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="e46e8-275">SQL Server 数据类型和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e46e8-275">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)
- [<span data-ttu-id="e46e8-276">ADO.NET 托管提供程序和 DataSet 开发人员中心</span><span class="sxs-lookup"><span data-stu-id="e46e8-276">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
