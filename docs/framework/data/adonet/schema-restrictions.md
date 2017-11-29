---
title: "架构限制"
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
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c254865800694af8eb754c3e8d4072688fd7e89a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="schema-restrictions"></a><span data-ttu-id="d6ba0-102">架构限制</span><span class="sxs-lookup"><span data-stu-id="d6ba0-102">Schema Restrictions</span></span>
<span data-ttu-id="d6ba0-103">第二个可选参数**GetSchema**方法是返回用于限制的架构信息量的限制，以及将其传递到**GetSchema**作为一个字符串数组的方法.</span><span class="sxs-lookup"><span data-stu-id="d6ba0-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="d6ba0-104">在数组中的位置确定可以传递的值，这等效于限制数。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="d6ba0-105">例如，下表说明使用适用于 SQL Server 的 .NET Framework 数据提供程序时“Tables”架构集合支持的限制。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="d6ba0-106">SQL Server 架构集合的其他限制在本主题的结尾处列出。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="d6ba0-107">限制名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-107">Restriction Name</span></span>|<span data-ttu-id="d6ba0-108">参数名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-108">Parameter Name</span></span>|<span data-ttu-id="d6ba0-109">限制默认值</span><span class="sxs-lookup"><span data-stu-id="d6ba0-109">Restriction Default</span></span>|<span data-ttu-id="d6ba0-110">限制数</span><span class="sxs-lookup"><span data-stu-id="d6ba0-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6ba0-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6ba0-111">Catalog</span></span>|@Catalog|<span data-ttu-id="d6ba0-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6ba0-112">TABLE_CATALOG</span></span>|<span data-ttu-id="d6ba0-113">1</span><span class="sxs-lookup"><span data-stu-id="d6ba0-113">1</span></span>|  
|<span data-ttu-id="d6ba0-114">Owner</span><span class="sxs-lookup"><span data-stu-id="d6ba0-114">Owner</span></span>|@Owner|<span data-ttu-id="d6ba0-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6ba0-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="d6ba0-116">2</span><span class="sxs-lookup"><span data-stu-id="d6ba0-116">2</span></span>|  
|<span data-ttu-id="d6ba0-117">表</span><span class="sxs-lookup"><span data-stu-id="d6ba0-117">Table</span></span>|@Name|<span data-ttu-id="d6ba0-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d6ba0-118">TABLE_NAME</span></span>|<span data-ttu-id="d6ba0-119">3</span><span class="sxs-lookup"><span data-stu-id="d6ba0-119">3</span></span>|  
|<span data-ttu-id="d6ba0-120">TableType</span><span class="sxs-lookup"><span data-stu-id="d6ba0-120">TableType</span></span>|@TableType|<span data-ttu-id="d6ba0-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d6ba0-121">TABLE_TYPE</span></span>|<span data-ttu-id="d6ba0-122">4</span><span class="sxs-lookup"><span data-stu-id="d6ba0-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="d6ba0-123">指定限制值</span><span class="sxs-lookup"><span data-stu-id="d6ba0-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="d6ba0-124">要使用“Tables”架构集合的一个限制，只需创建一个包含四个元素的字符串数组，然后在与限制数匹配的元素中填充值。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="d6ba0-125">例如，若要限制返回的**GetSchema**对仅在"Sales"架构中，这些表的方法将其传递给之前设置为"Sales"数组的第二个元素**GetSchema**方法。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6ba0-126">`SqlClient` 和 `OracleClient` 的限制集合还有附加的 `ParameterName` 列。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="d6ba0-127">为了向后兼容，仍提供限制默认列，但是目前忽略该列。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="d6ba0-128">在指定限制值时，应使用参数化查询（而不是字符串替换）来最大程度地降低受到 SQL 注入式攻击的风险。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6ba0-129">数组中的元素数必须小于或等于指定架构集合支持的限制数，否则，将引发 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="d6ba0-130">可以小于最大限制数。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="d6ba0-131">缺少的限制假定为空（无限制）。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="d6ba0-132">您可以查询由.NET Framework 托管提供程序以确定支持的限制列表通过调用**GetSchema**限制架构集合，这是"限制"同名的方法。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="d6ba0-133">此时将返回 <xref:System.Data.DataTable>，包含集合名称、限制名称、默认限制值和限制数的列表。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="d6ba0-134">示例</span><span class="sxs-lookup"><span data-stu-id="d6ba0-134">Example</span></span>  
 <span data-ttu-id="d6ba0-135">下面的示例演示如何使用<xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>SQL Server 的.NET Framework 数据提供程序方法<xref:System.Data.SqlClient.SqlConnection>类检索有关的所有表中包含的架构信息**AdventureWorks**示例数据库，并能够限制的信息返回到只有"销售"的架构中的表：</span><span class="sxs-lookup"><span data-stu-id="d6ba0-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
