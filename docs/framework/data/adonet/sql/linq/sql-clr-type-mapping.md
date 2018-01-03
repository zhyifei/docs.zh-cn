---
title: "SQL-CLR 类型映射"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ed76327-54a7-414b-82a9-7579bfcec04b
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 84c7f870edd1c8082936b380547e181d129f529e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="sql-clr-type-mapping"></a><span data-ttu-id="485cc-102">SQL-CLR 类型映射</span><span class="sxs-lookup"><span data-stu-id="485cc-102">SQL-CLR Type Mapping</span></span>
<span data-ttu-id="485cc-103">在 LINQ to SQL 中，关系数据库的数据模型映射到用您所选择的编程语言表示的对象模型。</span><span class="sxs-lookup"><span data-stu-id="485cc-103">In LINQ to SQL, the data model of a relational database maps to an object model that is expressed in the programming language of your choice.</span></span> <span data-ttu-id="485cc-104">当应用程序运行时，LINQ to SQL 会将对象模型中的语言集成查询转换为 SQL，然后将它们发送到数据库进行执行。</span><span class="sxs-lookup"><span data-stu-id="485cc-104">When the application runs, LINQ to SQL translates the language-integrated queries in the object model into SQL and sends them to the database for execution.</span></span> <span data-ttu-id="485cc-105">当数据库返回结果时，LINQ to SQL 会将它们转换回您可以用您自己的编程语言处理的对象。</span><span class="sxs-lookup"><span data-stu-id="485cc-105">When the database returns the results, LINQ to SQL translates the results back to objects that you can work with in your own programming language.</span></span>  
  
 <span data-ttu-id="485cc-106">要转换的对象模型和数据库之间的数据*类型映射*必须定义。</span><span class="sxs-lookup"><span data-stu-id="485cc-106">In order to translate data between the object model and the database, a *type mapping* must be defined.</span></span> <span data-ttu-id="485cc-107">LINQ to SQL 使用类型映射将每个公共语言运行时 (CLR) 类型与一种特定 SQL Server 类型相匹配。</span><span class="sxs-lookup"><span data-stu-id="485cc-107">LINQ to SQL uses a type mapping to match each common language runtime (CLR) type with a particular SQL Server type.</span></span> <span data-ttu-id="485cc-108">您可以使用基于属性的映射在对象模型内部定义类型映射和其他映射信息，例如数据库结构和表关系。</span><span class="sxs-lookup"><span data-stu-id="485cc-108">You can define type mappings and other mapping information, such as database structure and table relationships, inside the object model with attribute-based mapping.</span></span> <span data-ttu-id="485cc-109">或者，您可以使用外部映射文件在对象模型外部指定映射信息。</span><span class="sxs-lookup"><span data-stu-id="485cc-109">Alternatively, you can specify the mapping information outside the object model with an external mapping file.</span></span> <span data-ttu-id="485cc-110">有关详细信息，请参阅[基于属性的映射](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)和[外部映射](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="485cc-110">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md) and [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
 <span data-ttu-id="485cc-111">本主题讨论下列内容：</span><span class="sxs-lookup"><span data-stu-id="485cc-111">This topic discusses the following points:</span></span>  
  
-   [<span data-ttu-id="485cc-112">默认类型映射</span><span class="sxs-lookup"><span data-stu-id="485cc-112">Default Type Mapping</span></span>](#DefaultTypeMapping)  
  
-   [<span data-ttu-id="485cc-113">类型映射运行时行为矩阵</span><span class="sxs-lookup"><span data-stu-id="485cc-113">Type Mapping Run-time Behavior Matrix</span></span>](#BehaviorMatrix)  
  
-   [<span data-ttu-id="485cc-114">CLR 和 SQL 执行之间的行为差异</span><span class="sxs-lookup"><span data-stu-id="485cc-114">Behavior Differences Between CLR and SQL Execution</span></span>](#BehaviorDiffs)  
  
-   [<span data-ttu-id="485cc-115">枚举映射</span><span class="sxs-lookup"><span data-stu-id="485cc-115">Enum Mapping</span></span>](#EnumMapping)  
  
-   [<span data-ttu-id="485cc-116">数值映射</span><span class="sxs-lookup"><span data-stu-id="485cc-116">Numeric Mapping</span></span>](#NumericMapping)  
  
-   [<span data-ttu-id="485cc-117">文本和 XML 映射</span><span class="sxs-lookup"><span data-stu-id="485cc-117">Text and XML Mapping</span></span>](#TextMapping)  
  
-   [<span data-ttu-id="485cc-118">日期和时间映射</span><span class="sxs-lookup"><span data-stu-id="485cc-118">Date and Time Mapping</span></span>](#DateMapping)  
  
-   [<span data-ttu-id="485cc-119">二进制映射</span><span class="sxs-lookup"><span data-stu-id="485cc-119">Binary Mapping</span></span>](#BinaryMapping)  
  
-   [<span data-ttu-id="485cc-120">杂项映射</span><span class="sxs-lookup"><span data-stu-id="485cc-120">Miscellaneous Mapping</span></span>](#MiscMapping)  
  
<a name="DefaultTypeMapping"></a>   
## <a name="default-type-mapping"></a><span data-ttu-id="485cc-121">默认类型映射</span><span class="sxs-lookup"><span data-stu-id="485cc-121">Default Type Mapping</span></span>  
 <span data-ttu-id="485cc-122">您可以使用对象关系设计器（O/R 设计器）或 SQLMetal 命令行工具自动创建对象模型或外部映射文件。</span><span class="sxs-lookup"><span data-stu-id="485cc-122">You can create the object model or external mapping file automatically with the Object Relational Designer (O/R Designer) or the SQLMetal command-line tool.</span></span> <span data-ttu-id="485cc-123">这些工具的默认类型映射定义选择何种 CLR 类型来映射到 SQL Server 数据库内部的列。</span><span class="sxs-lookup"><span data-stu-id="485cc-123">The default type mappings for these tools define which CLR types are chosen to map to columns inside the SQL Server database.</span></span> <span data-ttu-id="485cc-124">有关使用这些工具的详细信息，请参阅[创建对象模型](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)。</span><span class="sxs-lookup"><span data-stu-id="485cc-124">For more information about using these tools, see [Creating the Object Model](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md).</span></span>  
  
 <span data-ttu-id="485cc-125">您也可以使用 <xref:System.Data.Linq.DataContext.CreateDatabase%2A> 方法来创建基于对象模型或外部映射文件中的映射信息的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="485cc-125">You can also use the <xref:System.Data.Linq.DataContext.CreateDatabase%2A> method to create a SQL Server database based on the mapping information in the object model or external mapping file.</span></span> <span data-ttu-id="485cc-126"><xref:System.Data.Linq.DataContext.CreateDatabase%2A> 方法的默认类型映射定义创建何种 SQL Server 列来映射到对象模型中的 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="485cc-126">The default type mappings for the <xref:System.Data.Linq.DataContext.CreateDatabase%2A> method define which type of SQL Server columns are created to map to the CLR types in the object model.</span></span> <span data-ttu-id="485cc-127">有关详细信息，请参阅[如何： 动态创建数据库](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md)。</span><span class="sxs-lookup"><span data-stu-id="485cc-127">For more information, see [How to: Dynamically Create a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md).</span></span>  
  
<a name="BehaviorMatrix"></a>   
## <a name="type-mapping-run-time-behavior-matrix"></a><span data-ttu-id="485cc-128">类型映射运行时行为矩阵</span><span class="sxs-lookup"><span data-stu-id="485cc-128">Type Mapping Run-time Behavior Matrix</span></span>  
 <span data-ttu-id="485cc-129">下图显示了数据从数据库检索或保存到数据库时特定类型映射的预期运行时行为。</span><span class="sxs-lookup"><span data-stu-id="485cc-129">The following diagram shows the expected run-time behavior of specific type mappings when data is retrieved from or saved to the database.</span></span> <span data-ttu-id="485cc-130">除序列化之外，LINQ to SQL 不支持任何该矩阵中未指定的 CLR 或 SQL Server 数据类型之间的映射。</span><span class="sxs-lookup"><span data-stu-id="485cc-130">With the exception of serialization, LINQ to SQL does not support mapping between any CLR or SQL Server data types that are not specified in this matrix.</span></span> <span data-ttu-id="485cc-131">有关序列化支持的详细信息，请参阅[二进制序列化](#BinarySerialization)。</span><span class="sxs-lookup"><span data-stu-id="485cc-131">For more information on serialization support, see [Binary Serialization](#BinarySerialization).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="485cc-132">在进行数据库转换时，某些类型映射可能会导致溢出或数据丢失异常。</span><span class="sxs-lookup"><span data-stu-id="485cc-132">Some type mappings may result in overflow or data loss exceptions while translating to or from the database.</span></span>  
  
### <a name="custom-type-mapping"></a><span data-ttu-id="485cc-133">自定义类型映射</span><span class="sxs-lookup"><span data-stu-id="485cc-133">Custom Type Mapping</span></span>  
 <span data-ttu-id="485cc-134">通过使用 LINQ to SQL，您并非仅可以使用 O/R 设计器、SQLMetal 和 <xref:System.Data.Linq.DataContext.CreateDatabase%2A> 方法所使用的默认类型映射。</span><span class="sxs-lookup"><span data-stu-id="485cc-134">With LINQ to SQL, you are not limited to the default type mappings used by the O/R Designer, SQLMetal, and the <xref:System.Data.Linq.DataContext.CreateDatabase%2A> method.</span></span> <span data-ttu-id="485cc-135">您可以通过在 DBML 文件中显式指定自定义类型映射来创建它们。</span><span class="sxs-lookup"><span data-stu-id="485cc-135">You can create custom type mappings by explicitly specifying them in a DBML file.</span></span> <span data-ttu-id="485cc-136">然后，可以使用该 DBML 文件创建对象模型代码和映射文件。</span><span class="sxs-lookup"><span data-stu-id="485cc-136">Then you can use that DBML file to create the object model code and mapping file.</span></span> <span data-ttu-id="485cc-137">有关详细信息，请参阅[SQL-CLR 自定义类型映射](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-custom-type-mappings.md)。</span><span class="sxs-lookup"><span data-stu-id="485cc-137">For more information, see [SQL-CLR Custom Type Mappings](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-custom-type-mappings.md).</span></span>  
  
<a name="BehaviorDiffs"></a>   
## <a name="behavior-differences-between-clr-and-sql-execution"></a><span data-ttu-id="485cc-138">CLR 和 SQL 执行之间的行为差异</span><span class="sxs-lookup"><span data-stu-id="485cc-138">Behavior Differences Between CLR and SQL Execution</span></span>  
 <span data-ttu-id="485cc-139">由于 CLR 和 SQL Server 之间的精度及执行差异，可能会收到不同的结果或体验不同的行为，这取决于执行计算的位置。</span><span class="sxs-lookup"><span data-stu-id="485cc-139">Because of differences in precision and execution between the CLR and SQL Server, you may receive different results or experience different behavior depending on where you perform your calculations.</span></span> <span data-ttu-id="485cc-140">在 LINQ to SQL 查询中执行的计算实际上转换为 Transact-SQL，然后在 SQL Server 数据库上执行。</span><span class="sxs-lookup"><span data-stu-id="485cc-140">Calculations performed in LINQ to SQL queries are actually translated to Transact-SQL and then executed on the SQL Server database.</span></span> <span data-ttu-id="485cc-141">在 LINQ to SQL 查询外执行的计算则在 CLR 的上下文中执行。</span><span class="sxs-lookup"><span data-stu-id="485cc-141">Calculations performed outside LINQ to SQL queries are executed within the context of the CLR.</span></span>  
  
 <span data-ttu-id="485cc-142">例如，以下是一些 CLR 和 SQL Server 之间的行为差异：</span><span class="sxs-lookup"><span data-stu-id="485cc-142">For example, the following are some differences in behavior between the CLR and SQL Server:</span></span>  
  
-   <span data-ttu-id="485cc-143">SQL Server 对一些数据类型的排序不同于 CLR 中等效类型数据的排序。</span><span class="sxs-lookup"><span data-stu-id="485cc-143">SQL Server orders some data types differently than data of equivalent type in the CLR.</span></span> <span data-ttu-id="485cc-144">例如，SQL Server 类型 `UNIQUEIDENTIFIER` 的数据排序不同于 CLR 类型 <xref:System.Guid?displayProperty=nameWithType> 的数据排序。</span><span class="sxs-lookup"><span data-stu-id="485cc-144">For example, SQL Server data of type `UNIQUEIDENTIFIER` is ordered differently than CLR data of type <xref:System.Guid?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="485cc-145">SQL Server 处理一些字符串比较操作的方式不同于 CLR。</span><span class="sxs-lookup"><span data-stu-id="485cc-145">SQL Server handles some string comparison operations differently than the CLR.</span></span> <span data-ttu-id="485cc-146">在 SQL Server 中，字符串比较行为取决于服务器上的排序规则设置。</span><span class="sxs-lookup"><span data-stu-id="485cc-146">In SQL Server, string comparison behavior depends on the collation settings on the server.</span></span> <span data-ttu-id="485cc-147">有关详细信息，请参阅[使用排序规则](http://go.microsoft.com/fwlink/?LinkId=115330)Microsoft SQL Server 联机丛书中。</span><span class="sxs-lookup"><span data-stu-id="485cc-147">For more information, see [Working with Collations](http://go.microsoft.com/fwlink/?LinkId=115330) in the Microsoft SQL Server Books Online.</span></span>  
  
-   <span data-ttu-id="485cc-148">对于一些映射函数，SQL Server 返回的函数值可能与 CLR 不同。</span><span class="sxs-lookup"><span data-stu-id="485cc-148">SQL Server may return different values for some mapped functions than the CLR.</span></span> <span data-ttu-id="485cc-149">例如，相等函数会不同，因为在两个字符串仅在尾随空白不同的情况下，SQL Server 会视这两个字符串相等，而 CLR 则视其不相等。</span><span class="sxs-lookup"><span data-stu-id="485cc-149">For example, equality functions will differ because SQL Server considers two strings to be equal if they only differ in trailing white space; whereas the CLR considers them to be not equal.</span></span>  
  
<a name="EnumMapping"></a>   
## <a name="enum-mapping"></a><span data-ttu-id="485cc-150">枚举映射</span><span class="sxs-lookup"><span data-stu-id="485cc-150">Enum Mapping</span></span>  
 <span data-ttu-id="485cc-151">LINQ to SQL 支持使用如下两种方式将 CLR <xref:System.Enum?displayProperty=nameWithType> 类型映射到 SQL Server 类型：</span><span class="sxs-lookup"><span data-stu-id="485cc-151">LINQ to SQL supports mapping the CLR <xref:System.Enum?displayProperty=nameWithType> type to SQL Server types in two ways:</span></span>  
  
-   <span data-ttu-id="485cc-152">映射到 SQL 数值类型（`TINYINT`、`SMALLINT`、`INT`、`BIGINT`）</span><span class="sxs-lookup"><span data-stu-id="485cc-152">Mapping to SQL numeric types (`TINYINT`, `SMALLINT`, `INT`, `BIGINT`)</span></span>  
  
     <span data-ttu-id="485cc-153">将 CLR <xref:System.Enum?displayProperty=nameWithType> 类型映射到 SQL 数值类型时，您会将此 CLR <xref:System.Enum?displayProperty=nameWithType> 的基础整数值映射到 SQL Server 数据库列的值。</span><span class="sxs-lookup"><span data-stu-id="485cc-153">When you map a CLR <xref:System.Enum?displayProperty=nameWithType> type to a SQL numeric type, you map the underlying integer value of the CLR <xref:System.Enum?displayProperty=nameWithType> to the value of the SQL Server database column.</span></span> <span data-ttu-id="485cc-154">例如，如果一个名为 <xref:System.Enum?displayProperty=nameWithType> 的 `DaysOfWeek` 包含一个名为 `Tue` 且基础整数值为 3 的成员，则此成员映射到数据库值 3。</span><span class="sxs-lookup"><span data-stu-id="485cc-154">For example, if a <xref:System.Enum?displayProperty=nameWithType> named `DaysOfWeek` contains a member named `Tue` with an underlying integer value of 3, that member maps to a database value of 3.</span></span>  
  
-   <span data-ttu-id="485cc-155">映射到 SQL 文本类型（`CHAR`、`NCHAR`、`VARCHAR`、`NVARCHAR`）</span><span class="sxs-lookup"><span data-stu-id="485cc-155">Mapping to SQL text types (`CHAR`, `NCHAR`, `VARCHAR`, `NVARCHAR`)</span></span>  
  
     <span data-ttu-id="485cc-156">将 CLR <xref:System.Enum?displayProperty=nameWithType> 类型映射到 SQL 文本类型时，SQL 数据库值会映射到 CLR <xref:System.Enum?displayProperty=nameWithType> 成员的名称。</span><span class="sxs-lookup"><span data-stu-id="485cc-156">When you map a CLR <xref:System.Enum?displayProperty=nameWithType> type to a SQL text type, the SQL database value is mapped to the names of the CLR <xref:System.Enum?displayProperty=nameWithType> members.</span></span> <span data-ttu-id="485cc-157">例如，如果一个名为 <xref:System.Enum?displayProperty=nameWithType> 的 `DaysOfWeek` 包含一个名为 `Tue` 且基础整数值为 3 的成员，则此成员映射到数据库值 `Tue`。</span><span class="sxs-lookup"><span data-stu-id="485cc-157">For example, if a <xref:System.Enum?displayProperty=nameWithType> named `DaysOfWeek` contains a member named `Tue` with an underlying integer value of 3, that member maps to a database value of `Tue`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="485cc-158">将 SQL 文本类型映射到 CLR <xref:System.Enum?displayProperty=nameWithType> 时，映射的 SQL 列中仅包含 <xref:System.Enum> 成员的名称。</span><span class="sxs-lookup"><span data-stu-id="485cc-158">When mapping SQL text types to a CLR <xref:System.Enum?displayProperty=nameWithType>, include only the names of the <xref:System.Enum> members in the mapped SQL column.</span></span> <span data-ttu-id="485cc-159"><xref:System.Enum> 映射的 SQL 列不支持其他值。</span><span class="sxs-lookup"><span data-stu-id="485cc-159">Other values are not supported in the <xref:System.Enum>-mapped SQL column.</span></span>  
  
 <span data-ttu-id="485cc-160">O/R 设计器和 SQLMetal 命令行工具无法将 SQL 类型自动映射到 CLR <xref:System.Enum> 类。</span><span class="sxs-lookup"><span data-stu-id="485cc-160">The O/R Designer and SQLMetal command-line tool cannot automatically map a SQL type to a CLR <xref:System.Enum> class.</span></span> <span data-ttu-id="485cc-161">您必须通过自定义 DBML 文件以供 O/R 设计器和 SQLMetal 使用来显式配置此映射。</span><span class="sxs-lookup"><span data-stu-id="485cc-161">You must explicitly configure this mapping by customizing a DBML file for use by the O/R Designer and SQLMetal.</span></span> <span data-ttu-id="485cc-162">有关自定义类型映射的信息的详细信息，请参阅[SQL-CLR 自定义类型映射](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-custom-type-mappings.md)。</span><span class="sxs-lookup"><span data-stu-id="485cc-162">For more information about custom type mapping, see [SQL-CLR Custom Type Mappings](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-custom-type-mappings.md).</span></span>  
  
 <span data-ttu-id="485cc-163">因为用于枚举的 SQL 列将具有与其他数值和文本列; 同一类型这些工具将无法识别您的意图并默认的映射在下面的示例所述[数值映射](#NumericMapping)和[文本和 XML 映射](#TextMapping)部分。</span><span class="sxs-lookup"><span data-stu-id="485cc-163">Because a SQL column intended for enumeration will be of the same type as other numeric and text columns; these tools will not recognize your intent and default to mapping as described in the following [Numeric Mapping](#NumericMapping) and [Text and XML Mapping](#TextMapping) sections.</span></span> <span data-ttu-id="485cc-164">有关使用 DBML 文件生成代码的详细信息，请参阅[LINQ to SQL 中的代码生成](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="485cc-164">For more information about generating code with the DBML file, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
 <span data-ttu-id="485cc-165"><xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 方法创建一个数值类型的 SQL 列以映射 CLR <xref:System.Enum?displayProperty=nameWithType> 类型。</span><span class="sxs-lookup"><span data-stu-id="485cc-165">The <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method creates a SQL column of numeric type to map a CLR <xref:System.Enum?displayProperty=nameWithType> type.</span></span>  
  
<a name="NumericMapping"></a>   
## <a name="numeric-mapping"></a><span data-ttu-id="485cc-166">数值映射</span><span class="sxs-lookup"><span data-stu-id="485cc-166">Numeric Mapping</span></span>  
 <span data-ttu-id="485cc-167">LINQ to SQL 允许您映射多种 CLR 和 SQL Server 数值类型。</span><span class="sxs-lookup"><span data-stu-id="485cc-167">LINQ to SQL lets you map many CLR and SQL Server numeric types.</span></span> <span data-ttu-id="485cc-168">下表显示生成基于数据库的对象模型或外部映射文件时 O/R 设计器和 SQLMetal 选择的 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="485cc-168">The following table shows the CLR types that O/R Designer and SQLMetal select when building an object model or external mapping file based on your database.</span></span>  
  
|<span data-ttu-id="485cc-169">SQL Server 类型</span><span class="sxs-lookup"><span data-stu-id="485cc-169">SQL Server Type</span></span>|<span data-ttu-id="485cc-170">O/R 设计器和 SQLMetal 使用的默认 CLR 类型映射</span><span class="sxs-lookup"><span data-stu-id="485cc-170">Default CLR Type mapping used by O/R Designer and SQLMetal</span></span>|  
|---------------------|-----------------------------------------------------------------|  
|`BIT`|<xref:System.Boolean?displayProperty=nameWithType>|  
|`TINYINT`|<xref:System.Int16?displayProperty=nameWithType>|  
|`INT`|<xref:System.Int32?displayProperty=nameWithType>|  
|`BIGINT`|<xref:System.Int64?displayProperty=nameWithType>|  
|`SMALLMONEY`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`MONEY`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`DECIMAL`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`NUMERIC`|<xref:System.Decimal?displayProperty=nameWithType>|  
|`REAL/FLOAT(24)`|<xref:System.Single?displayProperty=nameWithType>|  
|`FLOAT/FLOAT(53)`|<xref:System.Double?displayProperty=nameWithType>|  
  
 <span data-ttu-id="485cc-171">下一个表显示 <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 方法使用的默认类型映射，以定义创建何种 SQL 列来映射到对象模型或外部映射文件中定义的 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="485cc-171">The next table shows the default type mappings used by the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method to define which type of SQL columns are created to map to the CLR types defined in your object model or external mapping file.</span></span>  
  
|<span data-ttu-id="485cc-172">CLR 类型</span><span class="sxs-lookup"><span data-stu-id="485cc-172">CLR Type</span></span>|<span data-ttu-id="485cc-173"><xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 使用的默认 SQL Server 类型</span><span class="sxs-lookup"><span data-stu-id="485cc-173">Default SQL Server Type used by <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType></span></span>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Boolean?displayProperty=nameWithType>|`BIT`|  
|<xref:System.Byte?displayProperty=nameWithType>|`TINYINT`|  
|<xref:System.Int16?displayProperty=nameWithType>|`SMALLINT`|  
|<xref:System.Int32?displayProperty=nameWithType>|`INT`|  
|<xref:System.Int64?displayProperty=nameWithType>|`BIGINT`|  
|<xref:System.SByte?displayProperty=nameWithType>|`SMALLINT`|  
|<xref:System.UInt16?displayProperty=nameWithType>|`INT`|  
|<xref:System.UInt32?displayProperty=nameWithType>|`BIGINT`|  
|<xref:System.UInt64?displayProperty=nameWithType>|`DECIMAL(20)`|  
|<xref:System.Decimal?displayProperty=nameWithType>|`DECIMAL(29,4)`|  
|<xref:System.Single?displayProperty=nameWithType>|`REAL`|  
|<xref:System.Double?displayProperty=nameWithType>|`FLOAT`|  
  
 <span data-ttu-id="485cc-174">有许多其他可以选择的数值映射，但是某些数值映射在转换到数据库或从数据库中转换时，可能会导致溢出或数据丢失异常。</span><span class="sxs-lookup"><span data-stu-id="485cc-174">There are many other numeric mappings you can choose, but some may result in overflow or data loss exceptions while translating to or from the database.</span></span> <span data-ttu-id="485cc-175">有关详细信息，请参阅[类型映射运行时行为矩阵](#BehaviorMatrix)。</span><span class="sxs-lookup"><span data-stu-id="485cc-175">For more information, see the [Type Mapping Run Time Behavior Matrix](#BehaviorMatrix).</span></span>  
  
### <a name="decimal-and-money-types"></a><span data-ttu-id="485cc-176">Decimal 和 Money 类型</span><span class="sxs-lookup"><span data-stu-id="485cc-176">Decimal and Money Types</span></span>  
 <span data-ttu-id="485cc-177">SQL Server 的默认精度`DECIMAL`类型 （18 十进制数字的左侧和右侧的小数点） 是比 CLR 的精度小得多<!--zz <xref:System.Decima?displayProperty=nameWithType>l -->`Decimal`与默认情况下配对的类型。</span><span class="sxs-lookup"><span data-stu-id="485cc-177">The default precision of SQL Server `DECIMAL` type (18 decimal digits to the left and right of the decimal point) is much smaller than the precision of the CLR <!--zz <xref:System.Decima?displayProperty=nameWithType>l --> `Decimal` type that it is paired with by default.</span></span> <span data-ttu-id="485cc-178">这可导致将数据保存到数据库时的精度降低。</span><span class="sxs-lookup"><span data-stu-id="485cc-178">This can result in precision loss when you save data to the database.</span></span> <span data-ttu-id="485cc-179">但是，如果将 SQL Server `DECIMAL` 类型配置为大于 29 位精度，则会产生相反的结果。</span><span class="sxs-lookup"><span data-stu-id="485cc-179">However, just the opposite can happen if the SQL Server `DECIMAL` type is configured with greater than 29 digits of precision.</span></span> <span data-ttu-id="485cc-180">将 SQL Server `DECIMAL` 类型的精度配置为大于 CLR <xref:System.Decimal?displayProperty=nameWithType> 时，则在从数据库检索数据时会发生精度降低。</span><span class="sxs-lookup"><span data-stu-id="485cc-180">When a SQL Server `DECIMAL` type has been configured with a greater precision than the CLR <xref:System.Decimal?displayProperty=nameWithType>, precision loss can occur when retrieving data from the database.</span></span>  
  
 <span data-ttu-id="485cc-181">默认情况下和 CLR `MONEY` 类型成对使用的 SQL Server `SMALLMONEY` 和 <xref:System.Decimal?displayProperty=nameWithType> 具有非常小的精度，在将数据保存到数据库时可导致溢出或数据丢失异常。</span><span class="sxs-lookup"><span data-stu-id="485cc-181">The SQL Server `MONEY` and `SMALLMONEY` types, which are also paired with the CLR <xref:System.Decimal?displayProperty=nameWithType> type by default, have a much smaller precision, which can result in overflow or data loss exceptions when saving data to the database.</span></span>  
  
<a name="TextMapping"></a>   
## <a name="text-and-xml-mapping"></a><span data-ttu-id="485cc-182">文本和 XML 映射</span><span class="sxs-lookup"><span data-stu-id="485cc-182">Text and XML Mapping</span></span>  
 <span data-ttu-id="485cc-183">还有很多基于文本的类型和 XML 类型，您可以使用 LINQ to SQL 将其映射。</span><span class="sxs-lookup"><span data-stu-id="485cc-183">There are also many text-based and XML types that you can map with LINQ to SQL.</span></span> <span data-ttu-id="485cc-184">下表显示生成基于数据库的对象模型或外部映射文件时 O/R 设计器和 SQLMetal 选择的 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="485cc-184">The following table shows the CLR types that O/R Designer and SQLMetal select when building an object model or external mapping file based on your database.</span></span>  
  
|<span data-ttu-id="485cc-185">SQL Server 类型</span><span class="sxs-lookup"><span data-stu-id="485cc-185">SQL Server Type</span></span>|<span data-ttu-id="485cc-186">O/R 设计器和 SQLMetal 使用的默认 CLR 类型映射</span><span class="sxs-lookup"><span data-stu-id="485cc-186">Default CLR Type mapping used by O/R Designer and SQLMetal</span></span>|  
|---------------------|-----------------------------------------------------------------|  
|`CHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`NCHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`VARCHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`NVARCHAR`|<xref:System.String?displayProperty=nameWithType>|  
|`TEXT`|<xref:System.String?displayProperty=nameWithType>|  
|`NTEXT`|<xref:System.String?displayProperty=nameWithType>|  
|`XML`|<xref:System.Xml.Linq.XElement?displayProperty=nameWithType>|  
  
 <span data-ttu-id="485cc-187">下一个表显示 <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 方法使用的默认类型映射，以定义创建何种 SQL 列来映射到对象模型或外部映射文件中定义的 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="485cc-187">The next table shows the default type mappings used by the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method to define which type of SQL columns are created to map to the CLR types defined in your object model or external mapping file.</span></span>  
  
|<span data-ttu-id="485cc-188">CLR 类型</span><span class="sxs-lookup"><span data-stu-id="485cc-188">CLR Type</span></span>|<span data-ttu-id="485cc-189"><xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 使用的默认 SQL Server 类型</span><span class="sxs-lookup"><span data-stu-id="485cc-189">Default SQL Server Type used by <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType></span></span>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Char?displayProperty=nameWithType>|`NCHAR(1)`|  
|<xref:System.String?displayProperty=nameWithType>|`NVARCHAR(4000)`|  
|<span data-ttu-id="485cc-190"><xref:System.Char?displayProperty=nameWithType>[]</span><span class="sxs-lookup"><span data-stu-id="485cc-190"><xref:System.Char?displayProperty=nameWithType>[]</span></span>|`NVARCHAR(4000)`|  
|<span data-ttu-id="485cc-191">实现 `Parse()` 和 `ToString()` 的自定义类型</span><span class="sxs-lookup"><span data-stu-id="485cc-191">Custom type implementing `Parse()` and `ToString()`</span></span>|`NVARCHAR(MAX)`|  
  
 <span data-ttu-id="485cc-192">有许多其他可以选择的基于文本的映射和 XML 映射，但是某些映射在转换到数据库或从数据库中转换时，可能会导致溢出或数据丢失异常。</span><span class="sxs-lookup"><span data-stu-id="485cc-192">There are many other text-based and XML mappings you can choose, but some may result in overflow or data loss exceptions while translating to or from the database.</span></span> <span data-ttu-id="485cc-193">有关详细信息，请参阅[类型映射运行时行为矩阵](#BehaviorMatrix)。</span><span class="sxs-lookup"><span data-stu-id="485cc-193">For more information, see the [Type Mapping Run Time Behavior Matrix](#BehaviorMatrix).</span></span>  
  
### <a name="xml-types"></a><span data-ttu-id="485cc-194">XML 类型</span><span class="sxs-lookup"><span data-stu-id="485cc-194">XML Types</span></span>  
 <span data-ttu-id="485cc-195">从 Microsoft SQL Server 2005 开始，提供了 SQL Server `XML` 数据类型。</span><span class="sxs-lookup"><span data-stu-id="485cc-195">The SQL Server `XML` data type is available starting in Microsoft SQL Server 2005.</span></span> <span data-ttu-id="485cc-196">您可以将 SQL Server `XML` 数据类型映射到 <xref:System.Xml.Linq.XElement>、<xref:System.Xml.Linq.XDocument> 或 <xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="485cc-196">You can map the SQL Server `XML` data type to <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XDocument>, or <xref:System.String>.</span></span> <span data-ttu-id="485cc-197">如果列中存储了无法读入 <xref:System.Xml.Linq.XElement> 的 XML 片段，则此列必须映射到 <xref:System.String> 以免出现运行时错误。</span><span class="sxs-lookup"><span data-stu-id="485cc-197">If the column stores XML fragments that cannot be read into <xref:System.Xml.Linq.XElement>, the column must be mapped to <xref:System.String> to avoid run-time errors.</span></span> <span data-ttu-id="485cc-198">必须映射到 <xref:System.String> 的 XML 片段包括：</span><span class="sxs-lookup"><span data-stu-id="485cc-198">XML fragments that must be mapped to <xref:System.String> include the following:</span></span>  
  
-   <span data-ttu-id="485cc-199">XML 元素的序列。</span><span class="sxs-lookup"><span data-stu-id="485cc-199">A sequence of XML elements</span></span>  
  
-   <span data-ttu-id="485cc-200">特性</span><span class="sxs-lookup"><span data-stu-id="485cc-200">Attributes</span></span>  
  
-   <span data-ttu-id="485cc-201">公共标识符 (PI)</span><span class="sxs-lookup"><span data-stu-id="485cc-201">Public Identifiers (PI)</span></span>  
  
-   <span data-ttu-id="485cc-202">注释</span><span class="sxs-lookup"><span data-stu-id="485cc-202">Comments</span></span>  
  
 <span data-ttu-id="485cc-203">尽管你可以映射<xref:System.Xml.Linq.XElement>和<xref:System.Xml.Linq.XDocument>到 SQL Server 中所示[类型映射运行时行为矩阵](#BehaviorMatrix)、<xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>方法具有这些类型的任何默认 SQL Server 类型映射。</span><span class="sxs-lookup"><span data-stu-id="485cc-203">Although you can map <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> to SQL Server as shown in the [Type Mapping Run Time Behavior Matrix](#BehaviorMatrix), the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method has no default SQL Server type mapping for these types.</span></span>  
  
### <a name="custom-types"></a><span data-ttu-id="485cc-204">自定义类型</span><span class="sxs-lookup"><span data-stu-id="485cc-204">Custom Types</span></span>  
 <span data-ttu-id="485cc-205">如果一个类实现`Parse()`和`ToString()`，可以将对象映射到任何 SQL 文本类型 (`CHAR`， `NCHAR`， `VARCHAR`， `NVARCHAR`， `TEXT`， `NTEXT`， `XML`)。</span><span class="sxs-lookup"><span data-stu-id="485cc-205">If a class implements `Parse()` and `ToString()`, you can map the object to any SQL text type (`CHAR`, `NCHAR`, `VARCHAR`, `NVARCHAR`, `TEXT`, `NTEXT`, `XML`).</span></span> <span data-ttu-id="485cc-206">通过将 `ToString()` 返回的值发送到映射的数据库列，把对象存储在数据库中。</span><span class="sxs-lookup"><span data-stu-id="485cc-206">The object is stored in the database by sending the value returned by `ToString()` to the mapped database column.</span></span> <span data-ttu-id="485cc-207">通过在数据库返回的字符串上调用 `Parse()` 重新构造对象。</span><span class="sxs-lookup"><span data-stu-id="485cc-207">The object is reconstructed by invoking `Parse()` on the string returned by the database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="485cc-208">LINQ to SQL 不支持使用 <xref:System.Xml.Serialization.IXmlSerializable?displayProperty=nameWithType> 进行序列化。</span><span class="sxs-lookup"><span data-stu-id="485cc-208">LINQ to SQL does not support serialization by using <xref:System.Xml.Serialization.IXmlSerializable?displayProperty=nameWithType>.</span></span>  
  
<a name="DateMapping"></a>   
## <a name="date-and-time-mapping"></a><span data-ttu-id="485cc-209">日期和时间映射</span><span class="sxs-lookup"><span data-stu-id="485cc-209">Date and Time Mapping</span></span>  
 <span data-ttu-id="485cc-210">通过使用 LINQ to SQL，您可以映射多种 SQL Server 日期和时间类型。</span><span class="sxs-lookup"><span data-stu-id="485cc-210">With LINQ to SQL, you can map many SQL Server date and time types.</span></span> <span data-ttu-id="485cc-211">下表显示生成基于数据库的对象模型或外部映射文件时 O/R 设计器和 SQLMetal 选择的 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="485cc-211">The following table shows the CLR types that O/R Designer and SQLMetal select when building an object model or external mapping file based on your database.</span></span>  
  
|<span data-ttu-id="485cc-212">SQL Server 类型</span><span class="sxs-lookup"><span data-stu-id="485cc-212">SQL Server Type</span></span>|<span data-ttu-id="485cc-213">O/R 设计器和 SQLMetal 使用的默认 CLR 类型映射</span><span class="sxs-lookup"><span data-stu-id="485cc-213">Default CLR Type mapping used by O/R Designer and SQLMetal</span></span>|  
|---------------------|-----------------------------------------------------------------|  
|`SMALLDATETIME`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`DATETIME`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`DATETIME2`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`DATETIMEOFFSET`|<xref:System.DateTimeOffset?displayProperty=nameWithType>|  
|`DATE`|<xref:System.DateTime?displayProperty=nameWithType>|  
|`TIME`|<xref:System.TimeSpan?displayProperty=nameWithType>|  
  
 <span data-ttu-id="485cc-214">下一个表显示 <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 方法使用的默认类型映射，以定义创建何种 SQL 列来映射到对象模型或外部映射文件中定义的 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="485cc-214">The next table shows the default type mappings used by the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method to define which type of SQL columns are created to map to the CLR types defined in your object model or external mapping file.</span></span>  
  
|<span data-ttu-id="485cc-215">CLR 类型</span><span class="sxs-lookup"><span data-stu-id="485cc-215">CLR Type</span></span>|<span data-ttu-id="485cc-216"><xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 使用的默认 SQL Server 类型</span><span class="sxs-lookup"><span data-stu-id="485cc-216">Default SQL Server Type used by <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType></span></span>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.DateTime?displayProperty=nameWithType>|`DATETIME`|  
|<xref:System.DateTimeOffset?displayProperty=nameWithType>|`DATETIMEOFFSET`|  
|<xref:System.TimeSpan?displayProperty=nameWithType>|`TIME`|  
  
 <span data-ttu-id="485cc-217">有许多其他可以选择的日期和时间映射，但是某些映射在转换到数据库或从数据库中转换时，可能会导致溢出或数据丢失异常。</span><span class="sxs-lookup"><span data-stu-id="485cc-217">There are many other date and time mappings you can choose, but some may result in overflow or data loss exceptions while translating to or from the database.</span></span> <span data-ttu-id="485cc-218">有关详细信息，请参阅[类型映射运行时行为矩阵](#BehaviorMatrix)。</span><span class="sxs-lookup"><span data-stu-id="485cc-218">For more information, see the [Type Mapping Run Time Behavior Matrix](#BehaviorMatrix).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="485cc-219">从 Microsoft SQL Server 2008 开始，提供了 SQL Server 类型 `DATETIME2`、`DATETIMEOFFSET`、`DATE` 和 `TIME`。</span><span class="sxs-lookup"><span data-stu-id="485cc-219">The SQL Server types `DATETIME2`, `DATETIMEOFFSET`, `DATE`, and `TIME` are available starting with Microsoft SQL Server 2008.</span></span> <span data-ttu-id="485cc-220">从 .NET Framework 版本 3.5 SP1 开始，LINQ to SQL 支持映射到这些新类型。</span><span class="sxs-lookup"><span data-stu-id="485cc-220">LINQ to SQL supports mapping to these new types starting with the .NET Framework version 3.5 SP1.</span></span>  
  
### <a name="systemdatetime"></a><span data-ttu-id="485cc-221">System.Datetime</span><span class="sxs-lookup"><span data-stu-id="485cc-221">System.Datetime</span></span>  
 <span data-ttu-id="485cc-222">CLR <xref:System.DateTime?displayProperty=nameWithType> 类型的范围和精度大于 SQL Server `DATETIME` 类型，这是 <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 方法的默认类型映射。</span><span class="sxs-lookup"><span data-stu-id="485cc-222">The range and precision of the CLR <xref:System.DateTime?displayProperty=nameWithType> type is greater than the range and precision of the SQL Server `DATETIME` type, which is the default type mapping for the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="485cc-223">要避免与 `DATETIME` 范围之外的日期相关的异常，请使用 `DATETIME2`（从 Microsoft SQL Server 2008 开始可用）。</span><span class="sxs-lookup"><span data-stu-id="485cc-223">To help avoid exceptions related to dates outside the range of `DATETIME`, use `DATETIME2`, which is available starting with Microsoft SQL Server 2008.</span></span> <span data-ttu-id="485cc-224">`DATETIME2`可以与匹配的范围和精度 CLR <xref:System.DateTime?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="485cc-224">`DATETIME2` can match the range and precision of the CLR <xref:System.DateTime?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="485cc-225">SQL Server 日期不具有 <xref:System.TimeZone>（CLR 中得到充分支持的一种功能）的概念。</span><span class="sxs-lookup"><span data-stu-id="485cc-225">SQL Server dates have no concept of <xref:System.TimeZone>, a feature that is richly supported in the CLR.</span></span> <span data-ttu-id="485cc-226">无论原始 <xref:System.TimeZone> 信息如何，<xref:System.TimeZone> 值均不进行 <xref:System.DateTimeKind> 转换，按原样保存到数据库中。</span><span class="sxs-lookup"><span data-stu-id="485cc-226"><xref:System.TimeZone> values are saved as is to the database without <xref:System.TimeZone> conversion, regardless of the original <xref:System.DateTimeKind> information.</span></span> <span data-ttu-id="485cc-227">从数据库中检索到 <xref:System.DateTime> 值时，它们的值按原样加载到 <xref:System.DateTime> 为 <xref:System.DateTimeKind> 的 <xref:System.DateTimeKind.Unspecified> 中。</span><span class="sxs-lookup"><span data-stu-id="485cc-227">When <xref:System.DateTime> values are retrieved from the database, their value is loaded as is into a <xref:System.DateTime> with a <xref:System.DateTimeKind> of <xref:System.DateTimeKind.Unspecified>.</span></span> <span data-ttu-id="485cc-228">有关详细信息支持<xref:System.DateTime?displayProperty=nameWithType>方法，请参阅[System.DateTime 方法](../../../../../../docs/framework/data/adonet/sql/linq/system-datetime-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="485cc-228">For more information about supported <xref:System.DateTime?displayProperty=nameWithType> methods, see [System.DateTime Methods](../../../../../../docs/framework/data/adonet/sql/linq/system-datetime-methods.md).</span></span>  
  
### <a name="systemtimespan"></a><span data-ttu-id="485cc-229">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="485cc-229">System.TimeSpan</span></span>  
 <span data-ttu-id="485cc-230">Microsoft SQL Server 2008 和 .NET Framework 3.5 SP1 允许您将 CLR <xref:System.TimeSpan?displayProperty=nameWithType> 类型映射到 SQL Server `TIME` 类型。</span><span class="sxs-lookup"><span data-stu-id="485cc-230">Microsoft SQL Server 2008 and the .NET Framework 3.5 SP1 let you map the CLR <xref:System.TimeSpan?displayProperty=nameWithType> type to the SQL Server `TIME` type.</span></span> <span data-ttu-id="485cc-231">但是，CLR <xref:System.TimeSpan?displayProperty=nameWithType> 支持的范围和 SQL Server `TIME` 类型支持的范围之间存在很大的差异。</span><span class="sxs-lookup"><span data-stu-id="485cc-231">However, there is a large difference between the range that the CLR <xref:System.TimeSpan?displayProperty=nameWithType> supports and what the SQL Server `TIME` type supports.</span></span> <span data-ttu-id="485cc-232">SQL `TIME` 的映射值小于 0 或大于 23:59:59.9999999 小时将导致溢出异常。</span><span class="sxs-lookup"><span data-stu-id="485cc-232">Mapping values less than 0 or greater than 23:59:59.9999999 hours to the SQL `TIME` will result in overflow exceptions.</span></span> <span data-ttu-id="485cc-233">有关详细信息，请参阅[System.TimeSpan 方法](../../../../../../docs/framework/data/adonet/sql/linq/system-timespan-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="485cc-233">For more information, see [System.TimeSpan Methods](../../../../../../docs/framework/data/adonet/sql/linq/system-timespan-methods.md).</span></span>  
  
 <span data-ttu-id="485cc-234">在 Microsoft SQL Server 2000 和 SQL Server 2005 中，您无法将数据库字段映射到 <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="485cc-234">In Microsoft SQL Server 2000 and SQL Server 2005, you cannot map database fields to <xref:System.TimeSpan>.</span></span> <span data-ttu-id="485cc-235">但是，支持对 <xref:System.TimeSpan> 的操作，原因是可以通过 <xref:System.TimeSpan> 减法运算返回 <xref:System.DateTime> 值或将这些值作为文本或绑定变量引入表达式。</span><span class="sxs-lookup"><span data-stu-id="485cc-235">However, operations on <xref:System.TimeSpan> are supported because <xref:System.TimeSpan> values can be returned from <xref:System.DateTime> subtraction or introduced into an expression as a literal or bound variable.</span></span>  
  
<a name="BinaryMapping"></a>   
## <a name="binary-mapping"></a><span data-ttu-id="485cc-236">二进制映射</span><span class="sxs-lookup"><span data-stu-id="485cc-236">Binary Mapping</span></span>  
 <span data-ttu-id="485cc-237">还有很多可以映射到 CLR 类型 <xref:System.Data.Linq.Binary?displayProperty=nameWithType> 的 SQL Server 类型。</span><span class="sxs-lookup"><span data-stu-id="485cc-237">There are many SQL Server types that can map to the CLR type <xref:System.Data.Linq.Binary?displayProperty=nameWithType>.</span></span> <span data-ttu-id="485cc-238">下表显示生成基于数据库的对象模型或外部映射文件时使 O/R 设计器和 SQLMetal 定义 CLR <xref:System.Data.Linq.Binary?displayProperty=nameWithType> 类型的 SQL Server 类型。</span><span class="sxs-lookup"><span data-stu-id="485cc-238">The following table shows the SQL Server types that cause O/R Designer and SQLMetal to define a CLR <xref:System.Data.Linq.Binary?displayProperty=nameWithType> type when building an object model or external mapping file based on your database.</span></span>  
  
|<span data-ttu-id="485cc-239">SQL Server 类型</span><span class="sxs-lookup"><span data-stu-id="485cc-239">SQL Server Type</span></span>|<span data-ttu-id="485cc-240">O/R 设计器和 SQLMetal 使用的默认 CLR 类型映射</span><span class="sxs-lookup"><span data-stu-id="485cc-240">Default CLR Type mapping used by O/R Designer and SQLMetal</span></span>|  
|---------------------|-----------------------------------------------------------------|  
|`BINARY(50)`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`VARBINARY(50)`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`VARBINARY(MAX)`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|<span data-ttu-id="485cc-241">`VARBINARY(MAX)`与`FILESTREAM`属性</span><span class="sxs-lookup"><span data-stu-id="485cc-241">`VARBINARY(MAX)` with the `FILESTREAM` attribute</span></span>|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`IMAGE`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
|`TIMESTAMP`|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|  
  
 <span data-ttu-id="485cc-242">下一个表显示 <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 方法使用的默认类型映射，以定义创建何种 SQL 列来映射到对象模型或外部映射文件中定义的 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="485cc-242">The next table shows the default type mappings used by the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method to define which type of SQL columns are created to map to the CLR types defined in your object model or external mapping file.</span></span>  
  
|<span data-ttu-id="485cc-243">CLR 类型</span><span class="sxs-lookup"><span data-stu-id="485cc-243">CLR Type</span></span>|<span data-ttu-id="485cc-244"><xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 使用的默认 SQL Server 类型</span><span class="sxs-lookup"><span data-stu-id="485cc-244">Default SQL Server Type used by <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType></span></span>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Data.Linq.Binary?displayProperty=nameWithType>|`VARBINARY(MAX)`|  
|<xref:System.Byte?displayProperty=nameWithType>|`VARBINARY(MAX)`|  
|<xref:System.Runtime.Serialization.ISerializable?displayProperty=nameWithType>|`VARBINARY(MAX)`|  
  
 <span data-ttu-id="485cc-245">有许多其他可以选择的二进制映射，但是某些映射在转换到数据库或从数据库中转换时，可能会导致溢出或数据丢失异常。</span><span class="sxs-lookup"><span data-stu-id="485cc-245">There are many other binary mappings you can choose, but some may result in overflow or data loss exceptions while translating to or from the database.</span></span> <span data-ttu-id="485cc-246">有关详细信息，请参阅[类型映射运行时行为矩阵](#BehaviorMatrix)。</span><span class="sxs-lookup"><span data-stu-id="485cc-246">For more information, see the [Type Mapping Run Time Behavior Matrix](#BehaviorMatrix).</span></span>  
  
### <a name="sql-server-filestream"></a><span data-ttu-id="485cc-247">SQL Server FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="485cc-247">SQL Server FILESTREAM</span></span>  
 <span data-ttu-id="485cc-248">从 Microsoft SQL Server 2008 开始，提供了 `FILESTREAM` 列的 `VARBINARY(MAX)` 属性；从 .NET Framework 版本 3.5 SP1 开始，您可以使用 LINQ to SQL 映射到该属性。</span><span class="sxs-lookup"><span data-stu-id="485cc-248">The `FILESTREAM` attribute for `VARBINARY(MAX)` columns is available starting with Microsoft SQL Server 2008; you can map to it with LINQ to SQL starting with the .NET Framework version 3.5 SP1.</span></span>  
  
 <span data-ttu-id="485cc-249">尽管您可以使用 `VARBINARY(MAX)` 属性将 `FILESTREAM` 列映射到 <xref:System.Data.Linq.Binary> 对象，但是 <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 方法无法使用 `FILESTREAM` 属性自动创建列。</span><span class="sxs-lookup"><span data-stu-id="485cc-249">Although you can map `VARBINARY(MAX)` columns with the `FILESTREAM` attribute to <xref:System.Data.Linq.Binary> objects, the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method is unable to automatically create columns with the `FILESTREAM` attribute.</span></span> <span data-ttu-id="485cc-250">有关详细信息`FILESTREAM`，请参阅[FILESTREAM 概述](http://go.microsoft.com/fwlink/?LinkId=115291)上 Microsoft SQL Server 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="485cc-250">For more information about `FILESTREAM`, see [FILESTREAM Overview](http://go.microsoft.com/fwlink/?LinkId=115291) on Microsoft SQL Server Books Online.</span></span>  
  
<a name="BinarySerialization"></a>   
### <a name="binary-serialization"></a><span data-ttu-id="485cc-251">二进制序列化</span><span class="sxs-lookup"><span data-stu-id="485cc-251">Binary Serialization</span></span>  
 <span data-ttu-id="485cc-252">如果一个类实现了 <xref:System.Runtime.Serialization.ISerializable> 接口，则可以将对象序列化到任何 SQL 二进制字段 (`BINARY`、`VARBINARY`、`IMAGE`)。</span><span class="sxs-lookup"><span data-stu-id="485cc-252">If a class implements the <xref:System.Runtime.Serialization.ISerializable> interface, you can serialize an object to any SQL binary field (`BINARY`, `VARBINARY`, `IMAGE`).</span></span> <span data-ttu-id="485cc-253">将根据如何实现 <xref:System.Runtime.Serialization.ISerializable> 接口来对对象进行序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="485cc-253">The object is serialized and deserialized according to how the <xref:System.Runtime.Serialization.ISerializable> interface is implemented.</span></span> <span data-ttu-id="485cc-254">有关详细信息，请参阅[二进制序列化](http://go.microsoft.com/fwlink/?LinkId=115581)。</span><span class="sxs-lookup"><span data-stu-id="485cc-254">For more information, see [Binary Serialization](http://go.microsoft.com/fwlink/?LinkId=115581).</span></span>  
  
<a name="MiscMapping"></a>   
## <a name="miscellaneous-mapping"></a><span data-ttu-id="485cc-255">杂项映射</span><span class="sxs-lookup"><span data-stu-id="485cc-255">Miscellaneous Mapping</span></span>  
 <span data-ttu-id="485cc-256">下表显示一些尚未提及的杂项类型的默认类型映射。</span><span class="sxs-lookup"><span data-stu-id="485cc-256">The following table shows the default type mappings for some miscellaneous types that have not yet been mentioned.</span></span> <span data-ttu-id="485cc-257">下表显示生成基于数据库的对象模型或外部映射文件时 O/R 设计器和 SQLMetal 选择的 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="485cc-257">The following table shows the CLR types that O/R Designer and SQLMetal select when building an object model or external mapping file based on your database.</span></span>  
  
|<span data-ttu-id="485cc-258">SQL Server 类型</span><span class="sxs-lookup"><span data-stu-id="485cc-258">SQL Server Type</span></span>|<span data-ttu-id="485cc-259">O/R 设计器和 SQLMetal 使用的默认 CLR 类型映射</span><span class="sxs-lookup"><span data-stu-id="485cc-259">Default CLR Type mapping used by O/R Designer and SQLMetal</span></span>|  
|---------------------|-----------------------------------------------------------------|  
|`UNIQUEIDENTIFIER`|<xref:System.Guid?displayProperty=nameWithType>|  
|`SQL_VARIANT`|<xref:System.Object?displayProperty=nameWithType>|  
  
 <span data-ttu-id="485cc-260">下一个表显示 <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 方法使用的默认类型映射，以定义创建何种 SQL 列来映射到对象模型或外部映射文件中定义的 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="485cc-260">The next table shows the default type mappings used by the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method to define which type of SQL columns are created to map to the CLR types defined in your object model or external mapping file.</span></span>  
  
|<span data-ttu-id="485cc-261">CLR 类型</span><span class="sxs-lookup"><span data-stu-id="485cc-261">CLR Type</span></span>|<span data-ttu-id="485cc-262"><xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 使用的默认 SQL Server 类型</span><span class="sxs-lookup"><span data-stu-id="485cc-262">Default SQL Server Type used by <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType></span></span>|  
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Guid?displayProperty=nameWithType>|`UNIQUEIDENTIFIER`|  
|<xref:System.Object?displayProperty=nameWithType>|`SQL_VARIANT`|  
  
 <span data-ttu-id="485cc-263">LINQ to SQL 不支持这些杂项类型的任何其他类型映射。</span><span class="sxs-lookup"><span data-stu-id="485cc-263">LINQ to SQL does not support any other type mappings for these miscellaneous types.</span></span>  <span data-ttu-id="485cc-264">有关详细信息，请参阅[类型映射运行时行为矩阵](#BehaviorMatrix)。</span><span class="sxs-lookup"><span data-stu-id="485cc-264">For more information, see the [Type Mapping Run Time Behavior Matrix](#BehaviorMatrix).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="485cc-265">请参阅</span><span class="sxs-lookup"><span data-stu-id="485cc-265">See Also</span></span>  
 [<span data-ttu-id="485cc-266">基于特性的映射</span><span class="sxs-lookup"><span data-stu-id="485cc-266">Attribute-Based Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)  
 [<span data-ttu-id="485cc-267">外部映射</span><span class="sxs-lookup"><span data-stu-id="485cc-267">External Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)  
 [<span data-ttu-id="485cc-268">数据类型和函数</span><span class="sxs-lookup"><span data-stu-id="485cc-268">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)  
 [<span data-ttu-id="485cc-269">SQL-CLR 类型不匹配</span><span class="sxs-lookup"><span data-stu-id="485cc-269">SQL-CLR Type Mismatches</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)
