---
title: 架构限制
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 17c42c5131252993d1f16e4a2f7a6450f0984d11
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149006"
---
# <a name="schema-restrictions"></a><span data-ttu-id="abc3b-102">架构限制</span><span class="sxs-lookup"><span data-stu-id="abc3b-102">Schema Restrictions</span></span>
<span data-ttu-id="abc3b-103">**GetSchema**方法的第二个可选参数是用于限制返回的架构信息量的限制，它作为字符串数组传递给**GetSchema**方法。</span><span class="sxs-lookup"><span data-stu-id="abc3b-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="abc3b-104">在数组中的位置确定可以传递的值，这等效于限制数。</span><span class="sxs-lookup"><span data-stu-id="abc3b-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="abc3b-105">例如，下表说明使用适用于 SQL Server 的 .NET Framework 数据提供程序时“Tables”架构集合支持的限制。</span><span class="sxs-lookup"><span data-stu-id="abc3b-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="abc3b-106">SQL Server 架构集合的其他限制在本主题的结尾处列出。</span><span class="sxs-lookup"><span data-stu-id="abc3b-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="abc3b-107">限制名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-107">Restriction Name</span></span>|<span data-ttu-id="abc3b-108">参数名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-108">Parameter Name</span></span>|<span data-ttu-id="abc3b-109">限制默认值</span><span class="sxs-lookup"><span data-stu-id="abc3b-109">Restriction Default</span></span>|<span data-ttu-id="abc3b-110">限制数</span><span class="sxs-lookup"><span data-stu-id="abc3b-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="abc3b-111">目录</span><span class="sxs-lookup"><span data-stu-id="abc3b-111">Catalog</span></span>|@Catalog|<span data-ttu-id="abc3b-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="abc3b-112">TABLE_CATALOG</span></span>|<span data-ttu-id="abc3b-113">1</span><span class="sxs-lookup"><span data-stu-id="abc3b-113">1</span></span>|  
|<span data-ttu-id="abc3b-114">“所有者”</span><span class="sxs-lookup"><span data-stu-id="abc3b-114">Owner</span></span>|@Owner|<span data-ttu-id="abc3b-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="abc3b-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="abc3b-116">2</span><span class="sxs-lookup"><span data-stu-id="abc3b-116">2</span></span>|  
|<span data-ttu-id="abc3b-117">表</span><span class="sxs-lookup"><span data-stu-id="abc3b-117">Table</span></span>|@Name|<span data-ttu-id="abc3b-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="abc3b-118">TABLE_NAME</span></span>|<span data-ttu-id="abc3b-119">3</span><span class="sxs-lookup"><span data-stu-id="abc3b-119">3</span></span>|  
|<span data-ttu-id="abc3b-120">TableType</span><span class="sxs-lookup"><span data-stu-id="abc3b-120">TableType</span></span>|@TableType|<span data-ttu-id="abc3b-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="abc3b-121">TABLE_TYPE</span></span>|<span data-ttu-id="abc3b-122">4</span><span class="sxs-lookup"><span data-stu-id="abc3b-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="abc3b-123">指定限制值</span><span class="sxs-lookup"><span data-stu-id="abc3b-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="abc3b-124">要使用“Tables”架构集合的一个限制，只需创建一个包含四个元素的字符串数组，然后在与限制数匹配的元素中填充值。</span><span class="sxs-lookup"><span data-stu-id="abc3b-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="abc3b-125">例如，要将**GetSchema**方法返回的表限制为"销售"架构中的这些表，在将其传递给**GetSchema**方法之前，将数组的第二个元素设置为"Sales"。</span><span class="sxs-lookup"><span data-stu-id="abc3b-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="abc3b-126">`SqlClient` 和 `OracleClient` 的限制集合还有附加的 `ParameterName` 列。</span><span class="sxs-lookup"><span data-stu-id="abc3b-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="abc3b-127">为了向后兼容，仍提供限制默认列，但是目前忽略该列。</span><span class="sxs-lookup"><span data-stu-id="abc3b-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="abc3b-128">在指定限制值时，应使用参数化查询（而不是字符串替换）来最大程度地降低受到 SQL 注入式攻击的风险。</span><span class="sxs-lookup"><span data-stu-id="abc3b-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="abc3b-129">数组中的元素数必须小于或等于指定架构集合支持的限制数，否则，将引发 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="abc3b-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="abc3b-130">可以小于最大限制数。</span><span class="sxs-lookup"><span data-stu-id="abc3b-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="abc3b-131">缺少的限制假定为空（无限制）。</span><span class="sxs-lookup"><span data-stu-id="abc3b-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="abc3b-132">您可以查询 .NET Framework 托管提供程序，通过调用具有限制架构集合名称的**GetSchema**方法（即"限制"）来确定受支持限制的列表。</span><span class="sxs-lookup"><span data-stu-id="abc3b-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="abc3b-133">此时将返回 <xref:System.Data.DataTable>，包含集合名称、限制名称、默认限制值和限制数的列表。</span><span class="sxs-lookup"><span data-stu-id="abc3b-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="abc3b-134">示例</span><span class="sxs-lookup"><span data-stu-id="abc3b-134">Example</span></span>  
 <span data-ttu-id="abc3b-135">以下示例演示如何使用 SQL Server<xref:System.Data.SqlClient.SqlConnection.GetSchema%2A><xref:System.Data.SqlClient.SqlConnection>类的 .NET 框架数据提供程序的方法检索有关**AdventureWorks**示例数据库中包含的所有表的架构信息，并将返回的信息限制为"销售"架构中仅返回的信息：</span><span class="sxs-lookup"><span data-stu-id="abc3b-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="abc3b-136">SQL Server 架构限制</span><span class="sxs-lookup"><span data-stu-id="abc3b-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="abc3b-137">下表列出了 SQL Server 架构集合的限制。</span><span class="sxs-lookup"><span data-stu-id="abc3b-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="abc3b-138">用户</span><span class="sxs-lookup"><span data-stu-id="abc3b-138">Users</span></span>  
  
