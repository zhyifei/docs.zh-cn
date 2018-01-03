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
ms.workload: dotnet
ms.openlocfilehash: 4a3cc1f0c27af1ad41e14374b4c155e6b8620f28
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="schema-restrictions"></a><span data-ttu-id="45ace-102">架构限制</span><span class="sxs-lookup"><span data-stu-id="45ace-102">Schema Restrictions</span></span>
<span data-ttu-id="45ace-103">第二个可选参数**GetSchema**方法是返回用于限制的架构信息量的限制，以及将其传递到**GetSchema**作为一个字符串数组的方法.</span><span class="sxs-lookup"><span data-stu-id="45ace-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="45ace-104">在数组中的位置确定可以传递的值，这等效于限制数。</span><span class="sxs-lookup"><span data-stu-id="45ace-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="45ace-105">例如，下表说明使用适用于 SQL Server 的 .NET Framework 数据提供程序时“Tables”架构集合支持的限制。</span><span class="sxs-lookup"><span data-stu-id="45ace-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="45ace-106">SQL Server 架构集合的其他限制在本主题的结尾处列出。</span><span class="sxs-lookup"><span data-stu-id="45ace-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="45ace-107">限制名称</span><span class="sxs-lookup"><span data-stu-id="45ace-107">Restriction Name</span></span>|<span data-ttu-id="45ace-108">参数名称</span><span class="sxs-lookup"><span data-stu-id="45ace-108">Parameter Name</span></span>|<span data-ttu-id="45ace-109">限制默认值</span><span class="sxs-lookup"><span data-stu-id="45ace-109">Restriction Default</span></span>|<span data-ttu-id="45ace-110">限制数</span><span class="sxs-lookup"><span data-stu-id="45ace-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="45ace-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="45ace-111">Catalog</span></span>|@Catalog|<span data-ttu-id="45ace-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45ace-112">TABLE_CATALOG</span></span>|<span data-ttu-id="45ace-113">1</span><span class="sxs-lookup"><span data-stu-id="45ace-113">1</span></span>|  
|<span data-ttu-id="45ace-114">Owner</span><span class="sxs-lookup"><span data-stu-id="45ace-114">Owner</span></span>|@Owner|<span data-ttu-id="45ace-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45ace-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="45ace-116">2</span><span class="sxs-lookup"><span data-stu-id="45ace-116">2</span></span>|  
|<span data-ttu-id="45ace-117">表</span><span class="sxs-lookup"><span data-stu-id="45ace-117">Table</span></span>|@Name|<span data-ttu-id="45ace-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="45ace-118">TABLE_NAME</span></span>|<span data-ttu-id="45ace-119">3</span><span class="sxs-lookup"><span data-stu-id="45ace-119">3</span></span>|  
|<span data-ttu-id="45ace-120">TableType</span><span class="sxs-lookup"><span data-stu-id="45ace-120">TableType</span></span>|@TableType|<span data-ttu-id="45ace-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="45ace-121">TABLE_TYPE</span></span>|<span data-ttu-id="45ace-122">4</span><span class="sxs-lookup"><span data-stu-id="45ace-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="45ace-123">指定限制值</span><span class="sxs-lookup"><span data-stu-id="45ace-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="45ace-124">要使用“Tables”架构集合的一个限制，只需创建一个包含四个元素的字符串数组，然后在与限制数匹配的元素中填充值。</span><span class="sxs-lookup"><span data-stu-id="45ace-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="45ace-125">例如，若要限制返回的**GetSchema**对仅在"Sales"架构中，这些表的方法将其传递给之前设置为"Sales"数组的第二个元素**GetSchema**方法。</span><span class="sxs-lookup"><span data-stu-id="45ace-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45ace-126">`SqlClient` 和 `OracleClient` 的限制集合还有附加的 `ParameterName` 列。</span><span class="sxs-lookup"><span data-stu-id="45ace-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="45ace-127">为了向后兼容，仍提供限制默认列，但是目前忽略该列。</span><span class="sxs-lookup"><span data-stu-id="45ace-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="45ace-128">在指定限制值时，应使用参数化查询（而不是字符串替换）来最大程度地降低受到 SQL 注入式攻击的风险。</span><span class="sxs-lookup"><span data-stu-id="45ace-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45ace-129">数组中的元素数必须小于或等于指定架构集合支持的限制数，否则，将引发 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="45ace-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="45ace-130">可以小于最大限制数。</span><span class="sxs-lookup"><span data-stu-id="45ace-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="45ace-131">缺少的限制假定为空（无限制）。</span><span class="sxs-lookup"><span data-stu-id="45ace-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="45ace-132">您可以查询由.NET Framework 托管提供程序以确定支持的限制列表通过调用**GetSchema**限制架构集合，这是"限制"同名的方法。</span><span class="sxs-lookup"><span data-stu-id="45ace-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="45ace-133">此时将返回 <xref:System.Data.DataTable>，包含集合名称、限制名称、默认限制值和限制数的列表。</span><span class="sxs-lookup"><span data-stu-id="45ace-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="45ace-134">示例</span><span class="sxs-lookup"><span data-stu-id="45ace-134">Example</span></span>  
 <span data-ttu-id="45ace-135">下面的示例演示如何使用<xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>SQL Server 的.NET Framework 数据提供程序方法<xref:System.Data.SqlClient.SqlConnection>类检索有关的所有表中包含的架构信息**AdventureWorks**示例数据库，并能够限制的信息返回到只有"销售"的架构中的表：</span><span class="sxs-lookup"><span data-stu-id="45ace-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="45ace-136">SQL Server 架构限制</span><span class="sxs-lookup"><span data-stu-id="45ace-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="45ace-137">下表列出了 SQL Server 架构集合的限制。</span><span class="sxs-lookup"><span data-stu-id="45ace-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="45ace-138">Users</span><span class="sxs-lookup"><span data-stu-id="45ace-138">Users</span></span>  
  
