---
title: SQL-CLR 类型不匹配
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0a90c33f-7ed7-4501-ad5f-6224c5da8e9b
ms.openlocfilehash: 77090a9f22dcf3d55739aa03535bee863793d858
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59172882"
---
# <a name="sql-clr-type-mismatches"></a><span data-ttu-id="02d0e-102">SQL-CLR 类型不匹配</span><span class="sxs-lookup"><span data-stu-id="02d0e-102">SQL-CLR Type Mismatches</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="02d0e-103">可以自动完成对象模型和 SQL Server 之间的大量转换。</span><span class="sxs-lookup"><span data-stu-id="02d0e-103">automates much of the translation between the object model and SQL Server.</span></span> <span data-ttu-id="02d0e-104">不过，有一些情况会阻碍进行精确转换。</span><span class="sxs-lookup"><span data-stu-id="02d0e-104">Nevertheless, some situations prevent exact translation.</span></span> <span data-ttu-id="02d0e-105">以下各部分将介绍公共语言运行库 (CLR) 类型与 SQL Server 数据库类型之间的主要不匹配。</span><span class="sxs-lookup"><span data-stu-id="02d0e-105">These key mismatches between the common language runtime (CLR) types and the SQL Server database types are summarized in the following sections.</span></span> <span data-ttu-id="02d0e-106">您可以找到有关特定类型映射和函数转换在更多详细信息[SQL-CLR 类型映射](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)并[数据类型及函数](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="02d0e-106">You can find more details about specific type mappings and function translation at [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md) and [Data Types and Functions](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md).</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="02d0e-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="02d0e-107">Data Types</span></span>  
 <span data-ttu-id="02d0e-108">将查询发送给数据库时和将结果发送回对象模型时，CLR 和 SQL Server 之间将发生转换。</span><span class="sxs-lookup"><span data-stu-id="02d0e-108">Translation between the CLR and SQL Server occurs when a query is being sent to the database, and when the results are sent back to your object model.</span></span> <span data-ttu-id="02d0e-109">例如，下面的 Transact-SQL 查询需要进行两次值转换：</span><span class="sxs-lookup"><span data-stu-id="02d0e-109">For example, the following Transact-SQL query requires two value conversions:</span></span>  
  
```  
Select DateOfBirth From Customer Where CustomerId = @id     
```  
  
 <span data-ttu-id="02d0e-110">可在 SQL Server 上执行查询之前，必须指定 Transact-SQL 参数的值。</span><span class="sxs-lookup"><span data-stu-id="02d0e-110">Before the query can be executed on SQL Server, the value for the Transact-SQL parameter must be specified.</span></span> <span data-ttu-id="02d0e-111">在此示例中，首先必须将 `id` 参数值从 CLR <xref:System.Int32?displayProperty=nameWithType> 类型转换为 SQL Server `INT` 类型，以便数据库可以理解该值。</span><span class="sxs-lookup"><span data-stu-id="02d0e-111">In this example, the `id` parameter value must first be translated from a CLR <xref:System.Int32?displayProperty=nameWithType> type to a SQL Server `INT` type so that the database can understand what the value is.</span></span> <span data-ttu-id="02d0e-112">然后，必须将 SQL Server `DateOfBirth` 列从 SQL Server `DATETIME` 类型转换为 CLR <xref:System.DateTime?displayProperty=nameWithType> 类型以在对象模型中使用，才能检索结果。</span><span class="sxs-lookup"><span data-stu-id="02d0e-112">Then to retrieve the results, the SQL Server `DateOfBirth` column must be translated from a SQL Server `DATETIME` type to a CLR <xref:System.DateTime?displayProperty=nameWithType> type for use in the object model.</span></span> <span data-ttu-id="02d0e-113">在此示例中，CLR 对象模型中的类型与 SQL Server 数据库中的类型会自然建立映射，</span><span class="sxs-lookup"><span data-stu-id="02d0e-113">In this example, the types in the CLR object model and SQL Server database have natural mappings.</span></span> <span data-ttu-id="02d0e-114">但不总是这样。</span><span class="sxs-lookup"><span data-stu-id="02d0e-114">But, this is not always the case.</span></span>  
  
### <a name="missing-counterparts"></a><span data-ttu-id="02d0e-115">缺少对应项</span><span class="sxs-lookup"><span data-stu-id="02d0e-115">Missing Counterparts</span></span>  
 <span data-ttu-id="02d0e-116">以下类型没有合理的对应项。</span><span class="sxs-lookup"><span data-stu-id="02d0e-116">The following types do not have reasonable counterparts.</span></span>  
  