|<span data-ttu-id="abc3b-139">限制名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-139">Restriction Name</span></span>|<span data-ttu-id="abc3b-140">参数名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-140">Parameter Name</span></span>|<span data-ttu-id="abc3b-141">限制默认值</span><span class="sxs-lookup"><span data-stu-id="abc3b-141">Restriction Default</span></span>|<span data-ttu-id="abc3b-142">限制数</span><span class="sxs-lookup"><span data-stu-id="abc3b-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="abc3b-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="abc3b-143">User_Name</span></span>|@Name|<span data-ttu-id="abc3b-144">name</span><span class="sxs-lookup"><span data-stu-id="abc3b-144">name</span></span>|<span data-ttu-id="abc3b-145">1</span><span class="sxs-lookup"><span data-stu-id="abc3b-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="abc3b-146">数据库</span><span class="sxs-lookup"><span data-stu-id="abc3b-146">Databases</span></span>  
  
|<span data-ttu-id="abc3b-147">限制名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-147">Restriction Name</span></span>|<span data-ttu-id="abc3b-148">参数名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-148">Parameter Name</span></span>|<span data-ttu-id="abc3b-149">限制默认值</span><span class="sxs-lookup"><span data-stu-id="abc3b-149">Restriction Default</span></span>|<span data-ttu-id="abc3b-150">限制数</span><span class="sxs-lookup"><span data-stu-id="abc3b-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="abc3b-151">名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-151">Name</span></span>|@Name|<span data-ttu-id="abc3b-152">名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-152">Name</span></span>|<span data-ttu-id="abc3b-153">1</span><span class="sxs-lookup"><span data-stu-id="abc3b-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="abc3b-154">表</span><span class="sxs-lookup"><span data-stu-id="abc3b-154">Tables</span></span>  
  