|<span data-ttu-id="45ace-139">限制名称</span><span class="sxs-lookup"><span data-stu-id="45ace-139">Restriction Name</span></span>|<span data-ttu-id="45ace-140">参数名称</span><span class="sxs-lookup"><span data-stu-id="45ace-140">Parameter Name</span></span>|<span data-ttu-id="45ace-141">限制默认值</span><span class="sxs-lookup"><span data-stu-id="45ace-141">Restriction Default</span></span>|<span data-ttu-id="45ace-142">限制数</span><span class="sxs-lookup"><span data-stu-id="45ace-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="45ace-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="45ace-143">User_Name</span></span>|@Name|<span data-ttu-id="45ace-144">name</span><span class="sxs-lookup"><span data-stu-id="45ace-144">name</span></span>|<span data-ttu-id="45ace-145">1</span><span class="sxs-lookup"><span data-stu-id="45ace-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="45ace-146">数据库</span><span class="sxs-lookup"><span data-stu-id="45ace-146">Databases</span></span>  
  
|<span data-ttu-id="45ace-147">限制名称</span><span class="sxs-lookup"><span data-stu-id="45ace-147">Restriction Name</span></span>|<span data-ttu-id="45ace-148">参数名称</span><span class="sxs-lookup"><span data-stu-id="45ace-148">Parameter Name</span></span>|<span data-ttu-id="45ace-149">限制默认值</span><span class="sxs-lookup"><span data-stu-id="45ace-149">Restriction Default</span></span>|<span data-ttu-id="45ace-150">限制数</span><span class="sxs-lookup"><span data-stu-id="45ace-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="45ace-151">name</span><span class="sxs-lookup"><span data-stu-id="45ace-151">Name</span></span>|@Name|<span data-ttu-id="45ace-152">name</span><span class="sxs-lookup"><span data-stu-id="45ace-152">Name</span></span>|<span data-ttu-id="45ace-153">1</span><span class="sxs-lookup"><span data-stu-id="45ace-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="45ace-154">表</span><span class="sxs-lookup"><span data-stu-id="45ace-154">Tables</span></span>  
  