Sub Main()  
  Dim connectionString As String = _  
    "Data Source=(local);Database=AdventureWorks;" & _  
       "Integrated Security=true;";  
  
  Dim restrictions(3) As String  
  Using connection As New SqlConnection(connectionString)  
    connection.Open()  
  
    'Specify the restrictions.  
    restrictions(1) = "Sales"  
    Dim table As DataTable = connection.GetSchema("Tables", _  
       restrictions)  
  
    ' Display the contents of the table.  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Using  
End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
    string connectionString =   
       "Data Source=(local);Database=AdventureWorks;" +  
       "Integrated Security=true;";  
    using (SqlConnection connection =  
       new SqlConnection(connectionString))  
    {  
        connection.Open();  
  
        // Specify the restrictions.  
        string[] restrictions = new string[4];  
        restrictions[1] = "Sales";  
        System.Data.DataTable table = connection.GetSchema(  
          "Tables", restrictions);  
  
        // Display the contents of the table.  
        foreach (System.Data.DataRow row in table.Rows)  
        {  
            foreach (System.Data.DataColumn col in table.Columns)  
            {  
                Console.WriteLine("{0} = {1}",   
                  col.ColumnName, row[col]);  
            }  
            Console.WriteLine("============================");  
        }  
        Console.WriteLine("Press any key to continue.");  
        Console.ReadKey();  
    }  
  }  
  
  private static string GetConnectionString()  
  {  
     // To avoid storing the connection string in your code,  
     // you can retrieve it from a configuration file.  
     return "Data Source=(local);Database=AdventureWorks;" +  
        "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="d6ba0-136">SQL Server 架构限制</span><span class="sxs-lookup"><span data-stu-id="d6ba0-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="d6ba0-137">下表列出了 SQL Server 架构集合的限制。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="d6ba0-138">Users</span><span class="sxs-lookup"><span data-stu-id="d6ba0-138">Users</span></span>  
  
|<span data-ttu-id="d6ba0-139">限制名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-139">Restriction Name</span></span>|<span data-ttu-id="d6ba0-140">参数名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-140">Parameter Name</span></span>|<span data-ttu-id="d6ba0-141">限制默认值</span><span class="sxs-lookup"><span data-stu-id="d6ba0-141">Restriction Default</span></span>|<span data-ttu-id="d6ba0-142">限制数</span><span class="sxs-lookup"><span data-stu-id="d6ba0-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6ba0-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="d6ba0-143">User_Name</span></span>|@Name|<span data-ttu-id="d6ba0-144">name</span><span class="sxs-lookup"><span data-stu-id="d6ba0-144">name</span></span>|<span data-ttu-id="d6ba0-145">1</span><span class="sxs-lookup"><span data-stu-id="d6ba0-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="d6ba0-146">数据库</span><span class="sxs-lookup"><span data-stu-id="d6ba0-146">Databases</span></span>  
  
|<span data-ttu-id="d6ba0-147">限制名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-147">Restriction Name</span></span>|<span data-ttu-id="d6ba0-148">参数名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-148">Parameter Name</span></span>|<span data-ttu-id="d6ba0-149">限制默认值</span><span class="sxs-lookup"><span data-stu-id="d6ba0-149">Restriction Default</span></span>|<span data-ttu-id="d6ba0-150">限制数</span><span class="sxs-lookup"><span data-stu-id="d6ba0-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6ba0-151">名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-151">Name</span></span>|@Name|<span data-ttu-id="d6ba0-152">名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-152">Name</span></span>|<span data-ttu-id="d6ba0-153">1</span><span class="sxs-lookup"><span data-stu-id="d6ba0-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="d6ba0-154">表</span><span class="sxs-lookup"><span data-stu-id="d6ba0-154">Tables</span></span>  
  
|<span data-ttu-id="d6ba0-155">限制名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-155">Restriction Name</span></span>|<span data-ttu-id="d6ba0-156">参数名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-156">Parameter Name</span></span>|<span data-ttu-id="d6ba0-157">限制默认值</span><span class="sxs-lookup"><span data-stu-id="d6ba0-157">Restriction Default</span></span>|<span data-ttu-id="d6ba0-158">限制数</span><span class="sxs-lookup"><span data-stu-id="d6ba0-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6ba0-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6ba0-159">Catalog</span></span>|@Catalog|<span data-ttu-id="d6ba0-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6ba0-160">TABLE_CATALOG</span></span>|<span data-ttu-id="d6ba0-161">1</span><span class="sxs-lookup"><span data-stu-id="d6ba0-161">1</span></span>|  
|<span data-ttu-id="d6ba0-162">Owner</span><span class="sxs-lookup"><span data-stu-id="d6ba0-162">Owner</span></span>|@Owner|<span data-ttu-id="d6ba0-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6ba0-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="d6ba0-164">2</span><span class="sxs-lookup"><span data-stu-id="d6ba0-164">2</span></span>|  
|<span data-ttu-id="d6ba0-165">表</span><span class="sxs-lookup"><span data-stu-id="d6ba0-165">Table</span></span>|@Name|<span data-ttu-id="d6ba0-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d6ba0-166">TABLE_NAME</span></span>|<span data-ttu-id="d6ba0-167">3</span><span class="sxs-lookup"><span data-stu-id="d6ba0-167">3</span></span>|  
|<span data-ttu-id="d6ba0-168">TableType</span><span class="sxs-lookup"><span data-stu-id="d6ba0-168">TableType</span></span>|@TableType|<span data-ttu-id="d6ba0-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d6ba0-169">TABLE_TYPE</span></span>|<span data-ttu-id="d6ba0-170">4</span><span class="sxs-lookup"><span data-stu-id="d6ba0-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d6ba0-171">Columns</span><span class="sxs-lookup"><span data-stu-id="d6ba0-171">Columns</span></span>  
  
|<span data-ttu-id="d6ba0-172">限制名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-172">Restriction Name</span></span>|<span data-ttu-id="d6ba0-173">参数名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-173">Parameter Name</span></span>|<span data-ttu-id="d6ba0-174">限制默认值</span><span class="sxs-lookup"><span data-stu-id="d6ba0-174">Restriction Default</span></span>|<span data-ttu-id="d6ba0-175">限制数</span><span class="sxs-lookup"><span data-stu-id="d6ba0-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6ba0-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6ba0-176">Catalog</span></span>|@Catalog|<span data-ttu-id="d6ba0-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6ba0-177">TABLE_CATALOG</span></span>|<span data-ttu-id="d6ba0-178">1</span><span class="sxs-lookup"><span data-stu-id="d6ba0-178">1</span></span>|  
|<span data-ttu-id="d6ba0-179">Owner</span><span class="sxs-lookup"><span data-stu-id="d6ba0-179">Owner</span></span>|@Owner|<span data-ttu-id="d6ba0-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6ba0-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="d6ba0-181">2</span><span class="sxs-lookup"><span data-stu-id="d6ba0-181">2</span></span>|  
|<span data-ttu-id="d6ba0-182">表</span><span class="sxs-lookup"><span data-stu-id="d6ba0-182">Table</span></span>|@Table|<span data-ttu-id="d6ba0-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d6ba0-183">TABLE_NAME</span></span>|<span data-ttu-id="d6ba0-184">3</span><span class="sxs-lookup"><span data-stu-id="d6ba0-184">3</span></span>|  
|<span data-ttu-id="d6ba0-185">列</span><span class="sxs-lookup"><span data-stu-id="d6ba0-185">Column</span></span>|@Column|<span data-ttu-id="d6ba0-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d6ba0-186">COLUMN_NAME</span></span>|<span data-ttu-id="d6ba0-187">4</span><span class="sxs-lookup"><span data-stu-id="d6ba0-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="d6ba0-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="d6ba0-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="d6ba0-189">限制名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-189">Restriction Name</span></span>|<span data-ttu-id="d6ba0-190">参数名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-190">Parameter Name</span></span>|<span data-ttu-id="d6ba0-191">限制默认值</span><span class="sxs-lookup"><span data-stu-id="d6ba0-191">Restriction Default</span></span>|<span data-ttu-id="d6ba0-192">限制数</span><span class="sxs-lookup"><span data-stu-id="d6ba0-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6ba0-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6ba0-193">Catalog</span></span>|@Catalog|<span data-ttu-id="d6ba0-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6ba0-194">TABLE_CATALOG</span></span>|<span data-ttu-id="d6ba0-195">1</span><span class="sxs-lookup"><span data-stu-id="d6ba0-195">1</span></span>|  
|<span data-ttu-id="d6ba0-196">Owner</span><span class="sxs-lookup"><span data-stu-id="d6ba0-196">Owner</span></span>|@Owner|<span data-ttu-id="d6ba0-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6ba0-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="d6ba0-198">2</span><span class="sxs-lookup"><span data-stu-id="d6ba0-198">2</span></span>|  
|<span data-ttu-id="d6ba0-199">表</span><span class="sxs-lookup"><span data-stu-id="d6ba0-199">Table</span></span>|@Table|<span data-ttu-id="d6ba0-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d6ba0-200">TABLE_NAME</span></span>|<span data-ttu-id="d6ba0-201">3</span><span class="sxs-lookup"><span data-stu-id="d6ba0-201">3</span></span>|  
|<span data-ttu-id="d6ba0-202">列</span><span class="sxs-lookup"><span data-stu-id="d6ba0-202">Column</span></span>|@Column|<span data-ttu-id="d6ba0-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d6ba0-203">COLUMN_NAME</span></span>|<span data-ttu-id="d6ba0-204">4</span><span class="sxs-lookup"><span data-stu-id="d6ba0-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="d6ba0-205">视图</span><span class="sxs-lookup"><span data-stu-id="d6ba0-205">Views</span></span>  
  
|<span data-ttu-id="d6ba0-206">限制名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-206">Restriction Name</span></span>|<span data-ttu-id="d6ba0-207">参数名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-207">Parameter Name</span></span>|<span data-ttu-id="d6ba0-208">限制默认值</span><span class="sxs-lookup"><span data-stu-id="d6ba0-208">Restriction Default</span></span>|<span data-ttu-id="d6ba0-209">限制数</span><span class="sxs-lookup"><span data-stu-id="d6ba0-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6ba0-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6ba0-210">Catalog</span></span>|@Catalog|<span data-ttu-id="d6ba0-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6ba0-211">TABLE_CATALOG</span></span>|<span data-ttu-id="d6ba0-212">1</span><span class="sxs-lookup"><span data-stu-id="d6ba0-212">1</span></span>|  
|<span data-ttu-id="d6ba0-213">Owner</span><span class="sxs-lookup"><span data-stu-id="d6ba0-213">Owner</span></span>|@Owner|<span data-ttu-id="d6ba0-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6ba0-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="d6ba0-215">2</span><span class="sxs-lookup"><span data-stu-id="d6ba0-215">2</span></span>|  
|<span data-ttu-id="d6ba0-216">表</span><span class="sxs-lookup"><span data-stu-id="d6ba0-216">Table</span></span>|@Table|<span data-ttu-id="d6ba0-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d6ba0-217">TABLE_NAME</span></span>|<span data-ttu-id="d6ba0-218">3</span><span class="sxs-lookup"><span data-stu-id="d6ba0-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="d6ba0-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="d6ba0-219">ViewColumns</span></span>  
  
|<span data-ttu-id="d6ba0-220">限制名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-220">Restriction Name</span></span>|<span data-ttu-id="d6ba0-221">参数名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-221">Parameter Name</span></span>|<span data-ttu-id="d6ba0-222">限制默认值</span><span class="sxs-lookup"><span data-stu-id="d6ba0-222">Restriction Default</span></span>|<span data-ttu-id="d6ba0-223">限制数</span><span class="sxs-lookup"><span data-stu-id="d6ba0-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6ba0-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6ba0-224">Catalog</span></span>|@Catalog|<span data-ttu-id="d6ba0-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6ba0-225">VIEW_CATALOG</span></span>|<span data-ttu-id="d6ba0-226">1</span><span class="sxs-lookup"><span data-stu-id="d6ba0-226">1</span></span>|  
|<span data-ttu-id="d6ba0-227">Owner</span><span class="sxs-lookup"><span data-stu-id="d6ba0-227">Owner</span></span>|@Owner|<span data-ttu-id="d6ba0-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6ba0-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="d6ba0-229">2</span><span class="sxs-lookup"><span data-stu-id="d6ba0-229">2</span></span>|  
|<span data-ttu-id="d6ba0-230">表</span><span class="sxs-lookup"><span data-stu-id="d6ba0-230">Table</span></span>|@Table|<span data-ttu-id="d6ba0-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="d6ba0-231">VIEW_NAME</span></span>|<span data-ttu-id="d6ba0-232">3</span><span class="sxs-lookup"><span data-stu-id="d6ba0-232">3</span></span>|  
|<span data-ttu-id="d6ba0-233">列</span><span class="sxs-lookup"><span data-stu-id="d6ba0-233">Column</span></span>|@Column|<span data-ttu-id="d6ba0-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d6ba0-234">COLUMN_NAME</span></span>|<span data-ttu-id="d6ba0-235">4</span><span class="sxs-lookup"><span data-stu-id="d6ba0-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="d6ba0-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d6ba0-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="d6ba0-237">限制名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-237">Restriction Name</span></span>|<span data-ttu-id="d6ba0-238">参数名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-238">Parameter Name</span></span>|<span data-ttu-id="d6ba0-239">限制默认值</span><span class="sxs-lookup"><span data-stu-id="d6ba0-239">Restriction Default</span></span>|<span data-ttu-id="d6ba0-240">限制数</span><span class="sxs-lookup"><span data-stu-id="d6ba0-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6ba0-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6ba0-241">Catalog</span></span>|@Catalog|<span data-ttu-id="d6ba0-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6ba0-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="d6ba0-243">1</span><span class="sxs-lookup"><span data-stu-id="d6ba0-243">1</span></span>|  
|<span data-ttu-id="d6ba0-244">Owner</span><span class="sxs-lookup"><span data-stu-id="d6ba0-244">Owner</span></span>|@Owner|<span data-ttu-id="d6ba0-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6ba0-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="d6ba0-246">2</span><span class="sxs-lookup"><span data-stu-id="d6ba0-246">2</span></span>|  
|<span data-ttu-id="d6ba0-247">名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-247">Name</span></span>|@Name|<span data-ttu-id="d6ba0-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="d6ba0-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="d6ba0-249">3</span><span class="sxs-lookup"><span data-stu-id="d6ba0-249">3</span></span>|  
|<span data-ttu-id="d6ba0-250">参数</span><span class="sxs-lookup"><span data-stu-id="d6ba0-250">Parameter</span></span>|@Parameter|<span data-ttu-id="d6ba0-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="d6ba0-251">PARAMETER_NAME</span></span>|<span data-ttu-id="d6ba0-252">4</span><span class="sxs-lookup"><span data-stu-id="d6ba0-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d6ba0-253">过程</span><span class="sxs-lookup"><span data-stu-id="d6ba0-253">Procedures</span></span>  
  
|<span data-ttu-id="d6ba0-254">限制名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-254">Restriction Name</span></span>|<span data-ttu-id="d6ba0-255">参数名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-255">Parameter Name</span></span>|<span data-ttu-id="d6ba0-256">限制默认值</span><span class="sxs-lookup"><span data-stu-id="d6ba0-256">Restriction Default</span></span>|<span data-ttu-id="d6ba0-257">限制数</span><span class="sxs-lookup"><span data-stu-id="d6ba0-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6ba0-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6ba0-258">Catalog</span></span>|@Catalog|<span data-ttu-id="d6ba0-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6ba0-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="d6ba0-260">1</span><span class="sxs-lookup"><span data-stu-id="d6ba0-260">1</span></span>|  
|<span data-ttu-id="d6ba0-261">Owner</span><span class="sxs-lookup"><span data-stu-id="d6ba0-261">Owner</span></span>|@Owner|<span data-ttu-id="d6ba0-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6ba0-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="d6ba0-263">2</span><span class="sxs-lookup"><span data-stu-id="d6ba0-263">2</span></span>|  
|<span data-ttu-id="d6ba0-264">名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-264">Name</span></span>|@Name|<span data-ttu-id="d6ba0-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="d6ba0-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="d6ba0-266">3</span><span class="sxs-lookup"><span data-stu-id="d6ba0-266">3</span></span>|  
|<span data-ttu-id="d6ba0-267">类型</span><span class="sxs-lookup"><span data-stu-id="d6ba0-267">Type</span></span>|@Type|<span data-ttu-id="d6ba0-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d6ba0-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="d6ba0-269">4</span><span class="sxs-lookup"><span data-stu-id="d6ba0-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="d6ba0-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="d6ba0-270">IndexColumns</span></span>  
  
|<span data-ttu-id="d6ba0-271">限制名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-271">Restriction Name</span></span>|<span data-ttu-id="d6ba0-272">参数名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-272">Parameter Name</span></span>|<span data-ttu-id="d6ba0-273">限制默认值</span><span class="sxs-lookup"><span data-stu-id="d6ba0-273">Restriction Default</span></span>|<span data-ttu-id="d6ba0-274">限制数</span><span class="sxs-lookup"><span data-stu-id="d6ba0-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6ba0-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6ba0-275">Catalog</span></span>|@Catalog|<span data-ttu-id="d6ba0-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="d6ba0-276">db_name()</span></span>|<span data-ttu-id="d6ba0-277">1</span><span class="sxs-lookup"><span data-stu-id="d6ba0-277">1</span></span>|  
|<span data-ttu-id="d6ba0-278">Owner</span><span class="sxs-lookup"><span data-stu-id="d6ba0-278">Owner</span></span>|@Owner|<span data-ttu-id="d6ba0-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="d6ba0-279">user_name()</span></span>|<span data-ttu-id="d6ba0-280">2</span><span class="sxs-lookup"><span data-stu-id="d6ba0-280">2</span></span>|  
|<span data-ttu-id="d6ba0-281">表</span><span class="sxs-lookup"><span data-stu-id="d6ba0-281">Table</span></span>|@Table|<span data-ttu-id="d6ba0-282">o.name</span><span class="sxs-lookup"><span data-stu-id="d6ba0-282">o.name</span></span>|<span data-ttu-id="d6ba0-283">3</span><span class="sxs-lookup"><span data-stu-id="d6ba0-283">3</span></span>|  
|<span data-ttu-id="d6ba0-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="d6ba0-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="d6ba0-285">x.name</span><span class="sxs-lookup"><span data-stu-id="d6ba0-285">x.name</span></span>|<span data-ttu-id="d6ba0-286">4</span><span class="sxs-lookup"><span data-stu-id="d6ba0-286">4</span></span>|  
|<span data-ttu-id="d6ba0-287">列</span><span class="sxs-lookup"><span data-stu-id="d6ba0-287">Column</span></span>|@Column|<span data-ttu-id="d6ba0-288">c.name</span><span class="sxs-lookup"><span data-stu-id="d6ba0-288">c.name</span></span>|<span data-ttu-id="d6ba0-289">5</span><span class="sxs-lookup"><span data-stu-id="d6ba0-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="d6ba0-290">索引</span><span class="sxs-lookup"><span data-stu-id="d6ba0-290">Indexes</span></span>  
  
|<span data-ttu-id="d6ba0-291">限制名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-291">Restriction Name</span></span>|<span data-ttu-id="d6ba0-292">参数名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-292">Parameter Name</span></span>|<span data-ttu-id="d6ba0-293">限制默认值</span><span class="sxs-lookup"><span data-stu-id="d6ba0-293">Restriction Default</span></span>|<span data-ttu-id="d6ba0-294">限制数</span><span class="sxs-lookup"><span data-stu-id="d6ba0-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6ba0-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6ba0-295">Catalog</span></span>|@Catalog|<span data-ttu-id="d6ba0-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="d6ba0-296">db_name()</span></span>|<span data-ttu-id="d6ba0-297">1</span><span class="sxs-lookup"><span data-stu-id="d6ba0-297">1</span></span>|  
|<span data-ttu-id="d6ba0-298">Owner</span><span class="sxs-lookup"><span data-stu-id="d6ba0-298">Owner</span></span>|@Owner|<span data-ttu-id="d6ba0-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="d6ba0-299">user_name()</span></span>|<span data-ttu-id="d6ba0-300">2</span><span class="sxs-lookup"><span data-stu-id="d6ba0-300">2</span></span>|  
|<span data-ttu-id="d6ba0-301">表</span><span class="sxs-lookup"><span data-stu-id="d6ba0-301">Table</span></span>|@Table|<span data-ttu-id="d6ba0-302">o.name</span><span class="sxs-lookup"><span data-stu-id="d6ba0-302">o.name</span></span>|<span data-ttu-id="d6ba0-303">3</span><span class="sxs-lookup"><span data-stu-id="d6ba0-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="d6ba0-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="d6ba0-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="d6ba0-305">限制名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-305">Restriction Name</span></span>|<span data-ttu-id="d6ba0-306">参数名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-306">Parameter Name</span></span>|<span data-ttu-id="d6ba0-307">限制默认值</span><span class="sxs-lookup"><span data-stu-id="d6ba0-307">Restriction Default</span></span>|<span data-ttu-id="d6ba0-308">限制数</span><span class="sxs-lookup"><span data-stu-id="d6ba0-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6ba0-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="d6ba0-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="d6ba0-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="d6ba0-310">assemblies.name</span></span>|<span data-ttu-id="d6ba0-311">1</span><span class="sxs-lookup"><span data-stu-id="d6ba0-311">1</span></span>|  
|<span data-ttu-id="d6ba0-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="d6ba0-312">udt_name</span></span>|@UDTName|<span data-ttu-id="d6ba0-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="d6ba0-313">types.assembly_class</span></span>|<span data-ttu-id="d6ba0-314">2</span><span class="sxs-lookup"><span data-stu-id="d6ba0-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="d6ba0-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="d6ba0-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="d6ba0-316">限制名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-316">Restriction Name</span></span>|<span data-ttu-id="d6ba0-317">参数名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-317">Parameter Name</span></span>|<span data-ttu-id="d6ba0-318">限制默认值</span><span class="sxs-lookup"><span data-stu-id="d6ba0-318">Restriction Default</span></span>|<span data-ttu-id="d6ba0-319">限制数</span><span class="sxs-lookup"><span data-stu-id="d6ba0-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6ba0-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6ba0-320">Catalog</span></span>|@Catalog|<span data-ttu-id="d6ba0-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6ba0-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="d6ba0-322">1</span><span class="sxs-lookup"><span data-stu-id="d6ba0-322">1</span></span>|  
|<span data-ttu-id="d6ba0-323">Owner</span><span class="sxs-lookup"><span data-stu-id="d6ba0-323">Owner</span></span>|@Owner|<span data-ttu-id="d6ba0-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6ba0-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="d6ba0-325">2</span><span class="sxs-lookup"><span data-stu-id="d6ba0-325">2</span></span>|  
|<span data-ttu-id="d6ba0-326">表</span><span class="sxs-lookup"><span data-stu-id="d6ba0-326">Table</span></span>|@Table|<span data-ttu-id="d6ba0-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d6ba0-327">TABLE_NAME</span></span>|<span data-ttu-id="d6ba0-328">3</span><span class="sxs-lookup"><span data-stu-id="d6ba0-328">3</span></span>|  
|<span data-ttu-id="d6ba0-329">名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-329">Name</span></span>|@Name|<span data-ttu-id="d6ba0-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="d6ba0-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="d6ba0-331">4</span><span class="sxs-lookup"><span data-stu-id="d6ba0-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="d6ba0-332">SQL Server 2008     </span><span class="sxs-lookup"><span data-stu-id="d6ba0-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="d6ba0-333">下表列出了 SQL Server 2008 架构集合的限制。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="d6ba0-334">这些限制从 .NET Framework 版本 3.5 SP1 和 SQL Server 2008 开始生效。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="d6ba0-335">.NET Framework 和 SQL Server 的早期版本不支持这些限制。</span><span class="sxs-lookup"><span data-stu-id="d6ba0-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="d6ba0-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="d6ba0-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="d6ba0-337">限制名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-337">Restriction Name</span></span>|<span data-ttu-id="d6ba0-338">参数名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-338">Parameter Name</span></span>|<span data-ttu-id="d6ba0-339">限制默认值</span><span class="sxs-lookup"><span data-stu-id="d6ba0-339">Restriction Default</span></span>|<span data-ttu-id="d6ba0-340">限制数</span><span class="sxs-lookup"><span data-stu-id="d6ba0-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6ba0-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6ba0-341">Catalog</span></span>|@Catalog|<span data-ttu-id="d6ba0-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6ba0-342">TABLE_CATALOG</span></span>|<span data-ttu-id="d6ba0-343">1</span><span class="sxs-lookup"><span data-stu-id="d6ba0-343">1</span></span>|  
|<span data-ttu-id="d6ba0-344">Owner</span><span class="sxs-lookup"><span data-stu-id="d6ba0-344">Owner</span></span>|@Owner|<span data-ttu-id="d6ba0-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6ba0-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="d6ba0-346">2</span><span class="sxs-lookup"><span data-stu-id="d6ba0-346">2</span></span>|  
|<span data-ttu-id="d6ba0-347">表</span><span class="sxs-lookup"><span data-stu-id="d6ba0-347">Table</span></span>|@Table|<span data-ttu-id="d6ba0-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d6ba0-348">TABLE_NAME</span></span>|<span data-ttu-id="d6ba0-349">3</span><span class="sxs-lookup"><span data-stu-id="d6ba0-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="d6ba0-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="d6ba0-350">AllColumns</span></span>  
  
|<span data-ttu-id="d6ba0-351">限制名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-351">Restriction Name</span></span>|<span data-ttu-id="d6ba0-352">参数名称</span><span class="sxs-lookup"><span data-stu-id="d6ba0-352">Parameter Name</span></span>|<span data-ttu-id="d6ba0-353">限制默认值</span><span class="sxs-lookup"><span data-stu-id="d6ba0-353">Restriction Default</span></span>|<span data-ttu-id="d6ba0-354">限制数</span><span class="sxs-lookup"><span data-stu-id="d6ba0-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d6ba0-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="d6ba0-355">Catalog</span></span>|@Catalog|<span data-ttu-id="d6ba0-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d6ba0-356">TABLE_CATALOG</span></span>|<span data-ttu-id="d6ba0-357">1</span><span class="sxs-lookup"><span data-stu-id="d6ba0-357">1</span></span>|  
|<span data-ttu-id="d6ba0-358">Owner</span><span class="sxs-lookup"><span data-stu-id="d6ba0-358">Owner</span></span>|@Owner|<span data-ttu-id="d6ba0-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d6ba0-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="d6ba0-360">2</span><span class="sxs-lookup"><span data-stu-id="d6ba0-360">2</span></span>|  
|<span data-ttu-id="d6ba0-361">表</span><span class="sxs-lookup"><span data-stu-id="d6ba0-361">Table</span></span>|@Table|<span data-ttu-id="d6ba0-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d6ba0-362">TABLE_NAME</span></span>|<span data-ttu-id="d6ba0-363">3</span><span class="sxs-lookup"><span data-stu-id="d6ba0-363">3</span></span>|  
|<span data-ttu-id="d6ba0-364">列</span><span class="sxs-lookup"><span data-stu-id="d6ba0-364">Column</span></span>|@Column|<span data-ttu-id="d6ba0-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d6ba0-365">COLUMN_NAME</span></span>|<span data-ttu-id="d6ba0-366">4</span><span class="sxs-lookup"><span data-stu-id="d6ba0-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d6ba0-367">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6ba0-367">See Also</span></span>  
 [<span data-ttu-id="d6ba0-368">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="d6ba0-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