|<span data-ttu-id="abc3b-155">限制名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-155">Restriction Name</span></span>|<span data-ttu-id="abc3b-156">参数名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-156">Parameter Name</span></span>|<span data-ttu-id="abc3b-157">限制默认值</span><span class="sxs-lookup"><span data-stu-id="abc3b-157">Restriction Default</span></span>|<span data-ttu-id="abc3b-158">限制数</span><span class="sxs-lookup"><span data-stu-id="abc3b-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="abc3b-159">目录</span><span class="sxs-lookup"><span data-stu-id="abc3b-159">Catalog</span></span>|@Catalog|<span data-ttu-id="abc3b-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="abc3b-160">TABLE_CATALOG</span></span>|<span data-ttu-id="abc3b-161">1</span><span class="sxs-lookup"><span data-stu-id="abc3b-161">1</span></span>|  
|<span data-ttu-id="abc3b-162">“所有者”</span><span class="sxs-lookup"><span data-stu-id="abc3b-162">Owner</span></span>|@Owner|<span data-ttu-id="abc3b-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="abc3b-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="abc3b-164">2</span><span class="sxs-lookup"><span data-stu-id="abc3b-164">2</span></span>|  
|<span data-ttu-id="abc3b-165">表</span><span class="sxs-lookup"><span data-stu-id="abc3b-165">Table</span></span>|@Name|<span data-ttu-id="abc3b-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="abc3b-166">TABLE_NAME</span></span>|<span data-ttu-id="abc3b-167">3</span><span class="sxs-lookup"><span data-stu-id="abc3b-167">3</span></span>|  
|<span data-ttu-id="abc3b-168">TableType</span><span class="sxs-lookup"><span data-stu-id="abc3b-168">TableType</span></span>|@TableType|<span data-ttu-id="abc3b-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="abc3b-169">TABLE_TYPE</span></span>|<span data-ttu-id="abc3b-170">4</span><span class="sxs-lookup"><span data-stu-id="abc3b-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="abc3b-171">列</span><span class="sxs-lookup"><span data-stu-id="abc3b-171">Columns</span></span>  
  
|<span data-ttu-id="abc3b-172">限制名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-172">Restriction Name</span></span>|<span data-ttu-id="abc3b-173">参数名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-173">Parameter Name</span></span>|<span data-ttu-id="abc3b-174">限制默认值</span><span class="sxs-lookup"><span data-stu-id="abc3b-174">Restriction Default</span></span>|<span data-ttu-id="abc3b-175">限制数</span><span class="sxs-lookup"><span data-stu-id="abc3b-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="abc3b-176">目录</span><span class="sxs-lookup"><span data-stu-id="abc3b-176">Catalog</span></span>|@Catalog|<span data-ttu-id="abc3b-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="abc3b-177">TABLE_CATALOG</span></span>|<span data-ttu-id="abc3b-178">1</span><span class="sxs-lookup"><span data-stu-id="abc3b-178">1</span></span>|  
|<span data-ttu-id="abc3b-179">“所有者”</span><span class="sxs-lookup"><span data-stu-id="abc3b-179">Owner</span></span>|@Owner|<span data-ttu-id="abc3b-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="abc3b-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="abc3b-181">2</span><span class="sxs-lookup"><span data-stu-id="abc3b-181">2</span></span>|  
|<span data-ttu-id="abc3b-182">表</span><span class="sxs-lookup"><span data-stu-id="abc3b-182">Table</span></span>|@Table|<span data-ttu-id="abc3b-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="abc3b-183">TABLE_NAME</span></span>|<span data-ttu-id="abc3b-184">3</span><span class="sxs-lookup"><span data-stu-id="abc3b-184">3</span></span>|  
|<span data-ttu-id="abc3b-185">列</span><span class="sxs-lookup"><span data-stu-id="abc3b-185">Column</span></span>|@Column|<span data-ttu-id="abc3b-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="abc3b-186">COLUMN_NAME</span></span>|<span data-ttu-id="abc3b-187">4</span><span class="sxs-lookup"><span data-stu-id="abc3b-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="abc3b-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="abc3b-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="abc3b-189">限制名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-189">Restriction Name</span></span>|<span data-ttu-id="abc3b-190">参数名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-190">Parameter Name</span></span>|<span data-ttu-id="abc3b-191">限制默认值</span><span class="sxs-lookup"><span data-stu-id="abc3b-191">Restriction Default</span></span>|<span data-ttu-id="abc3b-192">限制数</span><span class="sxs-lookup"><span data-stu-id="abc3b-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="abc3b-193">目录</span><span class="sxs-lookup"><span data-stu-id="abc3b-193">Catalog</span></span>|@Catalog|<span data-ttu-id="abc3b-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="abc3b-194">TABLE_CATALOG</span></span>|<span data-ttu-id="abc3b-195">1</span><span class="sxs-lookup"><span data-stu-id="abc3b-195">1</span></span>|  
|<span data-ttu-id="abc3b-196">“所有者”</span><span class="sxs-lookup"><span data-stu-id="abc3b-196">Owner</span></span>|@Owner|<span data-ttu-id="abc3b-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="abc3b-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="abc3b-198">2</span><span class="sxs-lookup"><span data-stu-id="abc3b-198">2</span></span>|  
|<span data-ttu-id="abc3b-199">表</span><span class="sxs-lookup"><span data-stu-id="abc3b-199">Table</span></span>|@Table|<span data-ttu-id="abc3b-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="abc3b-200">TABLE_NAME</span></span>|<span data-ttu-id="abc3b-201">3</span><span class="sxs-lookup"><span data-stu-id="abc3b-201">3</span></span>|  
|<span data-ttu-id="abc3b-202">列</span><span class="sxs-lookup"><span data-stu-id="abc3b-202">Column</span></span>|@Column|<span data-ttu-id="abc3b-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="abc3b-203">COLUMN_NAME</span></span>|<span data-ttu-id="abc3b-204">4</span><span class="sxs-lookup"><span data-stu-id="abc3b-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="abc3b-205">视图</span><span class="sxs-lookup"><span data-stu-id="abc3b-205">Views</span></span>  
  