|<span data-ttu-id="45ace-155">限制名称</span><span class="sxs-lookup"><span data-stu-id="45ace-155">Restriction Name</span></span>|<span data-ttu-id="45ace-156">参数名称</span><span class="sxs-lookup"><span data-stu-id="45ace-156">Parameter Name</span></span>|<span data-ttu-id="45ace-157">限制默认值</span><span class="sxs-lookup"><span data-stu-id="45ace-157">Restriction Default</span></span>|<span data-ttu-id="45ace-158">限制数</span><span class="sxs-lookup"><span data-stu-id="45ace-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="45ace-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="45ace-159">Catalog</span></span>|@Catalog|<span data-ttu-id="45ace-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45ace-160">TABLE_CATALOG</span></span>|<span data-ttu-id="45ace-161">1</span><span class="sxs-lookup"><span data-stu-id="45ace-161">1</span></span>|  
|<span data-ttu-id="45ace-162">Owner</span><span class="sxs-lookup"><span data-stu-id="45ace-162">Owner</span></span>|@Owner|<span data-ttu-id="45ace-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45ace-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="45ace-164">2</span><span class="sxs-lookup"><span data-stu-id="45ace-164">2</span></span>|  
|<span data-ttu-id="45ace-165">表</span><span class="sxs-lookup"><span data-stu-id="45ace-165">Table</span></span>|@Name|<span data-ttu-id="45ace-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="45ace-166">TABLE_NAME</span></span>|<span data-ttu-id="45ace-167">3</span><span class="sxs-lookup"><span data-stu-id="45ace-167">3</span></span>|  
|<span data-ttu-id="45ace-168">TableType</span><span class="sxs-lookup"><span data-stu-id="45ace-168">TableType</span></span>|@TableType|<span data-ttu-id="45ace-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="45ace-169">TABLE_TYPE</span></span>|<span data-ttu-id="45ace-170">4</span><span class="sxs-lookup"><span data-stu-id="45ace-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="45ace-171">Columns</span><span class="sxs-lookup"><span data-stu-id="45ace-171">Columns</span></span>  
  
|<span data-ttu-id="45ace-172">限制名称</span><span class="sxs-lookup"><span data-stu-id="45ace-172">Restriction Name</span></span>|<span data-ttu-id="45ace-173">参数名称</span><span class="sxs-lookup"><span data-stu-id="45ace-173">Parameter Name</span></span>|<span data-ttu-id="45ace-174">限制默认值</span><span class="sxs-lookup"><span data-stu-id="45ace-174">Restriction Default</span></span>|<span data-ttu-id="45ace-175">限制数</span><span class="sxs-lookup"><span data-stu-id="45ace-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="45ace-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="45ace-176">Catalog</span></span>|@Catalog|<span data-ttu-id="45ace-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45ace-177">TABLE_CATALOG</span></span>|<span data-ttu-id="45ace-178">1</span><span class="sxs-lookup"><span data-stu-id="45ace-178">1</span></span>|  
|<span data-ttu-id="45ace-179">Owner</span><span class="sxs-lookup"><span data-stu-id="45ace-179">Owner</span></span>|@Owner|<span data-ttu-id="45ace-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45ace-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="45ace-181">2</span><span class="sxs-lookup"><span data-stu-id="45ace-181">2</span></span>|  
|<span data-ttu-id="45ace-182">表</span><span class="sxs-lookup"><span data-stu-id="45ace-182">Table</span></span>|@Table|<span data-ttu-id="45ace-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="45ace-183">TABLE_NAME</span></span>|<span data-ttu-id="45ace-184">3</span><span class="sxs-lookup"><span data-stu-id="45ace-184">3</span></span>|  
|<span data-ttu-id="45ace-185">列</span><span class="sxs-lookup"><span data-stu-id="45ace-185">Column</span></span>|@Column|<span data-ttu-id="45ace-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="45ace-186">COLUMN_NAME</span></span>|<span data-ttu-id="45ace-187">4</span><span class="sxs-lookup"><span data-stu-id="45ace-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="45ace-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="45ace-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="45ace-189">限制名称</span><span class="sxs-lookup"><span data-stu-id="45ace-189">Restriction Name</span></span>|<span data-ttu-id="45ace-190">参数名称</span><span class="sxs-lookup"><span data-stu-id="45ace-190">Parameter Name</span></span>|<span data-ttu-id="45ace-191">限制默认值</span><span class="sxs-lookup"><span data-stu-id="45ace-191">Restriction Default</span></span>|<span data-ttu-id="45ace-192">限制数</span><span class="sxs-lookup"><span data-stu-id="45ace-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="45ace-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="45ace-193">Catalog</span></span>|@Catalog|<span data-ttu-id="45ace-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45ace-194">TABLE_CATALOG</span></span>|<span data-ttu-id="45ace-195">1</span><span class="sxs-lookup"><span data-stu-id="45ace-195">1</span></span>|  
|<span data-ttu-id="45ace-196">Owner</span><span class="sxs-lookup"><span data-stu-id="45ace-196">Owner</span></span>|@Owner|<span data-ttu-id="45ace-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45ace-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="45ace-198">2</span><span class="sxs-lookup"><span data-stu-id="45ace-198">2</span></span>|  
|<span data-ttu-id="45ace-199">表</span><span class="sxs-lookup"><span data-stu-id="45ace-199">Table</span></span>|@Table|<span data-ttu-id="45ace-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="45ace-200">TABLE_NAME</span></span>|<span data-ttu-id="45ace-201">3</span><span class="sxs-lookup"><span data-stu-id="45ace-201">3</span></span>|  
|<span data-ttu-id="45ace-202">列</span><span class="sxs-lookup"><span data-stu-id="45ace-202">Column</span></span>|@Column|<span data-ttu-id="45ace-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="45ace-203">COLUMN_NAME</span></span>|<span data-ttu-id="45ace-204">4</span><span class="sxs-lookup"><span data-stu-id="45ace-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="45ace-205">视图</span><span class="sxs-lookup"><span data-stu-id="45ace-205">Views</span></span>  
  