-   <span data-ttu-id="02d0e-117">CLR <xref:System> 命名空间中的不匹配：</span><span class="sxs-lookup"><span data-stu-id="02d0e-117">Mismatches in the CLR <xref:System> namespace:</span></span>  
  
    -   <span data-ttu-id="02d0e-118">**无符号整数**。</span><span class="sxs-lookup"><span data-stu-id="02d0e-118">**Unsigned integers**.</span></span> <span data-ttu-id="02d0e-119">这些类型通常映射到较大大小的有符号对应项，以避免溢出。</span><span class="sxs-lookup"><span data-stu-id="02d0e-119">These types are typically mapped to their signed counterparts of larger size to avoid overflow.</span></span> <span data-ttu-id="02d0e-120">文本可以根据值转换为相同或较小大小的有符号数字。</span><span class="sxs-lookup"><span data-stu-id="02d0e-120">Literals can be converted to a signed numeric of the same or smaller size, based on value.</span></span>  
  
    -   <span data-ttu-id="02d0e-121">**布尔**。</span><span class="sxs-lookup"><span data-stu-id="02d0e-121">**Boolean**.</span></span> <span data-ttu-id="02d0e-122">这些类型可以映射到位、较大的数字或字符串。</span><span class="sxs-lookup"><span data-stu-id="02d0e-122">These types can be mapped to a bit or larger numeric or string.</span></span> <span data-ttu-id="02d0e-123">文本可以映射到计算结果为相同值的表达式（例如，SQL 中的 `1=1` 对应于 CLS 中的 `True`）。</span><span class="sxs-lookup"><span data-stu-id="02d0e-123">A literal can be mapped to an expression that evaluates to the same value (for example, `1=1` in SQL for `True` in CLS).</span></span>  
  
    -   <span data-ttu-id="02d0e-124">**时间跨度**。</span><span class="sxs-lookup"><span data-stu-id="02d0e-124">**TimeSpan**.</span></span> <span data-ttu-id="02d0e-125">此类型表示两个 `DateTime` 值之间的差异，并且不与 SQL Server 中的 `timestamp` 相对应。</span><span class="sxs-lookup"><span data-stu-id="02d0e-125">This type represents the difference between two `DateTime` values and does not correspond to the `timestamp` of SQL Server.</span></span> <span data-ttu-id="02d0e-126">在某些情况下，CLR <xref:System.TimeSpan?displayProperty=nameWithType> 还可以映射到 SQL Server `TIME` 类型。</span><span class="sxs-lookup"><span data-stu-id="02d0e-126">The CLR <xref:System.TimeSpan?displayProperty=nameWithType> may also map to the SQL Server `TIME` type in some cases.</span></span> <span data-ttu-id="02d0e-127">SQL Server `TIME` 类型只能表示小于 24 小时的正值。</span><span class="sxs-lookup"><span data-stu-id="02d0e-127">The SQL Server `TIME` type was only intended to represent positive values less than 24 hours.</span></span> <span data-ttu-id="02d0e-128">而 CLR <xref:System.TimeSpan> 具有的范围则大得多。</span><span class="sxs-lookup"><span data-stu-id="02d0e-128">The CLR <xref:System.TimeSpan> has a much larger range.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="02d0e-129">[!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] 中特定于 SQL Server 的 <xref:System.Data.SqlTypes> 类型不包含在此比较范围内。</span><span class="sxs-lookup"><span data-stu-id="02d0e-129">SQL Server-specific [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] types in <xref:System.Data.SqlTypes> are not included in this comparison.</span></span>  
  
-   <span data-ttu-id="02d0e-130">SQL Server 中的不匹配：</span><span class="sxs-lookup"><span data-stu-id="02d0e-130">Mismatches in SQL Server:</span></span>  
  
    -   <span data-ttu-id="02d0e-131">**固定长度字符类型**。</span><span class="sxs-lookup"><span data-stu-id="02d0e-131">**Fixed length character types**.</span></span> <span data-ttu-id="02d0e-132">TRANSACT-SQL 会区分 Unicode 和非 Unicode 类别并且每个类别有三个不同类型： 固定长度`nchar` / `char`，可变长度`nvarchar` / `varchar`，和较大`ntext` / `text`。</span><span class="sxs-lookup"><span data-stu-id="02d0e-132">Transact-SQL distinguishes between Unicode and non-Unicode categories and has three distinct types in each category: fixed length `nchar`/`char`, variable length `nvarchar`/`varchar`, and larger-sized `ntext`/`text`.</span></span> <span data-ttu-id="02d0e-133">固定长度字符类型可以映射到 CLR <xref:System.Char?displayProperty=nameWithType> 类型以检索字符，但在转换和行为方面不能真正对应于同一类型。</span><span class="sxs-lookup"><span data-stu-id="02d0e-133">The fixed length character types could be mapped to the CLR <xref:System.Char?displayProperty=nameWithType> type for retrieving characters, but they do not really correspond to the same type in conversions and behavior.</span></span>  
  
    -   <span data-ttu-id="02d0e-134">**位**。</span><span class="sxs-lookup"><span data-stu-id="02d0e-134">**Bit**.</span></span> <span data-ttu-id="02d0e-135">尽管 `bit` 域与 `Nullable<Boolean>` 具有相同数目的值，但二者是不同的类型。</span><span class="sxs-lookup"><span data-stu-id="02d0e-135">Although the `bit` domain has the same number of values as `Nullable<Boolean>`, the two are different types.</span></span> <span data-ttu-id="02d0e-136">`Bit` 接受的值`1`并`0`而不是`true` / `false`，并且不能用作布尔表达式的等效项。</span><span class="sxs-lookup"><span data-stu-id="02d0e-136">`Bit` takes values `1` and `0` instead of `true`/`false`, and cannot be used as an equivalent to Boolean expressions.</span></span>  
  
    -   <span data-ttu-id="02d0e-137">**时间戳**。</span><span class="sxs-lookup"><span data-stu-id="02d0e-137">**Timestamp**.</span></span> <span data-ttu-id="02d0e-138">与 CLR <xref:System.TimeSpan?displayProperty=nameWithType> 类型不同，SQL Server `TIMESTAMP` 类型表示由数据库生成的 8 字节数字，它对于每次更新都是唯一的，而不是基于 <xref:System.DateTime> 值之间的差异。</span><span class="sxs-lookup"><span data-stu-id="02d0e-138">Unlike the CLR <xref:System.TimeSpan?displayProperty=nameWithType> type, the SQL Server `TIMESTAMP` type represents an 8-byte number generated by the database that is unique for each update and is not based on the difference between <xref:System.DateTime> values.</span></span>  
  
    -   <span data-ttu-id="02d0e-139">**Money**并**SmallMoney**。</span><span class="sxs-lookup"><span data-stu-id="02d0e-139">**Money** and **SmallMoney**.</span></span> <span data-ttu-id="02d0e-140">这些类型可以映射到 <xref:System.Decimal>，但本质上是不同的类型，并且基于服务器的函数和转换也将它们视为不同的类型。</span><span class="sxs-lookup"><span data-stu-id="02d0e-140">These types can be mapped to <xref:System.Decimal> but are basically different types and are treated as such by server-based functions and conversions.</span></span>  
  