|<span data-ttu-id="abc3b-206">限制名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-206">Restriction Name</span></span>|<span data-ttu-id="abc3b-207">参数名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-207">Parameter Name</span></span>|<span data-ttu-id="abc3b-208">限制默认值</span><span class="sxs-lookup"><span data-stu-id="abc3b-208">Restriction Default</span></span>|<span data-ttu-id="abc3b-209">限制数</span><span class="sxs-lookup"><span data-stu-id="abc3b-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="abc3b-210">目录</span><span class="sxs-lookup"><span data-stu-id="abc3b-210">Catalog</span></span>|@Catalog|<span data-ttu-id="abc3b-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="abc3b-211">TABLE_CATALOG</span></span>|<span data-ttu-id="abc3b-212">1</span><span class="sxs-lookup"><span data-stu-id="abc3b-212">1</span></span>|  
|<span data-ttu-id="abc3b-213">“所有者”</span><span class="sxs-lookup"><span data-stu-id="abc3b-213">Owner</span></span>|@Owner|<span data-ttu-id="abc3b-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="abc3b-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="abc3b-215">2</span><span class="sxs-lookup"><span data-stu-id="abc3b-215">2</span></span>|  
|<span data-ttu-id="abc3b-216">表</span><span class="sxs-lookup"><span data-stu-id="abc3b-216">Table</span></span>|@Table|<span data-ttu-id="abc3b-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="abc3b-217">TABLE_NAME</span></span>|<span data-ttu-id="abc3b-218">3</span><span class="sxs-lookup"><span data-stu-id="abc3b-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="abc3b-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="abc3b-219">ViewColumns</span></span>  
  