|<span data-ttu-id="45ace-206">限制名称</span><span class="sxs-lookup"><span data-stu-id="45ace-206">Restriction Name</span></span>|<span data-ttu-id="45ace-207">参数名称</span><span class="sxs-lookup"><span data-stu-id="45ace-207">Parameter Name</span></span>|<span data-ttu-id="45ace-208">限制默认值</span><span class="sxs-lookup"><span data-stu-id="45ace-208">Restriction Default</span></span>|<span data-ttu-id="45ace-209">限制数</span><span class="sxs-lookup"><span data-stu-id="45ace-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="45ace-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="45ace-210">Catalog</span></span>|@Catalog|<span data-ttu-id="45ace-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45ace-211">TABLE_CATALOG</span></span>|<span data-ttu-id="45ace-212">1</span><span class="sxs-lookup"><span data-stu-id="45ace-212">1</span></span>|  
|<span data-ttu-id="45ace-213">Owner</span><span class="sxs-lookup"><span data-stu-id="45ace-213">Owner</span></span>|@Owner|<span data-ttu-id="45ace-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45ace-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="45ace-215">2</span><span class="sxs-lookup"><span data-stu-id="45ace-215">2</span></span>|  
|<span data-ttu-id="45ace-216">表</span><span class="sxs-lookup"><span data-stu-id="45ace-216">Table</span></span>|@Table|<span data-ttu-id="45ace-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="45ace-217">TABLE_NAME</span></span>|<span data-ttu-id="45ace-218">3</span><span class="sxs-lookup"><span data-stu-id="45ace-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="45ace-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="45ace-219">ViewColumns</span></span>  
  