### <a name="multiple-mappings"></a><span data-ttu-id="02d0e-141">多重映射</span><span class="sxs-lookup"><span data-stu-id="02d0e-141">Multiple Mappings</span></span>  
 <span data-ttu-id="02d0e-142">有很多可以映射到一种或多种 CLR 数据类型的 SQL Server 数据类型。</span><span class="sxs-lookup"><span data-stu-id="02d0e-142">There are many SQL Server data types that you can map to one or more CLR data types.</span></span> <span data-ttu-id="02d0e-143">也有很多可以映射到一种或多种 SQL Server 类型的 CLR 类型。</span><span class="sxs-lookup"><span data-stu-id="02d0e-143">There are also many CLR types that you can map to one or more SQL Server types.</span></span> <span data-ttu-id="02d0e-144">虽然 LINQ to SQL 可能支持映射，但这并不意味着 CLR 与 SQL Server 之间映射的两种类型在精度、范围和语义上都完全匹配。</span><span class="sxs-lookup"><span data-stu-id="02d0e-144">Although a mapping may be supported by LINQ to SQL, it does not mean that the two types mapped between the CLR and SQL Server are a perfect match in precision, range, and semantics.</span></span> <span data-ttu-id="02d0e-145">某些映射可能在以上任何或所有方面存在差异。</span><span class="sxs-lookup"><span data-stu-id="02d0e-145">Some mappings may include differences in any or all of these dimensions.</span></span> <span data-ttu-id="02d0e-146">您可以找到有关这些可能出现的差异的详细信息在各种映射可能性[SQL-CLR 类型映射](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="02d0e-146">You can find details about these potential differences for the various mapping possibilities at [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span></span>  
  
### <a name="user-defined-types"></a><span data-ttu-id="02d0e-147">用户定义类型</span><span class="sxs-lookup"><span data-stu-id="02d0e-147">User-defined Types</span></span>  
 <span data-ttu-id="02d0e-148">用户定义的 CLR 类型旨在帮助弥合类型系统之间的差异。</span><span class="sxs-lookup"><span data-stu-id="02d0e-148">User-defined CLR types are designed to help bridge the type system gap.</span></span> <span data-ttu-id="02d0e-149">不过，这些类型也引起了与类型版本管理有关的值得注意的问题。</span><span class="sxs-lookup"><span data-stu-id="02d0e-149">Nevertheless they surface interesting issues about type versioning.</span></span> <span data-ttu-id="02d0e-150">客户端上的版本更改可能无法与数据库服务器上存储的类型的更改相匹配。</span><span class="sxs-lookup"><span data-stu-id="02d0e-150">A change in the version on the client might not be matched by a change in the type stored on the database server.</span></span> <span data-ttu-id="02d0e-151">任何此类更改都会导致另一个类型不匹配，体现在其类型语义不匹配，并且版本差距可能变得明显。</span><span class="sxs-lookup"><span data-stu-id="02d0e-151">Any such change causes another type mismatch where the type semantics might not match and the version gap is likely to become visible.</span></span> <span data-ttu-id="02d0e-152">在后续版本中重构继承层次结构时，会发生更多的复杂问题。</span><span class="sxs-lookup"><span data-stu-id="02d0e-152">Further complications occur as inheritance hierarchies are refactored in successive versions.</span></span>  
  
## <a name="expression-semantics"></a><span data-ttu-id="02d0e-153">表达式语义</span><span class="sxs-lookup"><span data-stu-id="02d0e-153">Expression Semantics</span></span>  
 <span data-ttu-id="02d0e-154">除了 CLR 和数据库类型之间配对的不匹配之外，表达式增加了不匹配的复杂性。</span><span class="sxs-lookup"><span data-stu-id="02d0e-154">In addition to the pairwise mismatch between CLR and database types, expressions add complexity to the mismatch.</span></span> <span data-ttu-id="02d0e-155">必须考虑运算符语义、函数语义、隐式类型转换和优先级规则方面的不匹配。</span><span class="sxs-lookup"><span data-stu-id="02d0e-155">Mismatches in operator semantics, function semantics, implicit type conversion, and precedence rules must be considered.</span></span>  
  
 <span data-ttu-id="02d0e-156">以下小节演示了表面相似的表达式之间的不匹配。</span><span class="sxs-lookup"><span data-stu-id="02d0e-156">The following subsections illustrate the mismatch between apparently similar expressions.</span></span> <span data-ttu-id="02d0e-157">可以生成在语义上与给定的 CLR 表达式等效的 SQL 表达式。</span><span class="sxs-lookup"><span data-stu-id="02d0e-157">It might be possible to generate SQL expressions that are semantically equivalent to a given CLR expression.</span></span> <span data-ttu-id="02d0e-158">但是对于 CLR 用户来说，表面相似的表达式之间的语义差异是否明显，这一点并不明确。因此，是否需要进行实现语义等效方面的更改也不明确。</span><span class="sxs-lookup"><span data-stu-id="02d0e-158">However, it is not clear whether the semantic differences between apparently similar expressions are evident to a CLR user, and therefore whether the changes that are required for semantic equivalence are intended or not.</span></span> <span data-ttu-id="02d0e-159">要计算出表达式的一组值时，这个问题尤为严重。</span><span class="sxs-lookup"><span data-stu-id="02d0e-159">This is an especially critical issue when an expression is evaluated for a set of values.</span></span> <span data-ttu-id="02d0e-160">差异的明显程度可能取决于数据，因此很难在编码和调试过程中确定。</span><span class="sxs-lookup"><span data-stu-id="02d0e-160">The visibility of the difference might depend on data- and be hard to identify during coding and debugging.</span></span>  
  
### <a name="null-semantics"></a><span data-ttu-id="02d0e-161">Null 语义</span><span class="sxs-lookup"><span data-stu-id="02d0e-161">Null Semantics</span></span>  
 <span data-ttu-id="02d0e-162">SQL 表达式为布尔表达式提供了三值逻辑，</span><span class="sxs-lookup"><span data-stu-id="02d0e-162">SQL expressions provide three-valued logic for Boolean expressions.</span></span> <span data-ttu-id="02d0e-163">结果可以是 true、false 或 null。</span><span class="sxs-lookup"><span data-stu-id="02d0e-163">The result can be true, false, or null.</span></span> <span data-ttu-id="02d0e-164">相比之下，CLR 为涉及 null 值的比较指定了两值布尔结果。</span><span class="sxs-lookup"><span data-stu-id="02d0e-164">By contrast, CLR specifies two-valued Boolean result for comparisons involving null values.</span></span> <span data-ttu-id="02d0e-165">考虑下列代码：</span><span class="sxs-lookup"><span data-stu-id="02d0e-165">Consider the following code:</span></span>  
  
 [!code-csharp[DLinqMismatch#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#2)]
 [!code-vb[DLinqMismatch#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#2)]  
  
```  
-- Assume col1 and col2 are integer columns with null values.   
-- Assume that ANSI null behavior has not been explicitly  
--    turned off.  
Select …  
From …  
Where col1 = col2  
-- Evaluates to null, not true and the corresponding row is not  
--     selected.  
-- To obtain matching behavior (i -> col1, j -> col2) change  
--     the query to the following:  
Select …  
From …  
Where  
    col1 = col2   
or (col1 is null and col2 is null)  
-- (Visual Basic 'Nothing'.)  
```  
  
 <span data-ttu-id="02d0e-166">出现存在两个值的结果时会发生类似问题。</span><span class="sxs-lookup"><span data-stu-id="02d0e-166">A similar problem occurs with the assumption about two-valued results.</span></span>  
  
 [!code-csharp[DLinqMismatch#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#3)]
 [!code-vb[DLinqMismatch#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#3)]  
  
```  
-- Assume col1 and col2 are nullable columns.  
-- Assume that ANSI null behavior has not been explicitly  
--     turned off.  
Select …  
From …  
Where  
    col1 = col2        
or col1 != col2  
-- Visual Basic: col1 <> col2.  
  
-- Excludes the case where the boolean expression evaluates  
--     to null. Therefore the where clause does not always  
--     evaluate to true.  
```  
  
 <span data-ttu-id="02d0e-167">在上例中，在生成 SQL 方面可能得出等效的行为，但是转换可能不会准确地反映您的意图。</span><span class="sxs-lookup"><span data-stu-id="02d0e-167">In the previous case, you can get equivalent behavior in generating SQL, but the translation might not accurately reflect your intention.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="02d0e-168">不会施加C#`null`或 Visual Basic`nothing`在 SQL 上的比较语义。</span><span class="sxs-lookup"><span data-stu-id="02d0e-168">does not impose C# `null` or Visual Basic `nothing` comparison semantics on SQL.</span></span> <span data-ttu-id="02d0e-169">比较运算符在语法上被转换为其 SQL 等效项。</span><span class="sxs-lookup"><span data-stu-id="02d0e-169">Comparison operators are syntactically translated to their SQL equivalents.</span></span> <span data-ttu-id="02d0e-170">反映 SQL 语义的语义是由服务器或连接设置定义的。</span><span class="sxs-lookup"><span data-stu-id="02d0e-170">The semantics reflect SQL semantics as defined by server or connection settings.</span></span> <span data-ttu-id="02d0e-171">在默认的 SQL Server 设置下，两个 null 值被视为不相等（尽管您可以更改设置以改变语义）。</span><span class="sxs-lookup"><span data-stu-id="02d0e-171">Two null values are considered unequal under default SQL Server settings (although you can change the settings to change the semantics).</span></span> <span data-ttu-id="02d0e-172">无论如何，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 在查询转换中不会考虑服务器设置。</span><span class="sxs-lookup"><span data-stu-id="02d0e-172">Regardless, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not consider server settings in query translation.</span></span>  
  
 <span data-ttu-id="02d0e-173">带有文本 `null` (`nothing`) 的比较被转换为相应的 SQL 版本（`is null` 或 `is not null`）。</span><span class="sxs-lookup"><span data-stu-id="02d0e-173">A comparison with the literal `null` (`nothing`) is translated to the appropriate SQL version (`is null` or `is not null`).</span></span>  
  
 <span data-ttu-id="02d0e-174">排序规则中的 `null` (`nothing`) 值是由 SQL Server 定义的；[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 不会更改排序规则。</span><span class="sxs-lookup"><span data-stu-id="02d0e-174">The value of `null` (`nothing`) in collation is defined by SQL Server; [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not change the collation.</span></span>  
  
### <a name="type-conversion-and-promotion"></a><span data-ttu-id="02d0e-175">类型转换和提升</span><span class="sxs-lookup"><span data-stu-id="02d0e-175">Type Conversion and Promotion</span></span>  
 <span data-ttu-id="02d0e-176">SQL 支持在表达式中使用一组丰富的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="02d0e-176">SQL supports a rich set of implicit conversions in expressions.</span></span> <span data-ttu-id="02d0e-177">C# 中的类似表达式则需要显式强制转换。</span><span class="sxs-lookup"><span data-stu-id="02d0e-177">Similar expressions in C# would require an explicit cast.</span></span> <span data-ttu-id="02d0e-178">例如：</span><span class="sxs-lookup"><span data-stu-id="02d0e-178">For example:</span></span>  
  
-   <span data-ttu-id="02d0e-179">`Nvarchar` 和 `DateTime` 类型在 SQL 中可以不经过任何显式强制转换进行比较，而在 C# 中则需要显式转换。</span><span class="sxs-lookup"><span data-stu-id="02d0e-179">`Nvarchar` and `DateTime` types can be compared in SQL without any explicit casts; C# requires explicit conversion.</span></span>  
  
-   <span data-ttu-id="02d0e-180">`Decimal` 在 SQL 中隐式转换为 `DateTime`。</span><span class="sxs-lookup"><span data-stu-id="02d0e-180">`Decimal` is implicitly converted to `DateTime` in SQL.</span></span> <span data-ttu-id="02d0e-181">C# 不允许使用隐式转换。</span><span class="sxs-lookup"><span data-stu-id="02d0e-181">C# does not allow for an implicit conversion.</span></span>  
  
 <span data-ttu-id="02d0e-182">同样，由于基础类型集不同，Transact-SQL 中的类型优先级与 C# 中的类型优先级不同。</span><span class="sxs-lookup"><span data-stu-id="02d0e-182">Likewise, type precedence in Transact-SQL differs from type precedence in C# because the underlying set of types is different.</span></span> <span data-ttu-id="02d0e-183">实际上，在优先级列表之间没有明确的子集/父集关系。</span><span class="sxs-lookup"><span data-stu-id="02d0e-183">In fact, there is no clear subset/superset relationship between the precedence lists.</span></span> <span data-ttu-id="02d0e-184">例如，将 `nvarchar` 和 `varchar` 进行比较会导致 `varchar` 表达式隐式转换为 `nvarchar`。</span><span class="sxs-lookup"><span data-stu-id="02d0e-184">For example, comparing an `nvarchar` with a `varchar` causes the implicit conversion of the `varchar` expression to `nvarchar`.</span></span> <span data-ttu-id="02d0e-185">CLR 不提供等效的提升。</span><span class="sxs-lookup"><span data-stu-id="02d0e-185">The CLR provides no equivalent promotion.</span></span>  
  
 <span data-ttu-id="02d0e-186">在简单的情况下，这些差异会导致 CLR 表达式包含对于相应的 SQL 表达式来说多余的强制转换。</span><span class="sxs-lookup"><span data-stu-id="02d0e-186">In simple cases, these differences cause CLR expressions with casts to be redundant for a corresponding SQL expression.</span></span> <span data-ttu-id="02d0e-187">更重要的是，SQL 表达式的中间结果可能会隐式提升到在 C# 中没有精确对应项的类型，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="02d0e-187">More importantly, the intermediate results of a SQL expression might be implicitly promoted to a type that has no accurate counterpart in C#, and vice versa.</span></span> <span data-ttu-id="02d0e-188">总之，此类表达式的测试、调试和验证会给用户增加大量的负担。</span><span class="sxs-lookup"><span data-stu-id="02d0e-188">Overall, the testing, debugging, and validation of such expressions adds significant burden on the user.</span></span>  
  
### <a name="collation"></a><span data-ttu-id="02d0e-189">排序规则</span><span class="sxs-lookup"><span data-stu-id="02d0e-189">Collation</span></span>  
 <span data-ttu-id="02d0e-190">Transact-SQL 支持作为字符串类型的批注的显式排序规则。</span><span class="sxs-lookup"><span data-stu-id="02d0e-190">Transact-SQL supports explicit collations as annotations to character string types.</span></span> <span data-ttu-id="02d0e-191">这些排序规则决定了某些比较的有效性。</span><span class="sxs-lookup"><span data-stu-id="02d0e-191">These collations determine the validity of certain comparisons.</span></span> <span data-ttu-id="02d0e-192">例如，比较两个使用不同显式排序规则的列将会出错。</span><span class="sxs-lookup"><span data-stu-id="02d0e-192">For example, comparing two columns with different explicit collations is an error.</span></span> <span data-ttu-id="02d0e-193">使用大大简化的 CTS 字符串类型不会导致这种错误。</span><span class="sxs-lookup"><span data-stu-id="02d0e-193">The use of much simplified CTS string type does not cause such errors.</span></span> <span data-ttu-id="02d0e-194">请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="02d0e-194">Consider the following example:</span></span>  
  
```  
create table T2 (  
    Col1 nvarchar(10),  
    Col2      nvarchar(10) collate Latin_general_ci_as  
)  
```  
  
 [!code-csharp[DLinqMismatch#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#4)]
 [!code-vb[DLinqMismatch#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#4)]  
  
```  
Select …  
From …  
Where Col1 = Col2  
-- Error, collation conflict.  
```  
  
 <span data-ttu-id="02d0e-195">实际上，排序规则子句会创建*受限类型*不可替换。</span><span class="sxs-lookup"><span data-stu-id="02d0e-195">In effect, the collation subclause creates a *restricted type* that is not substitutable.</span></span>  
  
 <span data-ttu-id="02d0e-196">同样，各个类型系统的排序顺序会有明显差异。</span><span class="sxs-lookup"><span data-stu-id="02d0e-196">Similarly, the sort order can be significantly different across the type systems.</span></span> <span data-ttu-id="02d0e-197">这种差异会影响到结果排序。</span><span class="sxs-lookup"><span data-stu-id="02d0e-197">This difference affects the sorting of results.</span></span> <span data-ttu-id="02d0e-198"><xref:System.Guid> 对全部 16 个字节按字典顺序排序 (`IComparable()`)，而 T-SQL 按下面的顺序比较 GUID：node(10-15)、clock-seq(8-9)、time-high(6-7)、time-mid(4-5)、time-low(0-3)。</span><span class="sxs-lookup"><span data-stu-id="02d0e-198"><xref:System.Guid> is sorted on all 16 bytes by lexicographic order (`IComparable()`), whereas T-SQL compares GUIDs in the following order: node(10-15), clock-seq(8-9), time-high(6-7), time-mid(4-5), time-low(0-3).</span></span> <span data-ttu-id="02d0e-199">当 NT 生成的 GUID 具有类似的八位字节顺序时，此排序在 SQL 7.0 中完成。</span><span class="sxs-lookup"><span data-stu-id="02d0e-199">This ordering was done in SQL 7.0 when NT-generated GUIDs had such an octet order.</span></span> <span data-ttu-id="02d0e-200">该方法确保在同一节点群集上生成的 GUID 按时间戳的顺序集合。</span><span class="sxs-lookup"><span data-stu-id="02d0e-200">The approach ensured that GUIDs generated at the same node cluster came together in sequential order according to timestamp.</span></span> <span data-ttu-id="02d0e-201">该方法还可用于生成索引（插入改为追加而不是随机 IO）。</span><span class="sxs-lookup"><span data-stu-id="02d0e-201">The approach was also useful for building indexes (inserts become appends instead of random IOs).</span></span> <span data-ttu-id="02d0e-202">出于保密考虑，该顺序稍后在 Windows 中加密，但 SQL 必须维护兼容性。</span><span class="sxs-lookup"><span data-stu-id="02d0e-202">The order was scrambled later in Windows because of privacy concerns, but SQL must maintain compatibility.</span></span> <span data-ttu-id="02d0e-203">一种解决方法是使用<xref:System.Data.SqlTypes.SqlGuid>而不是<xref:System.Guid>。</span><span class="sxs-lookup"><span data-stu-id="02d0e-203">A workaround is to use <xref:System.Data.SqlTypes.SqlGuid> instead of <xref:System.Guid>.</span></span>  
  
### <a name="operator-and-function-differences"></a><span data-ttu-id="02d0e-204">运算符和函数差异</span><span class="sxs-lookup"><span data-stu-id="02d0e-204">Operator and Function Differences</span></span>  
 <span data-ttu-id="02d0e-205">本质上可比较的运算符和函数在语义上稍有不同。</span><span class="sxs-lookup"><span data-stu-id="02d0e-205">Operators and functions that are essentially comparable have subtly different semantics.</span></span> <span data-ttu-id="02d0e-206">例如：</span><span class="sxs-lookup"><span data-stu-id="02d0e-206">For example:</span></span>  
  
-   <span data-ttu-id="02d0e-207">C# 基于逻辑运算符 `&&` 和 `||` 的操作数的词法顺序指定短路语义。</span><span class="sxs-lookup"><span data-stu-id="02d0e-207">C# specifies short circuit semantics based on lexical order of operands for logical operators `&&` and `||`.</span></span> <span data-ttu-id="02d0e-208">另一方面，SQL 面向基于集的查询，因此在决定执行顺序方面为优化器提供了更大的自由度。</span><span class="sxs-lookup"><span data-stu-id="02d0e-208">SQL on the other hand is targeted for set-based queries and therefore provides more freedom for the optimizer to decide the order of execution.</span></span> <span data-ttu-id="02d0e-209">由此产生的一些连带影响包括：</span><span class="sxs-lookup"><span data-stu-id="02d0e-209">Some of the implications include the following:</span></span>  
  
    -   <span data-ttu-id="02d0e-210">在语义上等效的转换将需要"`CASE` ...</span><span class="sxs-lookup"><span data-stu-id="02d0e-210">Semantically equivalent translation would require "`CASE` …</span></span> <span data-ttu-id="02d0e-211">`WHEN` …</span><span class="sxs-lookup"><span data-stu-id="02d0e-211">`WHEN` …</span></span> <span data-ttu-id="02d0e-212">`THEN`"构造，以避免对操作数执行重新排序。</span><span class="sxs-lookup"><span data-stu-id="02d0e-212">`THEN`" construct in SQL to avoid reordering of operand execution.</span></span>  
  
    -   <span data-ttu-id="02d0e-213">松散转换为`AND` / `OR`运算符可能导致错误，如果C#表达式依赖于计算基于第一个操作数的计算结果的第二个操作数。</span><span class="sxs-lookup"><span data-stu-id="02d0e-213">A loose translation to `AND`/`OR` operators could cause unexpected errors if the C# expression relies on evaluation the second operand being based on the result of the evaluation of the first operand.</span></span>  
  
-   <span data-ttu-id="02d0e-214">`Round()` 函数在 [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] 和 T-SQL 中具有不同的语义。</span><span class="sxs-lookup"><span data-stu-id="02d0e-214">`Round()` function has different semantics in [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] and in T-SQL.</span></span>  
  
-   <span data-ttu-id="02d0e-215">字符串的起始索引在 CLR 中是 0，而在 SQL 中是 1。</span><span class="sxs-lookup"><span data-stu-id="02d0e-215">Starting index for strings is 0 in the CLR but 1 in SQL.</span></span> <span data-ttu-id="02d0e-216">因此，任何具有索引的函数都需要进行索引转换。</span><span class="sxs-lookup"><span data-stu-id="02d0e-216">Therefore, any function that has index needs index translation.</span></span>  
  
-   <span data-ttu-id="02d0e-217">CLR 支持用于浮点数的模数 (‘%’) 运算符，但 SQL 不支持。</span><span class="sxs-lookup"><span data-stu-id="02d0e-217">The CLR supports modulus (‘%’) operator for floating point numbers but SQL does not.</span></span>  
  
-   <span data-ttu-id="02d0e-218">`Like` 运算符基于隐式转换有效地获取自动重载。</span><span class="sxs-lookup"><span data-stu-id="02d0e-218">The `Like` operator effectively acquires automatic overloads based on implicit conversions.</span></span> <span data-ttu-id="02d0e-219">虽然 `Like` 运算符被定义为对字符串类型发生作用，但如果对数字类型或 `DateTime` 类型进行隐式转换，则 `Like` 也可以用于这些非字符串类型。</span><span class="sxs-lookup"><span data-stu-id="02d0e-219">Although the `Like` operator is defined to operate on character string types, implicit conversion from numeric types or `DateTime` types allows for those non-string types to be used with `Like` just as well.</span></span> <span data-ttu-id="02d0e-220">在 CTS 中，不存在相应的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="02d0e-220">In CTS, comparable implicit conversions do not exist.</span></span> <span data-ttu-id="02d0e-221">因此，需要其他重载。</span><span class="sxs-lookup"><span data-stu-id="02d0e-221">Therefore, additional overloads are needed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="02d0e-222">此 `Like` 运算符行为仅适用于 C#；Visual Basic `Like` 关键字保持不变。</span><span class="sxs-lookup"><span data-stu-id="02d0e-222">This `Like` operator behavior applies to C# only; the Visual Basic `Like` keyword is unchanged.</span></span>  
  
-   <span data-ttu-id="02d0e-223">在 SQL 中始终检查溢出，但尚未显式指定在C#(不在 Visual Basic 中) 以避免头尾回绕。</span><span class="sxs-lookup"><span data-stu-id="02d0e-223">Overflow is always checked in SQL but it has to be explicitly specified in C# (not in Visual Basic) to avoid wraparound.</span></span> <span data-ttu-id="02d0e-224">假设有整数列 C1、C2 和 C3，并且 C1+C2 存储在 C3 中 (Update T Set C3 = C1 + C2)。</span><span class="sxs-lookup"><span data-stu-id="02d0e-224">Given integer columns C1, C2 and C3, if C1+C2 is stored in C3 (Update T Set C3 = C1 + C2).</span></span>  
  
    ```  
    create table T3 (  
        Col1      integer,  
        Col2      integer  
    )  
    insert into T3 (col1, col2) values (2147483647, 5)  
    -- Valid values: max integer value and 5.  
    select * from T3 where col1 + col2 < 0  
    -- Produces arithmetic overflow error.  
    ```  
  
 [!code-csharp[DLinqMismatch#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#5)]
 [!code-vb[DLinqMismatch#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#5)]  
  
-   <span data-ttu-id="02d0e-225">SQL 执行对称算法四舍五入，而 [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] 使用“四舍六入五取偶”。</span><span class="sxs-lookup"><span data-stu-id="02d0e-225">SQL performs symmetric arithmetic rounding while [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] uses banker’s rounding.</span></span> <span data-ttu-id="02d0e-226">有关更多信息，请参见知识库文章 196652。</span><span class="sxs-lookup"><span data-stu-id="02d0e-226">See Knowledgebase article 196652 for additional details.</span></span>  
  
-   <span data-ttu-id="02d0e-227">默认情况下，对于通用区域设置，字符串比较在 SQL 中不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="02d0e-227">By default, for common locales, character-string comparisons are case-insensitive in SQL.</span></span> <span data-ttu-id="02d0e-228">在 Visual Basic 和 C# 中，它们区分大小写。</span><span class="sxs-lookup"><span data-stu-id="02d0e-228">In Visual Basic and in C#, they are case-sensitive.</span></span> <span data-ttu-id="02d0e-229">例如， `s == "Food"` (`s = "Food"`在 Visual Basic 中) 和`s == "Food"`会产生不同的结果，如果`s`是`food`。</span><span class="sxs-lookup"><span data-stu-id="02d0e-229">For example, `s == "Food"` (`s = "Food"` in Visual Basic) and `s == "Food"` can yield different results if `s` is `food`.</span></span>  
  
    ```  
    -- Assume default US-English locale (case insensitive).  
    create table T4 (  
        Col1      nvarchar (256)  
    )  
    insert into T4 values (‘Food’)   
    insert into T4 values (‘FOOD’)  
    select * from T4 where Col1 = ‘food’  
    -- Both the rows are returned because of case-insensitive matching.  
    ```  
  
 [!code-csharp[DLinqMismatch#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#6)]
 [!code-vb[DLinqMismatch#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#6)]  
  
-   <span data-ttu-id="02d0e-230">在语义上，SQL 中适用于固定长度字符类型参数的运算符/函数与适用于 CLR <xref:System.String?displayProperty=nameWithType> 的相同运算符/函数有明显不同。</span><span class="sxs-lookup"><span data-stu-id="02d0e-230">Operators/ functions applied to fixed length character type arguments in SQL have significantly different semantics than the same operators/functions applied to the CLR <xref:System.String?displayProperty=nameWithType>.</span></span> <span data-ttu-id="02d0e-231">这也可以看作是关于类型的小节中讨论的缺少对应项问题的延伸。</span><span class="sxs-lookup"><span data-stu-id="02d0e-231">This could also be viewed as an extension of the missing counterpart problem discussed in the section about types.</span></span>  
  
    ```  
    create table T4 (  
        Col1      nchar(4)  
    )  
    Insert into T5(Col1) values ('21');  
    Insert into T5(Col1) values ('1021');  
    Select * from T5 where Col1 like '%1'  
    -- Only the second row with Col1 = '1021' is returned.  
    -- Not the first row!  
    ```  
  
     [!code-csharp[DLinqMismatch#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#7)]
     [!code-vb[DLinqMismatch#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#7)]  
  
     <span data-ttu-id="02d0e-232">字符串串联存在类似的问题。</span><span class="sxs-lookup"><span data-stu-id="02d0e-232">A similar problem occurs with string concatenation.</span></span>  
  
    ```  
    create table T6 (  
        Col1      nchar(4)  
        Col2       nchar(4)  
    )  
    Insert into T6 values ('a', 'b');  
    Select Col1+Col2 from T6  
    -- Returns concatenation of padded strings "a   b   " and not "ab".  
    ```  
  
 <span data-ttu-id="02d0e-233">总之，可能需要对 CLR 表达式进行复杂转换，同时可能需要附加的运算符/函数来公开 SQL 功能。</span><span class="sxs-lookup"><span data-stu-id="02d0e-233">In summary, a convoluted translation might be required for CLR expressions and additional operators/functions may be necessary to expose SQL functionality.</span></span>  
  
### <a name="type-casting"></a><span data-ttu-id="02d0e-234">类型强制转换</span><span class="sxs-lookup"><span data-stu-id="02d0e-234">Type Casting</span></span>  
 <span data-ttu-id="02d0e-235">在 C# 和 SQL 中，用户可以使用显式类型强制转换（`Cast` 和 `Convert`）来重写默认的表达式语义。</span><span class="sxs-lookup"><span data-stu-id="02d0e-235">In C# and in SQL, users can override the default semantics of expressions by using explicit type casts (`Cast` and `Convert`).</span></span> <span data-ttu-id="02d0e-236">但是，跨类型系统边界公开此功能将带来一个难题。</span><span class="sxs-lookup"><span data-stu-id="02d0e-236">However, exposing this capability across the type system boundary poses a dilemma.</span></span> <span data-ttu-id="02d0e-237">提供所需语义的 SQL 强制转换不能方便地转换为相应的 C# 强制转换。</span><span class="sxs-lookup"><span data-stu-id="02d0e-237">A SQL cast that provides the desired semantics cannot be easily translated to a corresponding C# cast.</span></span> <span data-ttu-id="02d0e-238">另一方面，由于类型不匹配、缺少对应项和类型优先级层次结构不同，C# 强制转换无法直接转换为等效的 SQL 强制转换。</span><span class="sxs-lookup"><span data-stu-id="02d0e-238">On the other hand, a C# cast cannot be directly translated into an equivalent SQL cast because of type mismatches, missing counterparts, and different type precedence hierarchies.</span></span> <span data-ttu-id="02d0e-239">需要在出现类型系统不匹配与损失表达式强大功能之间进行权衡。</span><span class="sxs-lookup"><span data-stu-id="02d0e-239">There is a trade-off between exposing the type system mismatch and losing significant power of expression.</span></span>  
  
 <span data-ttu-id="02d0e-240">在其他情况下，可能不需要对任何一种验证表达式的情况使用类型强制转换，但可能需要使用它来确保非默认映射正确地应用到表达式。</span><span class="sxs-lookup"><span data-stu-id="02d0e-240">In other cases, type casting might not be needed in either domain for validation of an expression but might be required to make sure that a non-default mapping is correctly applied to the expression.</span></span>  
  
```  
-- Example from "Non-default Mapping" section extended  
create table T5 (  
    Col1      nvarchar(10),  
    Col2      nvarchar(10)  
)  
Insert into T5(col1, col2) values (‘3’, ‘2’);  
```  
  
 [!code-csharp[DLinqMismatch#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#8)]
 [!code-vb[DLinqMismatch#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#8)]  
  
```  
Select *  
From T5  
Where Col1 + Col2 > 4     
-- "Col1 + Col2" expr evaluates to '32'   
```  
  
## <a name="performance-issues"></a><span data-ttu-id="02d0e-241">性能问题</span><span class="sxs-lookup"><span data-stu-id="02d0e-241">Performance Issues</span></span>  
 <span data-ttu-id="02d0e-242">记帐的某些 SQL Server-CLR 类型的差异可能会导致性能降低的 CLR 和 SQL Server 之间切换的类型系统时。</span><span class="sxs-lookup"><span data-stu-id="02d0e-242">Accounting for some SQL Server-CLR type differences may result in a decrease in performance when crossing between the CLR and SQL Server type systems.</span></span> <span data-ttu-id="02d0e-243">影响性能的方案示例包括：</span><span class="sxs-lookup"><span data-stu-id="02d0e-243">Examples of scenarios impacting performance include the following:</span></span>  
  
-   <span data-ttu-id="02d0e-244">强制对逻辑“与”/逻辑“或”运算符的计算顺序</span><span class="sxs-lookup"><span data-stu-id="02d0e-244">Forced order of evaluation for logical and/or operators</span></span>  
  
-   <span data-ttu-id="02d0e-245">生成 SQL 以对谓词计算执行排序会限制 SQL 优化器的功能。</span><span class="sxs-lookup"><span data-stu-id="02d0e-245">Generating SQL to enforce order of predicate evaluation restricts the SQL optimizer’s ability.</span></span>  
  
-   <span data-ttu-id="02d0e-246">类型转换（无论是由 CLR 编译器引入还是由对象关系查询实现引入）可能会限制索引的使用。</span><span class="sxs-lookup"><span data-stu-id="02d0e-246">Type conversions, whether introduced by a CLR compiler or by an Object-Relational query implementation, may curtail index usage.</span></span>  
  
     <span data-ttu-id="02d0e-247">例如，应用于对象的</span><span class="sxs-lookup"><span data-stu-id="02d0e-247">For example,</span></span>  
  
    ```  
    -- Table DDL  
    create table T5 (  
        Col1      varchar(100)  
    )  
    ```  
  
     [!code-csharp[DLinqMismatch#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#9)]
     [!code-vb[DLinqMismatch#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#9)]  
  
     <span data-ttu-id="02d0e-248">请考虑表达式 `(s = SOME_STRING_CONSTANT)` 的转换。</span><span class="sxs-lookup"><span data-stu-id="02d0e-248">Consider the translation of expression `(s = SOME_STRING_CONSTANT)`.</span></span>  
  
    ```  
    -- Corresponding part of SQL where clause  
    Where …  
    Col1 = SOME_STRING_CONSTANT  
    -- This expression is of the form <varchar> = <nvarchar>.  
    -- Hence SQL introduces a conversion from varchar to nvarchar,  
    --     resulting in  
    Where …  
    Convert(nvarchar(100), Col1) = SOME_STRING_CONSTANT  
    -- Cannot use the index for column Col1 for some implementations.  
    ```  
  
 <span data-ttu-id="02d0e-249">除了语义差异，考虑在 SQL Server 与 CLR 类型系统之间切换时对性能的影响非常重要。</span><span class="sxs-lookup"><span data-stu-id="02d0e-249">In addition to semantic differences, it is important to consider impacts to performance when crossing between the SQL Server and CLR type systems.</span></span> <span data-ttu-id="02d0e-250">对于大型数据集，此类性能问题可能决定应用程序是否可部署。</span><span class="sxs-lookup"><span data-stu-id="02d0e-250">For large data sets, such performance issues can determine whether an application is deployable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d0e-251">请参阅</span><span class="sxs-lookup"><span data-stu-id="02d0e-251">See also</span></span>

- [<span data-ttu-id="02d0e-252">背景信息</span><span class="sxs-lookup"><span data-stu-id="02d0e-252">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