|<span data-ttu-id="abc3b-220">限制名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-220">Restriction Name</span></span>|<span data-ttu-id="abc3b-221">参数名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-221">Parameter Name</span></span>|<span data-ttu-id="abc3b-222">限制默认值</span><span class="sxs-lookup"><span data-stu-id="abc3b-222">Restriction Default</span></span>|<span data-ttu-id="abc3b-223">限制数</span><span class="sxs-lookup"><span data-stu-id="abc3b-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="abc3b-224">目录</span><span class="sxs-lookup"><span data-stu-id="abc3b-224">Catalog</span></span>|@Catalog|<span data-ttu-id="abc3b-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="abc3b-225">VIEW_CATALOG</span></span>|<span data-ttu-id="abc3b-226">1</span><span class="sxs-lookup"><span data-stu-id="abc3b-226">1</span></span>|  
|<span data-ttu-id="abc3b-227">“所有者”</span><span class="sxs-lookup"><span data-stu-id="abc3b-227">Owner</span></span>|@Owner|<span data-ttu-id="abc3b-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="abc3b-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="abc3b-229">2</span><span class="sxs-lookup"><span data-stu-id="abc3b-229">2</span></span>|  
|<span data-ttu-id="abc3b-230">表</span><span class="sxs-lookup"><span data-stu-id="abc3b-230">Table</span></span>|@Table|<span data-ttu-id="abc3b-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="abc3b-231">VIEW_NAME</span></span>|<span data-ttu-id="abc3b-232">3</span><span class="sxs-lookup"><span data-stu-id="abc3b-232">3</span></span>|  
|<span data-ttu-id="abc3b-233">列</span><span class="sxs-lookup"><span data-stu-id="abc3b-233">Column</span></span>|@Column|<span data-ttu-id="abc3b-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="abc3b-234">COLUMN_NAME</span></span>|<span data-ttu-id="abc3b-235">4</span><span class="sxs-lookup"><span data-stu-id="abc3b-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="abc3b-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="abc3b-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="abc3b-237">限制名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-237">Restriction Name</span></span>|<span data-ttu-id="abc3b-238">参数名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-238">Parameter Name</span></span>|<span data-ttu-id="abc3b-239">限制默认值</span><span class="sxs-lookup"><span data-stu-id="abc3b-239">Restriction Default</span></span>|<span data-ttu-id="abc3b-240">限制数</span><span class="sxs-lookup"><span data-stu-id="abc3b-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="abc3b-241">目录</span><span class="sxs-lookup"><span data-stu-id="abc3b-241">Catalog</span></span>|@Catalog|<span data-ttu-id="abc3b-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="abc3b-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="abc3b-243">1</span><span class="sxs-lookup"><span data-stu-id="abc3b-243">1</span></span>|  
|<span data-ttu-id="abc3b-244">“所有者”</span><span class="sxs-lookup"><span data-stu-id="abc3b-244">Owner</span></span>|@Owner|<span data-ttu-id="abc3b-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="abc3b-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="abc3b-246">2</span><span class="sxs-lookup"><span data-stu-id="abc3b-246">2</span></span>|  
|<span data-ttu-id="abc3b-247">名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-247">Name</span></span>|@Name|<span data-ttu-id="abc3b-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="abc3b-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="abc3b-249">3</span><span class="sxs-lookup"><span data-stu-id="abc3b-249">3</span></span>|  
|<span data-ttu-id="abc3b-250">参数</span><span class="sxs-lookup"><span data-stu-id="abc3b-250">Parameter</span></span>|@Parameter|<span data-ttu-id="abc3b-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="abc3b-251">PARAMETER_NAME</span></span>|<span data-ttu-id="abc3b-252">4</span><span class="sxs-lookup"><span data-stu-id="abc3b-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="abc3b-253">过程</span><span class="sxs-lookup"><span data-stu-id="abc3b-253">Procedures</span></span>  
  
|<span data-ttu-id="abc3b-254">限制名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-254">Restriction Name</span></span>|<span data-ttu-id="abc3b-255">参数名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-255">Parameter Name</span></span>|<span data-ttu-id="abc3b-256">限制默认值</span><span class="sxs-lookup"><span data-stu-id="abc3b-256">Restriction Default</span></span>|<span data-ttu-id="abc3b-257">限制数</span><span class="sxs-lookup"><span data-stu-id="abc3b-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="abc3b-258">目录</span><span class="sxs-lookup"><span data-stu-id="abc3b-258">Catalog</span></span>|@Catalog|<span data-ttu-id="abc3b-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="abc3b-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="abc3b-260">1</span><span class="sxs-lookup"><span data-stu-id="abc3b-260">1</span></span>|  
|<span data-ttu-id="abc3b-261">“所有者”</span><span class="sxs-lookup"><span data-stu-id="abc3b-261">Owner</span></span>|@Owner|<span data-ttu-id="abc3b-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="abc3b-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="abc3b-263">2</span><span class="sxs-lookup"><span data-stu-id="abc3b-263">2</span></span>|  
|<span data-ttu-id="abc3b-264">名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-264">Name</span></span>|@Name|<span data-ttu-id="abc3b-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="abc3b-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="abc3b-266">3</span><span class="sxs-lookup"><span data-stu-id="abc3b-266">3</span></span>|  
|<span data-ttu-id="abc3b-267">类型</span><span class="sxs-lookup"><span data-stu-id="abc3b-267">Type</span></span>|@Type|<span data-ttu-id="abc3b-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="abc3b-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="abc3b-269">4</span><span class="sxs-lookup"><span data-stu-id="abc3b-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="abc3b-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="abc3b-270">IndexColumns</span></span>  
  