|<span data-ttu-id="45ace-220">限制名称</span><span class="sxs-lookup"><span data-stu-id="45ace-220">Restriction Name</span></span>|<span data-ttu-id="45ace-221">参数名称</span><span class="sxs-lookup"><span data-stu-id="45ace-221">Parameter Name</span></span>|<span data-ttu-id="45ace-222">限制默认值</span><span class="sxs-lookup"><span data-stu-id="45ace-222">Restriction Default</span></span>|<span data-ttu-id="45ace-223">限制数</span><span class="sxs-lookup"><span data-stu-id="45ace-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="45ace-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="45ace-224">Catalog</span></span>|@Catalog|<span data-ttu-id="45ace-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45ace-225">VIEW_CATALOG</span></span>|<span data-ttu-id="45ace-226">1</span><span class="sxs-lookup"><span data-stu-id="45ace-226">1</span></span>|  
|<span data-ttu-id="45ace-227">Owner</span><span class="sxs-lookup"><span data-stu-id="45ace-227">Owner</span></span>|@Owner|<span data-ttu-id="45ace-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45ace-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="45ace-229">2</span><span class="sxs-lookup"><span data-stu-id="45ace-229">2</span></span>|  
|<span data-ttu-id="45ace-230">表</span><span class="sxs-lookup"><span data-stu-id="45ace-230">Table</span></span>|@Table|<span data-ttu-id="45ace-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="45ace-231">VIEW_NAME</span></span>|<span data-ttu-id="45ace-232">3</span><span class="sxs-lookup"><span data-stu-id="45ace-232">3</span></span>|  
|<span data-ttu-id="45ace-233">列</span><span class="sxs-lookup"><span data-stu-id="45ace-233">Column</span></span>|@Column|<span data-ttu-id="45ace-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="45ace-234">COLUMN_NAME</span></span>|<span data-ttu-id="45ace-235">4</span><span class="sxs-lookup"><span data-stu-id="45ace-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="45ace-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="45ace-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="45ace-237">限制名称</span><span class="sxs-lookup"><span data-stu-id="45ace-237">Restriction Name</span></span>|<span data-ttu-id="45ace-238">参数名称</span><span class="sxs-lookup"><span data-stu-id="45ace-238">Parameter Name</span></span>|<span data-ttu-id="45ace-239">限制默认值</span><span class="sxs-lookup"><span data-stu-id="45ace-239">Restriction Default</span></span>|<span data-ttu-id="45ace-240">限制数</span><span class="sxs-lookup"><span data-stu-id="45ace-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="45ace-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="45ace-241">Catalog</span></span>|@Catalog|<span data-ttu-id="45ace-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45ace-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="45ace-243">1</span><span class="sxs-lookup"><span data-stu-id="45ace-243">1</span></span>|  
|<span data-ttu-id="45ace-244">Owner</span><span class="sxs-lookup"><span data-stu-id="45ace-244">Owner</span></span>|@Owner|<span data-ttu-id="45ace-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45ace-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="45ace-246">2</span><span class="sxs-lookup"><span data-stu-id="45ace-246">2</span></span>|  
|<span data-ttu-id="45ace-247">name</span><span class="sxs-lookup"><span data-stu-id="45ace-247">Name</span></span>|@Name|<span data-ttu-id="45ace-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="45ace-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="45ace-249">3</span><span class="sxs-lookup"><span data-stu-id="45ace-249">3</span></span>|  
|<span data-ttu-id="45ace-250">参数</span><span class="sxs-lookup"><span data-stu-id="45ace-250">Parameter</span></span>|@Parameter|<span data-ttu-id="45ace-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="45ace-251">PARAMETER_NAME</span></span>|<span data-ttu-id="45ace-252">4</span><span class="sxs-lookup"><span data-stu-id="45ace-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="45ace-253">过程</span><span class="sxs-lookup"><span data-stu-id="45ace-253">Procedures</span></span>  
  
|<span data-ttu-id="45ace-254">限制名称</span><span class="sxs-lookup"><span data-stu-id="45ace-254">Restriction Name</span></span>|<span data-ttu-id="45ace-255">参数名称</span><span class="sxs-lookup"><span data-stu-id="45ace-255">Parameter Name</span></span>|<span data-ttu-id="45ace-256">限制默认值</span><span class="sxs-lookup"><span data-stu-id="45ace-256">Restriction Default</span></span>|<span data-ttu-id="45ace-257">限制数</span><span class="sxs-lookup"><span data-stu-id="45ace-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="45ace-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="45ace-258">Catalog</span></span>|@Catalog|<span data-ttu-id="45ace-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45ace-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="45ace-260">1</span><span class="sxs-lookup"><span data-stu-id="45ace-260">1</span></span>|  
|<span data-ttu-id="45ace-261">Owner</span><span class="sxs-lookup"><span data-stu-id="45ace-261">Owner</span></span>|@Owner|<span data-ttu-id="45ace-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45ace-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="45ace-263">2</span><span class="sxs-lookup"><span data-stu-id="45ace-263">2</span></span>|  
|<span data-ttu-id="45ace-264">name</span><span class="sxs-lookup"><span data-stu-id="45ace-264">Name</span></span>|@Name|<span data-ttu-id="45ace-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="45ace-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="45ace-266">3</span><span class="sxs-lookup"><span data-stu-id="45ace-266">3</span></span>|  
|<span data-ttu-id="45ace-267">类型</span><span class="sxs-lookup"><span data-stu-id="45ace-267">Type</span></span>|@Type|<span data-ttu-id="45ace-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="45ace-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="45ace-269">4</span><span class="sxs-lookup"><span data-stu-id="45ace-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="45ace-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="45ace-270">IndexColumns</span></span>  
  
