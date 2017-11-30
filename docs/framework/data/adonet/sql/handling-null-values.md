---
title: "处理 Null 值"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: f18b288f-b265-4bbe-957f-c6833c0645ef
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1f29cbd51c036ecc15306f67fdd32dee6a4f1b68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="handling-null-values"></a><span data-ttu-id="4a465-102">处理 Null 值</span><span class="sxs-lookup"><span data-stu-id="4a465-102">Handling Null Values</span></span>
<span data-ttu-id="4a465-103">在列中的值未知或缺失时，在关系数据库中使用空值。</span><span class="sxs-lookup"><span data-stu-id="4a465-103">A null value in a relational database is used when the value in a column is unknown or missing.</span></span> <span data-ttu-id="4a465-104">空既不是空字符串（对于 character 或 datetime 数据类型），也不是零值（对于 numeric 数据类型）。</span><span class="sxs-lookup"><span data-stu-id="4a465-104">A null is neither an empty string (for character or datetime data types) nor a zero value (for numeric data types).</span></span> <span data-ttu-id="4a465-105">ANSI SQL-92 规范规定，空必须对于所有数据类型均相同，以便以一致的方式处理所有空。</span><span class="sxs-lookup"><span data-stu-id="4a465-105">The ANSI SQL-92 specification states that a null must be the same for all data types, so that all nulls are handled consistently.</span></span> <span data-ttu-id="4a465-106"><xref:System.Data.SqlTypes> 命名空间通过实现 <xref:System.Data.SqlTypes.INullable> 接口，提供空语义。</span><span class="sxs-lookup"><span data-stu-id="4a465-106">The <xref:System.Data.SqlTypes> namespace provides null semantics by implementing the <xref:System.Data.SqlTypes.INullable> interface.</span></span> <span data-ttu-id="4a465-107"><xref:System.Data.SqlTypes> 中的每种数据类型都有其自己的 `IsNull` 属性和可分配给该数据类型的实例的 `Null` 值。</span><span class="sxs-lookup"><span data-stu-id="4a465-107">Each of the data types in <xref:System.Data.SqlTypes> has its own `IsNull` property and a `Null` value that can be assigned to an instance of that data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a465-108">.NET Framework 2.0 版引入了对可以为 null 的类型的支持，这允许程序员扩展值类型以表示基础类型的所有值。</span><span class="sxs-lookup"><span data-stu-id="4a465-108">The .NET Framework version 2.0 introduced support for nullable types, which allow programmers to extend a value type to represent all values of the underlying type.</span></span> <span data-ttu-id="4a465-109">这些 CLR 可以为 null 的类型表示 <xref:System.Nullable> 结构的一个实例。</span><span class="sxs-lookup"><span data-stu-id="4a465-109">These CLR nullable types represent an instance of the <xref:System.Nullable> structure.</span></span> <span data-ttu-id="4a465-110">当值类型为装箱和未装箱，从而增强与对象类型的兼容性时，这个功能特别有用。</span><span class="sxs-lookup"><span data-stu-id="4a465-110">This capability is especially useful when value types are boxed and unboxed, providing enhanced compatibility with object types.</span></span> <span data-ttu-id="4a465-111">CLR 可以为 null 的类型不用于存储数据库 null 值，因为 ANSI SQL null 值的行为与 `null` 引用（或 Visual Basic 中的 `Nothing`）不同。</span><span class="sxs-lookup"><span data-stu-id="4a465-111">CLR nullable types are not intended for storage of database nulls because an ANSI SQL null does not behave the same way as a `null` reference (or `Nothing` in Visual Basic).</span></span> <span data-ttu-id="4a465-112">为了使用数据库 ANSI SQL null 值，请使用 <xref:System.Data.SqlTypes> null 值而不使用 <xref:System.Nullable>。</span><span class="sxs-lookup"><span data-stu-id="4a465-112">For working with database ANSI SQL null values, use <xref:System.Data.SqlTypes> nulls rather than <xref:System.Nullable>.</span></span> <span data-ttu-id="4a465-113">有关详细信息使用 CLR 可以为 null 类型在 Visual Basic 中的，请参阅[可以为 Null 的值类型](~/docs/visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)，和有关 C#，请参阅[使用可以为 Null 类型](~/docs/csharp/programming-guide/nullable-types/using-nullable-types.md)。</span><span class="sxs-lookup"><span data-stu-id="4a465-113">For more information on working with CLR nullable types in Visual Basic see [Nullable Value Types](~/docs/visual-basic/programming-guide/language-features/data-types/nullable-value-types.md), and for C# see [Using Nullable Types](~/docs/csharp/programming-guide/nullable-types/using-nullable-types.md).</span></span>  
  