|<span data-ttu-id="abc3b-271">限制名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-271">Restriction Name</span></span>|<span data-ttu-id="abc3b-272">参数名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-272">Parameter Name</span></span>|<span data-ttu-id="abc3b-273">限制默认值</span><span class="sxs-lookup"><span data-stu-id="abc3b-273">Restriction Default</span></span>|<span data-ttu-id="abc3b-274">限制数</span><span class="sxs-lookup"><span data-stu-id="abc3b-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="abc3b-275">目录</span><span class="sxs-lookup"><span data-stu-id="abc3b-275">Catalog</span></span>|@Catalog|<span data-ttu-id="abc3b-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="abc3b-276">db_name()</span></span>|<span data-ttu-id="abc3b-277">1</span><span class="sxs-lookup"><span data-stu-id="abc3b-277">1</span></span>|  
|<span data-ttu-id="abc3b-278">“所有者”</span><span class="sxs-lookup"><span data-stu-id="abc3b-278">Owner</span></span>|@Owner|<span data-ttu-id="abc3b-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="abc3b-279">user_name()</span></span>|<span data-ttu-id="abc3b-280">2</span><span class="sxs-lookup"><span data-stu-id="abc3b-280">2</span></span>|  
|<span data-ttu-id="abc3b-281">表</span><span class="sxs-lookup"><span data-stu-id="abc3b-281">Table</span></span>|@Table|<span data-ttu-id="abc3b-282">o.name</span><span class="sxs-lookup"><span data-stu-id="abc3b-282">o.name</span></span>|<span data-ttu-id="abc3b-283">3</span><span class="sxs-lookup"><span data-stu-id="abc3b-283">3</span></span>|  
|<span data-ttu-id="abc3b-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="abc3b-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="abc3b-285">x.name</span><span class="sxs-lookup"><span data-stu-id="abc3b-285">x.name</span></span>|<span data-ttu-id="abc3b-286">4</span><span class="sxs-lookup"><span data-stu-id="abc3b-286">4</span></span>|  
|<span data-ttu-id="abc3b-287">列</span><span class="sxs-lookup"><span data-stu-id="abc3b-287">Column</span></span>|@Column|<span data-ttu-id="abc3b-288">c.name</span><span class="sxs-lookup"><span data-stu-id="abc3b-288">c.name</span></span>|<span data-ttu-id="abc3b-289">5</span><span class="sxs-lookup"><span data-stu-id="abc3b-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="abc3b-290">索引</span><span class="sxs-lookup"><span data-stu-id="abc3b-290">Indexes</span></span>  
  