|<span data-ttu-id="45ace-271">限制名称</span><span class="sxs-lookup"><span data-stu-id="45ace-271">Restriction Name</span></span>|<span data-ttu-id="45ace-272">参数名称</span><span class="sxs-lookup"><span data-stu-id="45ace-272">Parameter Name</span></span>|<span data-ttu-id="45ace-273">限制默认值</span><span class="sxs-lookup"><span data-stu-id="45ace-273">Restriction Default</span></span>|<span data-ttu-id="45ace-274">限制数</span><span class="sxs-lookup"><span data-stu-id="45ace-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="45ace-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="45ace-275">Catalog</span></span>|@Catalog|<span data-ttu-id="45ace-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="45ace-276">db_name()</span></span>|<span data-ttu-id="45ace-277">1</span><span class="sxs-lookup"><span data-stu-id="45ace-277">1</span></span>|  
|<span data-ttu-id="45ace-278">Owner</span><span class="sxs-lookup"><span data-stu-id="45ace-278">Owner</span></span>|@Owner|<span data-ttu-id="45ace-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="45ace-279">user_name()</span></span>|<span data-ttu-id="45ace-280">2</span><span class="sxs-lookup"><span data-stu-id="45ace-280">2</span></span>|  
|<span data-ttu-id="45ace-281">表</span><span class="sxs-lookup"><span data-stu-id="45ace-281">Table</span></span>|@Table|<span data-ttu-id="45ace-282">o.name</span><span class="sxs-lookup"><span data-stu-id="45ace-282">o.name</span></span>|<span data-ttu-id="45ace-283">3</span><span class="sxs-lookup"><span data-stu-id="45ace-283">3</span></span>|  
|<span data-ttu-id="45ace-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="45ace-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="45ace-285">x.name</span><span class="sxs-lookup"><span data-stu-id="45ace-285">x.name</span></span>|<span data-ttu-id="45ace-286">4</span><span class="sxs-lookup"><span data-stu-id="45ace-286">4</span></span>|  
|<span data-ttu-id="45ace-287">列</span><span class="sxs-lookup"><span data-stu-id="45ace-287">Column</span></span>|@Column|<span data-ttu-id="45ace-288">c.name</span><span class="sxs-lookup"><span data-stu-id="45ace-288">c.name</span></span>|<span data-ttu-id="45ace-289">5</span><span class="sxs-lookup"><span data-stu-id="45ace-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="45ace-290">索引</span><span class="sxs-lookup"><span data-stu-id="45ace-290">Indexes</span></span>  
  