## <a name="nulls-and-three-valued-logic"></a><span data-ttu-id="4a465-114">空和三值逻辑</span><span class="sxs-lookup"><span data-stu-id="4a465-114">Nulls and Three-Valued Logic</span></span>  
 <span data-ttu-id="4a465-115">在列定义中允许空值将三值逻辑引入您的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4a465-115">Allowing null values in column definitions introduces three-valued logic into your application.</span></span> <span data-ttu-id="4a465-116">可以将比较计算为以下三个条件之一：</span><span class="sxs-lookup"><span data-stu-id="4a465-116">A comparison can evaluate to one of three conditions:</span></span>  
  
-   <span data-ttu-id="4a465-117">True</span><span class="sxs-lookup"><span data-stu-id="4a465-117">True</span></span>  
  
-   <span data-ttu-id="4a465-118">False</span><span class="sxs-lookup"><span data-stu-id="4a465-118">False</span></span>  
  
-   <span data-ttu-id="4a465-119">未知</span><span class="sxs-lookup"><span data-stu-id="4a465-119">Unknown</span></span>  
  
 <span data-ttu-id="4a465-120">因为空被视作未知，所以，对两个空值进行彼此比较，其结果不被视为相等。</span><span class="sxs-lookup"><span data-stu-id="4a465-120">Because null is considered to be unknown, two null values compared to each other are not considered to be equal.</span></span> <span data-ttu-id="4a465-121">在使用算术运算符的表达式中，如果任何操作数为空，结果也为空。</span><span class="sxs-lookup"><span data-stu-id="4a465-121">In expressions using arithmetic operators, if any of the operands is null, the result is null as well.</span></span>  
  
## <a name="nulls-and-sqlboolean"></a><span data-ttu-id="4a465-122">空和 SqlBoolean</span><span class="sxs-lookup"><span data-stu-id="4a465-122">Nulls and SqlBoolean</span></span>  
 <span data-ttu-id="4a465-123">任意 <xref:System.Data.SqlTypes> 之间的比较都将返回 <xref:System.Data.SqlTypes.SqlBoolean>。</span><span class="sxs-lookup"><span data-stu-id="4a465-123">Comparison between any <xref:System.Data.SqlTypes> will return a <xref:System.Data.SqlTypes.SqlBoolean>.</span></span> <span data-ttu-id="4a465-124">每个 `IsNull` 的 `SqlType` 函数都可返回一个 <xref:System.Data.SqlTypes.SqlBoolean> 并可用于检查 null 值。</span><span class="sxs-lookup"><span data-stu-id="4a465-124">The `IsNull` function for each `SqlType` returns a <xref:System.Data.SqlTypes.SqlBoolean> and can be used to check for null values.</span></span> <span data-ttu-id="4a465-125">下面的真值表显示在存在空值时 AND、OR 和 NOT 这三个运算符的计算方式。</span><span class="sxs-lookup"><span data-stu-id="4a465-125">The following truth tables show how the AND, OR, and NOT operators function in the presence of a null value.</span></span> <span data-ttu-id="4a465-126">（T=true，F=false，U=unknown 或空。）</span><span class="sxs-lookup"><span data-stu-id="4a465-126">(T=true, F=false, and U=unknown, or null.)</span></span>  
  
 <span data-ttu-id="4a465-127">![真值表](../../../../../docs/framework/data/adonet/sql/media/truthtable-bpuedev11.gif "TruthTable_bpuedev11")</span><span class="sxs-lookup"><span data-stu-id="4a465-127">![Truth Table](../../../../../docs/framework/data/adonet/sql/media/truthtable-bpuedev11.gif "TruthTable_bpuedev11")</span></span>  
  