|<span data-ttu-id="abc3b-291">限制名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-291">Restriction Name</span></span>|<span data-ttu-id="abc3b-292">参数名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-292">Parameter Name</span></span>|<span data-ttu-id="abc3b-293">限制默认值</span><span class="sxs-lookup"><span data-stu-id="abc3b-293">Restriction Default</span></span>|<span data-ttu-id="abc3b-294">限制数</span><span class="sxs-lookup"><span data-stu-id="abc3b-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="abc3b-295">目录</span><span class="sxs-lookup"><span data-stu-id="abc3b-295">Catalog</span></span>|@Catalog|<span data-ttu-id="abc3b-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="abc3b-296">db_name()</span></span>|<span data-ttu-id="abc3b-297">1</span><span class="sxs-lookup"><span data-stu-id="abc3b-297">1</span></span>|  
|<span data-ttu-id="abc3b-298">“所有者”</span><span class="sxs-lookup"><span data-stu-id="abc3b-298">Owner</span></span>|@Owner|<span data-ttu-id="abc3b-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="abc3b-299">user_name()</span></span>|<span data-ttu-id="abc3b-300">2</span><span class="sxs-lookup"><span data-stu-id="abc3b-300">2</span></span>|  
|<span data-ttu-id="abc3b-301">表</span><span class="sxs-lookup"><span data-stu-id="abc3b-301">Table</span></span>|@Table|<span data-ttu-id="abc3b-302">o.name</span><span class="sxs-lookup"><span data-stu-id="abc3b-302">o.name</span></span>|<span data-ttu-id="abc3b-303">3</span><span class="sxs-lookup"><span data-stu-id="abc3b-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="abc3b-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="abc3b-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="abc3b-305">限制名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-305">Restriction Name</span></span>|<span data-ttu-id="abc3b-306">参数名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-306">Parameter Name</span></span>|<span data-ttu-id="abc3b-307">限制默认值</span><span class="sxs-lookup"><span data-stu-id="abc3b-307">Restriction Default</span></span>|<span data-ttu-id="abc3b-308">限制数</span><span class="sxs-lookup"><span data-stu-id="abc3b-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="abc3b-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="abc3b-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="abc3b-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="abc3b-310">assemblies.name</span></span>|<span data-ttu-id="abc3b-311">1</span><span class="sxs-lookup"><span data-stu-id="abc3b-311">1</span></span>|  
|<span data-ttu-id="abc3b-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="abc3b-312">udt_name</span></span>|@UDTName|<span data-ttu-id="abc3b-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="abc3b-313">types.assembly_class</span></span>|<span data-ttu-id="abc3b-314">2</span><span class="sxs-lookup"><span data-stu-id="abc3b-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="abc3b-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="abc3b-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="abc3b-316">限制名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-316">Restriction Name</span></span>|<span data-ttu-id="abc3b-317">参数名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-317">Parameter Name</span></span>|<span data-ttu-id="abc3b-318">限制默认值</span><span class="sxs-lookup"><span data-stu-id="abc3b-318">Restriction Default</span></span>|<span data-ttu-id="abc3b-319">限制数</span><span class="sxs-lookup"><span data-stu-id="abc3b-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="abc3b-320">目录</span><span class="sxs-lookup"><span data-stu-id="abc3b-320">Catalog</span></span>|@Catalog|<span data-ttu-id="abc3b-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="abc3b-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="abc3b-322">1</span><span class="sxs-lookup"><span data-stu-id="abc3b-322">1</span></span>|  
|<span data-ttu-id="abc3b-323">“所有者”</span><span class="sxs-lookup"><span data-stu-id="abc3b-323">Owner</span></span>|@Owner|<span data-ttu-id="abc3b-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="abc3b-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="abc3b-325">2</span><span class="sxs-lookup"><span data-stu-id="abc3b-325">2</span></span>|  
|<span data-ttu-id="abc3b-326">表</span><span class="sxs-lookup"><span data-stu-id="abc3b-326">Table</span></span>|@Table|<span data-ttu-id="abc3b-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="abc3b-327">TABLE_NAME</span></span>|<span data-ttu-id="abc3b-328">3</span><span class="sxs-lookup"><span data-stu-id="abc3b-328">3</span></span>|  
|<span data-ttu-id="abc3b-329">名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-329">Name</span></span>|@Name|<span data-ttu-id="abc3b-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="abc3b-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="abc3b-331">4</span><span class="sxs-lookup"><span data-stu-id="abc3b-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="abc3b-332">SQL Server 2008     </span><span class="sxs-lookup"><span data-stu-id="abc3b-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="abc3b-333">下表列出了 SQL Server 2008 架构集合的限制。</span><span class="sxs-lookup"><span data-stu-id="abc3b-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="abc3b-334">这些限制从 .NET Framework 版本 3.5 SP1 和 SQL Server 2008 开始生效。</span><span class="sxs-lookup"><span data-stu-id="abc3b-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="abc3b-335">.NET Framework 和 SQL Server 的早期版本不支持这些限制。</span><span class="sxs-lookup"><span data-stu-id="abc3b-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="abc3b-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="abc3b-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="abc3b-337">限制名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-337">Restriction Name</span></span>|<span data-ttu-id="abc3b-338">参数名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-338">Parameter Name</span></span>|<span data-ttu-id="abc3b-339">限制默认值</span><span class="sxs-lookup"><span data-stu-id="abc3b-339">Restriction Default</span></span>|<span data-ttu-id="abc3b-340">限制数</span><span class="sxs-lookup"><span data-stu-id="abc3b-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="abc3b-341">目录</span><span class="sxs-lookup"><span data-stu-id="abc3b-341">Catalog</span></span>|@Catalog|<span data-ttu-id="abc3b-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="abc3b-342">TABLE_CATALOG</span></span>|<span data-ttu-id="abc3b-343">1</span><span class="sxs-lookup"><span data-stu-id="abc3b-343">1</span></span>|  
|<span data-ttu-id="abc3b-344">“所有者”</span><span class="sxs-lookup"><span data-stu-id="abc3b-344">Owner</span></span>|@Owner|<span data-ttu-id="abc3b-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="abc3b-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="abc3b-346">2</span><span class="sxs-lookup"><span data-stu-id="abc3b-346">2</span></span>|  
|<span data-ttu-id="abc3b-347">表</span><span class="sxs-lookup"><span data-stu-id="abc3b-347">Table</span></span>|@Table|<span data-ttu-id="abc3b-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="abc3b-348">TABLE_NAME</span></span>|<span data-ttu-id="abc3b-349">3</span><span class="sxs-lookup"><span data-stu-id="abc3b-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="abc3b-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="abc3b-350">AllColumns</span></span>  
  