|<span data-ttu-id="45ace-291">限制名称</span><span class="sxs-lookup"><span data-stu-id="45ace-291">Restriction Name</span></span>|<span data-ttu-id="45ace-292">参数名称</span><span class="sxs-lookup"><span data-stu-id="45ace-292">Parameter Name</span></span>|<span data-ttu-id="45ace-293">限制默认值</span><span class="sxs-lookup"><span data-stu-id="45ace-293">Restriction Default</span></span>|<span data-ttu-id="45ace-294">限制数</span><span class="sxs-lookup"><span data-stu-id="45ace-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="45ace-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="45ace-295">Catalog</span></span>|@Catalog|<span data-ttu-id="45ace-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="45ace-296">db_name()</span></span>|<span data-ttu-id="45ace-297">1</span><span class="sxs-lookup"><span data-stu-id="45ace-297">1</span></span>|  
|<span data-ttu-id="45ace-298">Owner</span><span class="sxs-lookup"><span data-stu-id="45ace-298">Owner</span></span>|@Owner|<span data-ttu-id="45ace-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="45ace-299">user_name()</span></span>|<span data-ttu-id="45ace-300">2</span><span class="sxs-lookup"><span data-stu-id="45ace-300">2</span></span>|  
|<span data-ttu-id="45ace-301">表</span><span class="sxs-lookup"><span data-stu-id="45ace-301">Table</span></span>|@Table|<span data-ttu-id="45ace-302">o.name</span><span class="sxs-lookup"><span data-stu-id="45ace-302">o.name</span></span>|<span data-ttu-id="45ace-303">3</span><span class="sxs-lookup"><span data-stu-id="45ace-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="45ace-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="45ace-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="45ace-305">限制名称</span><span class="sxs-lookup"><span data-stu-id="45ace-305">Restriction Name</span></span>|<span data-ttu-id="45ace-306">参数名称</span><span class="sxs-lookup"><span data-stu-id="45ace-306">Parameter Name</span></span>|<span data-ttu-id="45ace-307">限制默认值</span><span class="sxs-lookup"><span data-stu-id="45ace-307">Restriction Default</span></span>|<span data-ttu-id="45ace-308">限制数</span><span class="sxs-lookup"><span data-stu-id="45ace-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="45ace-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="45ace-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="45ace-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="45ace-310">assemblies.name</span></span>|<span data-ttu-id="45ace-311">1</span><span class="sxs-lookup"><span data-stu-id="45ace-311">1</span></span>|  
|<span data-ttu-id="45ace-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="45ace-312">udt_name</span></span>|@UDTName|<span data-ttu-id="45ace-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="45ace-313">types.assembly_class</span></span>|<span data-ttu-id="45ace-314">2</span><span class="sxs-lookup"><span data-stu-id="45ace-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="45ace-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="45ace-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="45ace-316">限制名称</span><span class="sxs-lookup"><span data-stu-id="45ace-316">Restriction Name</span></span>|<span data-ttu-id="45ace-317">参数名称</span><span class="sxs-lookup"><span data-stu-id="45ace-317">Parameter Name</span></span>|<span data-ttu-id="45ace-318">限制默认值</span><span class="sxs-lookup"><span data-stu-id="45ace-318">Restriction Default</span></span>|<span data-ttu-id="45ace-319">限制数</span><span class="sxs-lookup"><span data-stu-id="45ace-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="45ace-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="45ace-320">Catalog</span></span>|@Catalog|<span data-ttu-id="45ace-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45ace-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="45ace-322">1</span><span class="sxs-lookup"><span data-stu-id="45ace-322">1</span></span>|  
|<span data-ttu-id="45ace-323">Owner</span><span class="sxs-lookup"><span data-stu-id="45ace-323">Owner</span></span>|@Owner|<span data-ttu-id="45ace-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45ace-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="45ace-325">2</span><span class="sxs-lookup"><span data-stu-id="45ace-325">2</span></span>|  
|<span data-ttu-id="45ace-326">表</span><span class="sxs-lookup"><span data-stu-id="45ace-326">Table</span></span>|@Table|<span data-ttu-id="45ace-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="45ace-327">TABLE_NAME</span></span>|<span data-ttu-id="45ace-328">3</span><span class="sxs-lookup"><span data-stu-id="45ace-328">3</span></span>|  
|<span data-ttu-id="45ace-329">name</span><span class="sxs-lookup"><span data-stu-id="45ace-329">Name</span></span>|@Name|<span data-ttu-id="45ace-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="45ace-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="45ace-331">4</span><span class="sxs-lookup"><span data-stu-id="45ace-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="45ace-332">SQL Server 2008     </span><span class="sxs-lookup"><span data-stu-id="45ace-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="45ace-333">下表列出了 SQL Server 2008 架构集合的限制。</span><span class="sxs-lookup"><span data-stu-id="45ace-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="45ace-334">这些限制从 .NET Framework 版本 3.5 SP1 和 SQL Server 2008 开始生效。</span><span class="sxs-lookup"><span data-stu-id="45ace-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="45ace-335">.NET Framework 和 SQL Server 的早期版本不支持这些限制。</span><span class="sxs-lookup"><span data-stu-id="45ace-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="45ace-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="45ace-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="45ace-337">限制名称</span><span class="sxs-lookup"><span data-stu-id="45ace-337">Restriction Name</span></span>|<span data-ttu-id="45ace-338">参数名称</span><span class="sxs-lookup"><span data-stu-id="45ace-338">Parameter Name</span></span>|<span data-ttu-id="45ace-339">限制默认值</span><span class="sxs-lookup"><span data-stu-id="45ace-339">Restriction Default</span></span>|<span data-ttu-id="45ace-340">限制数</span><span class="sxs-lookup"><span data-stu-id="45ace-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="45ace-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="45ace-341">Catalog</span></span>|@Catalog|<span data-ttu-id="45ace-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45ace-342">TABLE_CATALOG</span></span>|<span data-ttu-id="45ace-343">1</span><span class="sxs-lookup"><span data-stu-id="45ace-343">1</span></span>|  
|<span data-ttu-id="45ace-344">Owner</span><span class="sxs-lookup"><span data-stu-id="45ace-344">Owner</span></span>|@Owner|<span data-ttu-id="45ace-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45ace-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="45ace-346">2</span><span class="sxs-lookup"><span data-stu-id="45ace-346">2</span></span>|  
|<span data-ttu-id="45ace-347">表</span><span class="sxs-lookup"><span data-stu-id="45ace-347">Table</span></span>|@Table|<span data-ttu-id="45ace-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="45ace-348">TABLE_NAME</span></span>|<span data-ttu-id="45ace-349">3</span><span class="sxs-lookup"><span data-stu-id="45ace-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="45ace-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="45ace-350">AllColumns</span></span>  
  