### <a name="understanding-the-ansinulls-option"></a><span data-ttu-id="4a465-128">理解 ANSI_NULLS 选项</span><span class="sxs-lookup"><span data-stu-id="4a465-128">Understanding the ANSI_NULLS Option</span></span>  
 <span data-ttu-id="4a465-129"><xref:System.Data.SqlTypes> 提供与在 SQL Server 中设置 ANSI_NULLS 选项时相同的语义。</span><span class="sxs-lookup"><span data-stu-id="4a465-129"><xref:System.Data.SqlTypes> provides the same semantics as when the ANSI_NULLS option is set on in SQL Server.</span></span> <span data-ttu-id="4a465-130">所有算术运算符 (+、-，*，/，%)，按位运算符 (~、 &、 &#124;)，和大多数函数都返回 null 如果上述任何操作数或参数为 null，但该属性除外`IsNull`。</span><span class="sxs-lookup"><span data-stu-id="4a465-130">All arithmetic operators (+, -, *, /, %), bitwise operators (~, &, &#124;), and most functions return null if any of the operands or arguments is null, except for the property `IsNull`.</span></span>  
  
 <span data-ttu-id="4a465-131">ANSI sql-92 标准不支持*columnName* = NULL 的 WHERE 子句中。</span><span class="sxs-lookup"><span data-stu-id="4a465-131">The ANSI SQL-92 standard does not support *columnName* = NULL in a WHERE clause.</span></span> <span data-ttu-id="4a465-132">在 SQL Server 中，ANSI_NULLS 选项既控制数据库中的默认可空性，也控制对空值的比较计算。</span><span class="sxs-lookup"><span data-stu-id="4a465-132">In SQL Server, the ANSI_NULLS option controls both default nullability in the database and evaluation of comparisons against null values.</span></span> <span data-ttu-id="4a465-133">如果启用 ANSI_NULLS（这是默认设置），则在测试空值时在表达式中必须使用 IS NULL 运算符。</span><span class="sxs-lookup"><span data-stu-id="4a465-133">If ANSI_NULLS is turned on (the default), the IS NULL operator must be used in expressions when testing for null values.</span></span> <span data-ttu-id="4a465-134">例如，在 ANSI_NULLS 为 on 时，以下比较始终生成 unknown：</span><span class="sxs-lookup"><span data-stu-id="4a465-134">For example, the following comparison always yields unknown when ANSI_NULLS is on:</span></span>  
  
```  
colname > NULL  
```  
  
 <span data-ttu-id="4a465-135">与包含空值的变量的比较也生成 unknown：</span><span class="sxs-lookup"><span data-stu-id="4a465-135">Comparison to a variable containing a null value also yields unknown:</span></span>  
  
```  
colname > @MyVariable  
```  
  
 <span data-ttu-id="4a465-136">使用 IS NULL 或 IS NOT NULL 谓词来测试是否有空值。</span><span class="sxs-lookup"><span data-stu-id="4a465-136">Use the IS NULL or IS NOT NULL predicate to test for a null value.</span></span> <span data-ttu-id="4a465-137">这可能会增加 WHERE 子句的复杂性。</span><span class="sxs-lookup"><span data-stu-id="4a465-137">This can add complexity to the WHERE clause.</span></span> <span data-ttu-id="4a465-138">例如，AdventureWorks 客户表中的 TerritoryID 列允许 null 值。</span><span class="sxs-lookup"><span data-stu-id="4a465-138">For example, the TerritoryID column in the AdventureWorks Customer table allows null values.</span></span> <span data-ttu-id="4a465-139">如果 SELECT 语句用于测试是否有空值以及测试其他内容，则它必须包含 IS NULL 谓词：</span><span class="sxs-lookup"><span data-stu-id="4a465-139">If a SELECT statement is to test for null values in addition to others, it must include an IS NULL predicate:</span></span>  
  
```  
SELECT CustomerID, AccountNumber, TerritoryID  
FROM AdventureWorks.Sales.Customer  
WHERE TerritoryID IN (1, 2, 3)  
   OR TerritoryID IS NULL  
```  
  
 <span data-ttu-id="4a465-140">如果在 SQL Server 中将 ANSI_NULLS 设置为 off，则可以创建使用等于运算符来比较空值的表达式。</span><span class="sxs-lookup"><span data-stu-id="4a465-140">If you set ANSI_NULLS off in SQL Server, you can create expressions that use the equality operator to compare to null.</span></span> <span data-ttu-id="4a465-141">但是，您无法阻止不同的连接为该连接设置空选项。</span><span class="sxs-lookup"><span data-stu-id="4a465-141">However, you can't prevent different connections from setting null options for that connection.</span></span> <span data-ttu-id="4a465-142">不管连接的 ANSI_NULLS 设置如何，使用 IS NULL 测试是否有空值始终有效。</span><span class="sxs-lookup"><span data-stu-id="4a465-142">Using IS NULL to test for null values always works, regardless of the ANSI_NULLS settings for a connection.</span></span>  
  
 <span data-ttu-id="4a465-143">不支持在 `DataSet` 中将 ANSI_NULLS 设置为 off，因为前者总是遵守 ANSI SQL-92 标准来处理 <xref:System.Data.SqlTypes> 中的 null 值。</span><span class="sxs-lookup"><span data-stu-id="4a465-143">Setting ANSI_NULLS off is not supported in a `DataSet`, which always follows the ANSI SQL-92 standard for handling null values in <xref:System.Data.SqlTypes>.</span></span>  
  
## <a name="assigning-null-values"></a><span data-ttu-id="4a465-144">赋予 Null 值</span><span class="sxs-lookup"><span data-stu-id="4a465-144">Assigning Null Values</span></span>  
 <span data-ttu-id="4a465-145">空值是特殊的值类型，并且其存储和赋值语义在不同类型系统和存储系统中是不同的。</span><span class="sxs-lookup"><span data-stu-id="4a465-145">Null values are special, and their storage and assignment semantics differ across different type systems and storage systems.</span></span> <span data-ttu-id="4a465-146">`Dataset` 已设计为可与不同的类型和存储系统一起使用。</span><span class="sxs-lookup"><span data-stu-id="4a465-146">A `Dataset` is designed to be used with different type and storage systems.</span></span>  
  
 <span data-ttu-id="4a465-147">本节描述用于在不同类型系统中将空值赋给 <xref:System.Data.DataColumn> 中的 <xref:System.Data.DataRow> 的空语义。</span><span class="sxs-lookup"><span data-stu-id="4a465-147">This section describes the null semantics for assigning null values to a <xref:System.Data.DataColumn> in a <xref:System.Data.DataRow> across the different type systems.</span></span>  
  
 `DBNull.Value`  
 <span data-ttu-id="4a465-148">此赋值对于任何类型的 `DataColumn` 都有效。</span><span class="sxs-lookup"><span data-stu-id="4a465-148">This assignment is valid for a `DataColumn` of any type.</span></span> <span data-ttu-id="4a465-149">如果该类型实现 `INullable`，则会将 `DBNull.Value` 强制为相应强类型的 Null 值。</span><span class="sxs-lookup"><span data-stu-id="4a465-149">If the type implements `INullable`, `DBNull.Value` is coerced into the appropriate strongly typed Null value.</span></span>  
  
 `SqlType.Null`  
 <span data-ttu-id="4a465-150">所有 <xref:System.Data.SqlTypes> 数据类型均实现 `INullable`。</span><span class="sxs-lookup"><span data-stu-id="4a465-150">All <xref:System.Data.SqlTypes> data types implement `INullable`.</span></span> <span data-ttu-id="4a465-151">如果可以使用隐式强制转换运算符将强类型的空值转换为该列的数据类型，则应该进行赋值。</span><span class="sxs-lookup"><span data-stu-id="4a465-151">If the strongly typed null value can be converted into the column's data type using implicit cast operators, the assignment should go through.</span></span> <span data-ttu-id="4a465-152">否则，将引发无效强制转换异常。</span><span class="sxs-lookup"><span data-stu-id="4a465-152">Otherwise an invalid cast exception is thrown.</span></span>  
  
 `null`  
 <span data-ttu-id="4a465-153">如果“null”是给定 `DataColumn` 数据类型的合法值，则会将其强制为相应的 `DbNull.Value` 或与 `Null` 类型关联的 `INullable` (`SqlType.Null`)。</span><span class="sxs-lookup"><span data-stu-id="4a465-153">If 'null' is a legal value for the given `DataColumn` data type, it is coerced into the appropriate `DbNull.Value` or `Null` associated with the `INullable` type (`SqlType.Null`)</span></span>  
  
 `derivedUdt.Null`  
 <span data-ttu-id="4a465-154">对于 UDT 列，null 值始终根据与 `DataColumn` 关联的类型来存储。</span><span class="sxs-lookup"><span data-stu-id="4a465-154">For UDT columns, nulls are always stored based on the type associated with the `DataColumn`.</span></span> <span data-ttu-id="4a465-155">设想这样的情况：与 `DataColumn` 关联的 UDT 不实现 `INullable`，但其子类实现。</span><span class="sxs-lookup"><span data-stu-id="4a465-155">Consider the case of a UDT associated with a `DataColumn` that does not implement `INullable` while its sub-class does.</span></span> <span data-ttu-id="4a465-156">在这种情况下，如果分配了与派生类关联的强类型 null 值，则它被存储为非类型化的 `DbNull.Value`，因为空存储始终与 DataColumn 的数据类型一致。</span><span class="sxs-lookup"><span data-stu-id="4a465-156">In this case, if a strongly typed null value associated with the derived class is assigned, it is stored as an untyped `DbNull.Value`, because null storage is always consistent with the DataColumn's data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a465-157">`Nullable<T>` 中当前不支持 <xref:System.Nullable> 或 `DataSet` 结构。</span><span class="sxs-lookup"><span data-stu-id="4a465-157">The `Nullable<T>` or <xref:System.Nullable> structure is not currently supported in the `DataSet`.</span></span>  
  
### <a name="multiple-column-row-assignment"></a><span data-ttu-id="4a465-158">多列（行）赋值</span><span class="sxs-lookup"><span data-stu-id="4a465-158">Multiple Column (Row) Assignment</span></span>  
 <span data-ttu-id="4a465-159">`DataTable.Add`、`DataTable.LoadDataRow` 或其他接受 <xref:System.Data.DataRow.ItemArray%2A>（映射到行）的 API 会将“null”映射到 DataColumn 的默认值。</span><span class="sxs-lookup"><span data-stu-id="4a465-159">`DataTable.Add`, `DataTable.LoadDataRow`, or other APIs that accept an <xref:System.Data.DataRow.ItemArray%2A> that gets mapped to a row, map 'null' to the DataColumn's default value.</span></span> <span data-ttu-id="4a465-160">如果数组中的对象包含 `DbNull.Value` 或其强类型对应项，则上述规则同样适用。</span><span class="sxs-lookup"><span data-stu-id="4a465-160">If an object in the array contains `DbNull.Value` or its strongly typed counterpart, the same rules as described above are applied.</span></span>  
  
 <span data-ttu-id="4a465-161">此外，下面的规则适用于 `DataRow.["columnName"]` null 赋值的实例：</span><span class="sxs-lookup"><span data-stu-id="4a465-161">In addition, the following rules apply for an instance of `DataRow.["columnName"]` null assignments:</span></span>  
  
1.  <span data-ttu-id="4a465-162">默认值*默认*值是`DbNull.Value`所有但强类型 null 列，它是相应的强类型化 null 值。</span><span class="sxs-lookup"><span data-stu-id="4a465-162">The default *default* value is `DbNull.Value` for all except the strongly typed null columns where it is the appropriate strongly typed null value.</span></span>  
  
2.  <span data-ttu-id="4a465-163">在序列化为 XML 文件（如在“xsi:nil”中）期间，永远不写出空值。</span><span class="sxs-lookup"><span data-stu-id="4a465-163">Null values are never written out during serialization to XML files (as in "xsi:nil").</span></span>  
  
3.  <span data-ttu-id="4a465-164">在序列化为 XML 时始终写出所有非空值，包括默认值。</span><span class="sxs-lookup"><span data-stu-id="4a465-164">All non-null values, including defaults, are always written out while serializing to XML.</span></span> <span data-ttu-id="4a465-165">这与 XSD/XML 语义不同。在 XSD/XML 语义中，空值 (xsi:nil) 是显式的并且默认值是隐式的（如果在 XML 中不提供，则验证分析程序可以从关联的 XSD 架构获取它）。</span><span class="sxs-lookup"><span data-stu-id="4a465-165">This is unlike XSD/XML semantics where a null value (xsi:nil) is explicit and the default value is implicit (if not present in XML, a validating parser can get it from an associated XSD schema).</span></span> <span data-ttu-id="4a465-166">对于 `DataTable`，反过来也成立：空值是隐式的，默认值是显式的。</span><span class="sxs-lookup"><span data-stu-id="4a465-166">The opposite is true for a `DataTable`: a null value is implicit and the default value is explicit.</span></span>  
  
4.  <span data-ttu-id="4a465-167">对于从 XML 输入读取的行的所有缺少的列值，都赋予 NULL。</span><span class="sxs-lookup"><span data-stu-id="4a465-167">All missing column values for rows read from XML input are assigned NULL.</span></span> <span data-ttu-id="4a465-168">使用 <xref:System.Data.DataTable.NewRow%2A> 或类似方法创建的行被赋予 DataColumn 的默认值。</span><span class="sxs-lookup"><span data-stu-id="4a465-168">Rows created using <xref:System.Data.DataTable.NewRow%2A> or similar methods are assigned the DataColumn's default value.</span></span>  
  
5.  <span data-ttu-id="4a465-169">对于 <xref:System.Data.DataRow.IsNull%2A> 和 `true`，`DbNull.Value` 方法均返回 `INullable.Null`。</span><span class="sxs-lookup"><span data-stu-id="4a465-169">The <xref:System.Data.DataRow.IsNull%2A> method returns `true` for both `DbNull.Value` and `INullable.Null`.</span></span>  
  
## <a name="assigning-null-values"></a><span data-ttu-id="4a465-170">赋予 Null 值</span><span class="sxs-lookup"><span data-stu-id="4a465-170">Assigning Null Values</span></span>  
 <span data-ttu-id="4a465-171">任何 <xref:System.Data.SqlTypes> 实例的默认值都是空。</span><span class="sxs-lookup"><span data-stu-id="4a465-171">The default value for any <xref:System.Data.SqlTypes> instance is null.</span></span>  
  
 <span data-ttu-id="4a465-172"><xref:System.Data.SqlTypes> 中的 null 值是类型特定的，不能由单个值（如 `DbNull`）来表示。</span><span class="sxs-lookup"><span data-stu-id="4a465-172">Nulls in <xref:System.Data.SqlTypes> are type-specific and cannot be represented by a single value, such as `DbNull`.</span></span> <span data-ttu-id="4a465-173">使用 `IsNull` 属性可以检查是否有空值。</span><span class="sxs-lookup"><span data-stu-id="4a465-173">Use the `IsNull` property to check for nulls.</span></span>  
  
 <span data-ttu-id="4a465-174">空值可被赋给 <xref:System.Data.DataColumn>，如以下代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="4a465-174">Null values can be assigned to a <xref:System.Data.DataColumn> as shown in the following code example.</span></span> <span data-ttu-id="4a465-175">您可以将空值直接赋给 `SqlTypes` 变量，而不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="4a465-175">You can directly assign null values to `SqlTypes` variables without triggering an exception.</span></span>  
  
### <a name="example"></a><span data-ttu-id="4a465-176">示例</span><span class="sxs-lookup"><span data-stu-id="4a465-176">Example</span></span>  
 <span data-ttu-id="4a465-177">以下代码示例创建一个 <xref:System.Data.DataTable>，它具有两列，分别定义为 <xref:System.Data.SqlTypes.SqlInt32> 和 <xref:System.Data.SqlTypes.SqlString>。</span><span class="sxs-lookup"><span data-stu-id="4a465-177">The following code example creates a <xref:System.Data.DataTable> with two columns defined as <xref:System.Data.SqlTypes.SqlInt32> and <xref:System.Data.SqlTypes.SqlString>.</span></span> <span data-ttu-id="4a465-178">该代码添加一行已知值和一行空值，然后循环访问 <xref:System.Data.DataTable>，将这些值赋给变量并在控制台窗口中显示输出。</span><span class="sxs-lookup"><span data-stu-id="4a465-178">The code adds one row of known values, one row of null values and then iterates through the <xref:System.Data.DataTable>, assigning the values to variables and displaying the output in the console window.</span></span>  
  
 [!code-csharp[DataWorks SqlTypes.IsNull#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.IsNull/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.IsNull#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.IsNull/VB/source.vb#1)]  
  
 <span data-ttu-id="4a465-179">此示例显示以下结果：</span><span class="sxs-lookup"><span data-stu-id="4a465-179">This example displays the following results:</span></span>  
  
```  
isColumnNull=False, ID=123, Description=Side Mirror  
isColumnNull=True, ID=Null, Description=Null  
```  
  
## <a name="comparing-null-values-with-sqltypes-and-clr-types"></a><span data-ttu-id="4a465-180">将空值与 SqlTypes 和 CLR 类型进行比较</span><span class="sxs-lookup"><span data-stu-id="4a465-180">Comparing Null Values with SqlTypes and CLR Types</span></span>  
 <span data-ttu-id="4a465-181">比较 null 值时，必须了解 `Equals` 方法在 <xref:System.Data.SqlTypes> 中计算 null 值的方式与处理 CLR 类型的方式之间的差别。</span><span class="sxs-lookup"><span data-stu-id="4a465-181">When comparing null values, it is important to understand the difference between the way the `Equals` method evaluates null values in <xref:System.Data.SqlTypes> as compared with the way it works with CLR types.</span></span> <span data-ttu-id="4a465-182">所有 <xref:System.Data.SqlTypes>`Equals` 方法都使用数据库语义计算 null 值：如果其中任何一个值为空或两个值都为空，则比较结果将为空。</span><span class="sxs-lookup"><span data-stu-id="4a465-182">All of the <xref:System.Data.SqlTypes>`Equals` methods use database semantics for evaluating null values: if either or both of the values is null, the comparison yields null.</span></span> <span data-ttu-id="4a465-183">另一方面，如果两个 `Equals` 都为 null，则对其使用 CLR <xref:System.Data.SqlTypes> 方法将生成 true。</span><span class="sxs-lookup"><span data-stu-id="4a465-183">On the other hand, using the CLR `Equals` method on two <xref:System.Data.SqlTypes> will yield true if both are null.</span></span> <span data-ttu-id="4a465-184">这反映了使用实例方法（如 CLR `String.Equals` 方法）和使用静态/共享方法 `SqlString.Equals` 之间的差别。</span><span class="sxs-lookup"><span data-stu-id="4a465-184">This reflects the difference between using an instance method such as the CLR `String.Equals` method, and using the static/shared method, `SqlString.Equals`.</span></span>  
  
 <span data-ttu-id="4a465-185">下面的示例演示为 `SqlString.Equals` 方法和 `String.Equals` 方法传递一对 null 值，然后传递一对空字符串时，这两种方法生成的结果之间存在的差异。</span><span class="sxs-lookup"><span data-stu-id="4a465-185">The following example demonstrates the difference in results between the `SqlString.Equals` method and the `String.Equals` method when each is passed a pair of null values and then a pair of empty strings.</span></span>  
  
 [!code-csharp[DataWorks SqlTypes.CompareNulls#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.CompareNulls/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.CompareNulls#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.CompareNulls/VB/source.vb#1)]  
  
 <span data-ttu-id="4a465-186">此代码生成以下输出内容：</span><span class="sxs-lookup"><span data-stu-id="4a465-186">The code produces the following output:</span></span>  
  
```  
SqlString.Equals shared/static method:  
  Two nulls=Null  
  
String.Equals instance method:  
  Two nulls=True  
  
SqlString.Equals shared/static method:  
  Two empty strings=True  
  
String.Equals instance method:  
  Two empty strings=True   
```  
  
## <a name="see-also"></a><span data-ttu-id="4a465-187">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a465-187">See Also</span></span>  
 [<span data-ttu-id="4a465-188">SQL Server 数据类型和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4a465-188">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [<span data-ttu-id="4a465-189">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="4a465-189">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