|<span data-ttu-id="abc3b-351">限制名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-351">Restriction Name</span></span>|<span data-ttu-id="abc3b-352">参数名称</span><span class="sxs-lookup"><span data-stu-id="abc3b-352">Parameter Name</span></span>|<span data-ttu-id="abc3b-353">限制默认值</span><span class="sxs-lookup"><span data-stu-id="abc3b-353">Restriction Default</span></span>|<span data-ttu-id="abc3b-354">限制数</span><span class="sxs-lookup"><span data-stu-id="abc3b-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="abc3b-355">目录</span><span class="sxs-lookup"><span data-stu-id="abc3b-355">Catalog</span></span>|@Catalog|<span data-ttu-id="abc3b-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="abc3b-356">TABLE_CATALOG</span></span>|<span data-ttu-id="abc3b-357">1</span><span class="sxs-lookup"><span data-stu-id="abc3b-357">1</span></span>|  
|<span data-ttu-id="abc3b-358">“所有者”</span><span class="sxs-lookup"><span data-stu-id="abc3b-358">Owner</span></span>|@Owner|<span data-ttu-id="abc3b-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="abc3b-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="abc3b-360">2</span><span class="sxs-lookup"><span data-stu-id="abc3b-360">2</span></span>|  
|<span data-ttu-id="abc3b-361">表</span><span class="sxs-lookup"><span data-stu-id="abc3b-361">Table</span></span>|@Table|<span data-ttu-id="abc3b-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="abc3b-362">TABLE_NAME</span></span>|<span data-ttu-id="abc3b-363">3</span><span class="sxs-lookup"><span data-stu-id="abc3b-363">3</span></span>|  
|<span data-ttu-id="abc3b-364">列</span><span class="sxs-lookup"><span data-stu-id="abc3b-364">Column</span></span>|@Column|<span data-ttu-id="abc3b-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="abc3b-365">COLUMN_NAME</span></span>|<span data-ttu-id="abc3b-366">4</span><span class="sxs-lookup"><span data-stu-id="abc3b-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="abc3b-367">另请参阅</span><span class="sxs-lookup"><span data-stu-id="abc3b-367">See also</span></span>

- [<span data-ttu-id="abc3b-368">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="abc3b-368">ADO.NET Overview</span></span>](ado-net-overview.md)