|<span data-ttu-id="45ace-351">限制名称</span><span class="sxs-lookup"><span data-stu-id="45ace-351">Restriction Name</span></span>|<span data-ttu-id="45ace-352">参数名称</span><span class="sxs-lookup"><span data-stu-id="45ace-352">Parameter Name</span></span>|<span data-ttu-id="45ace-353">限制默认值</span><span class="sxs-lookup"><span data-stu-id="45ace-353">Restriction Default</span></span>|<span data-ttu-id="45ace-354">限制数</span><span class="sxs-lookup"><span data-stu-id="45ace-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="45ace-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="45ace-355">Catalog</span></span>|@Catalog|<span data-ttu-id="45ace-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="45ace-356">TABLE_CATALOG</span></span>|<span data-ttu-id="45ace-357">1</span><span class="sxs-lookup"><span data-stu-id="45ace-357">1</span></span>|  
|<span data-ttu-id="45ace-358">Owner</span><span class="sxs-lookup"><span data-stu-id="45ace-358">Owner</span></span>|@Owner|<span data-ttu-id="45ace-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="45ace-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="45ace-360">2</span><span class="sxs-lookup"><span data-stu-id="45ace-360">2</span></span>|  
|<span data-ttu-id="45ace-361">表</span><span class="sxs-lookup"><span data-stu-id="45ace-361">Table</span></span>|@Table|<span data-ttu-id="45ace-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="45ace-362">TABLE_NAME</span></span>|<span data-ttu-id="45ace-363">3</span><span class="sxs-lookup"><span data-stu-id="45ace-363">3</span></span>|  
|<span data-ttu-id="45ace-364">列</span><span class="sxs-lookup"><span data-stu-id="45ace-364">Column</span></span>|@Column|<span data-ttu-id="45ace-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="45ace-365">COLUMN_NAME</span></span>|<span data-ttu-id="45ace-366">4</span><span class="sxs-lookup"><span data-stu-id="45ace-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="45ace-367">请参阅</span><span class="sxs-lookup"><span data-stu-id="45ace-367">See Also</span></span>  
 [<span data-ttu-id="45ace-368">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="45ace-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
