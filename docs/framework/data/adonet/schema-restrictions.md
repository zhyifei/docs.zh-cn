---
title: 架构限制
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 040ecd8a2ce223f89601de735b77ccc81638c7af
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43417077"
---
# <a name="schema-restrictions"></a><span data-ttu-id="a0697-102">架构限制</span><span class="sxs-lookup"><span data-stu-id="a0697-102">Schema Restrictions</span></span>
<span data-ttu-id="a0697-103">第二个可选参数**GetSchema**方法将返回用于限制架构信息的量的限制，并将它传递到**GetSchema**方法作为一个字符串数组.</span><span class="sxs-lookup"><span data-stu-id="a0697-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="a0697-104">在数组中的位置确定可以传递的值，这等效于限制数。</span><span class="sxs-lookup"><span data-stu-id="a0697-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="a0697-105">例如，下表说明使用适用于 SQL Server 的 .NET Framework 数据提供程序时“Tables”架构集合支持的限制。</span><span class="sxs-lookup"><span data-stu-id="a0697-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="a0697-106">SQL Server 架构集合的其他限制在本主题的结尾处列出。</span><span class="sxs-lookup"><span data-stu-id="a0697-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="a0697-107">限制名称</span><span class="sxs-lookup"><span data-stu-id="a0697-107">Restriction Name</span></span>|<span data-ttu-id="a0697-108">参数名称</span><span class="sxs-lookup"><span data-stu-id="a0697-108">Parameter Name</span></span>|<span data-ttu-id="a0697-109">限制默认值</span><span class="sxs-lookup"><span data-stu-id="a0697-109">Restriction Default</span></span>|<span data-ttu-id="a0697-110">限制数</span><span class="sxs-lookup"><span data-stu-id="a0697-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a0697-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="a0697-111">Catalog</span></span>|@Catalog|<span data-ttu-id="a0697-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a0697-112">TABLE_CATALOG</span></span>|<span data-ttu-id="a0697-113">1</span><span class="sxs-lookup"><span data-stu-id="a0697-113">1</span></span>|  
|<span data-ttu-id="a0697-114">Owner</span><span class="sxs-lookup"><span data-stu-id="a0697-114">Owner</span></span>|@Owner|<span data-ttu-id="a0697-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a0697-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="a0697-116">2</span><span class="sxs-lookup"><span data-stu-id="a0697-116">2</span></span>|  
|<span data-ttu-id="a0697-117">表</span><span class="sxs-lookup"><span data-stu-id="a0697-117">Table</span></span>|@Name|<span data-ttu-id="a0697-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a0697-118">TABLE_NAME</span></span>|<span data-ttu-id="a0697-119">3</span><span class="sxs-lookup"><span data-stu-id="a0697-119">3</span></span>|  
|<span data-ttu-id="a0697-120">TableType</span><span class="sxs-lookup"><span data-stu-id="a0697-120">TableType</span></span>|@TableType|<span data-ttu-id="a0697-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="a0697-121">TABLE_TYPE</span></span>|<span data-ttu-id="a0697-122">4</span><span class="sxs-lookup"><span data-stu-id="a0697-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="a0697-123">指定限制值</span><span class="sxs-lookup"><span data-stu-id="a0697-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="a0697-124">要使用“Tables”架构集合的一个限制，只需创建一个包含四个元素的字符串数组，然后在与限制数匹配的元素中填充值。</span><span class="sxs-lookup"><span data-stu-id="a0697-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="a0697-125">例如，若要限制的表返回的**GetSchema**仅在"Sales"架构中，这些表的方法将其传递给之前设置为"Sales"数组的第二个元素**GetSchema**方法。</span><span class="sxs-lookup"><span data-stu-id="a0697-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0697-126">`SqlClient` 和 `OracleClient` 的限制集合还有附加的 `ParameterName` 列。</span><span class="sxs-lookup"><span data-stu-id="a0697-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="a0697-127">为了向后兼容，仍提供限制默认列，但是目前忽略该列。</span><span class="sxs-lookup"><span data-stu-id="a0697-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="a0697-128">在指定限制值时，应使用参数化查询（而不是字符串替换）来最大程度地降低受到 SQL 注入式攻击的风险。</span><span class="sxs-lookup"><span data-stu-id="a0697-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0697-129">数组中的元素数必须小于或等于指定架构集合支持的限制数，否则，将引发 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="a0697-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="a0697-130">可以小于最大限制数。</span><span class="sxs-lookup"><span data-stu-id="a0697-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="a0697-131">缺少的限制假定为空（无限制）。</span><span class="sxs-lookup"><span data-stu-id="a0697-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="a0697-132">您可以查询的.NET Framework 托管提供程序来确定受支持的限制列表中，通过调用**GetSchema**方法替换为"限制"限制架构集合的名称。</span><span class="sxs-lookup"><span data-stu-id="a0697-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="a0697-133">此时将返回 <xref:System.Data.DataTable>，包含集合名称、限制名称、默认限制值和限制数的列表。</span><span class="sxs-lookup"><span data-stu-id="a0697-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="a0697-134">示例</span><span class="sxs-lookup"><span data-stu-id="a0697-134">Example</span></span>  
 <span data-ttu-id="a0697-135">下面的示例演示如何使用<xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>的 SQL Server 的.NET Framework 数据提供程序方法<xref:System.Data.SqlClient.SqlConnection>类来检索有关的所有表中包含的架构信息**AdventureWorks**示例数据库，并且能够限制的信息返回到"Sales"的架构中的这些表：</span><span class="sxs-lookup"><span data-stu-id="a0697-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="a0697-136">SQL Server 架构限制</span><span class="sxs-lookup"><span data-stu-id="a0697-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="a0697-137">下表列出了 SQL Server 架构集合的限制。</span><span class="sxs-lookup"><span data-stu-id="a0697-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="a0697-138">Users</span><span class="sxs-lookup"><span data-stu-id="a0697-138">Users</span></span>  
  
|<span data-ttu-id="a0697-139">限制名称</span><span class="sxs-lookup"><span data-stu-id="a0697-139">Restriction Name</span></span>|<span data-ttu-id="a0697-140">参数名称</span><span class="sxs-lookup"><span data-stu-id="a0697-140">Parameter Name</span></span>|<span data-ttu-id="a0697-141">限制默认值</span><span class="sxs-lookup"><span data-stu-id="a0697-141">Restriction Default</span></span>|<span data-ttu-id="a0697-142">限制数</span><span class="sxs-lookup"><span data-stu-id="a0697-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a0697-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="a0697-143">User_Name</span></span>|@Name|<span data-ttu-id="a0697-144">name</span><span class="sxs-lookup"><span data-stu-id="a0697-144">name</span></span>|<span data-ttu-id="a0697-145">1</span><span class="sxs-lookup"><span data-stu-id="a0697-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="a0697-146">数据库</span><span class="sxs-lookup"><span data-stu-id="a0697-146">Databases</span></span>  
  
|<span data-ttu-id="a0697-147">限制名称</span><span class="sxs-lookup"><span data-stu-id="a0697-147">Restriction Name</span></span>|<span data-ttu-id="a0697-148">参数名称</span><span class="sxs-lookup"><span data-stu-id="a0697-148">Parameter Name</span></span>|<span data-ttu-id="a0697-149">限制默认值</span><span class="sxs-lookup"><span data-stu-id="a0697-149">Restriction Default</span></span>|<span data-ttu-id="a0697-150">限制数</span><span class="sxs-lookup"><span data-stu-id="a0697-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a0697-151">name</span><span class="sxs-lookup"><span data-stu-id="a0697-151">Name</span></span>|@Name|<span data-ttu-id="a0697-152">name</span><span class="sxs-lookup"><span data-stu-id="a0697-152">Name</span></span>|<span data-ttu-id="a0697-153">1</span><span class="sxs-lookup"><span data-stu-id="a0697-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="a0697-154">表</span><span class="sxs-lookup"><span data-stu-id="a0697-154">Tables</span></span>  
  
|<span data-ttu-id="a0697-155">限制名称</span><span class="sxs-lookup"><span data-stu-id="a0697-155">Restriction Name</span></span>|<span data-ttu-id="a0697-156">参数名称</span><span class="sxs-lookup"><span data-stu-id="a0697-156">Parameter Name</span></span>|<span data-ttu-id="a0697-157">限制默认值</span><span class="sxs-lookup"><span data-stu-id="a0697-157">Restriction Default</span></span>|<span data-ttu-id="a0697-158">限制数</span><span class="sxs-lookup"><span data-stu-id="a0697-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a0697-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="a0697-159">Catalog</span></span>|@Catalog|<span data-ttu-id="a0697-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a0697-160">TABLE_CATALOG</span></span>|<span data-ttu-id="a0697-161">1</span><span class="sxs-lookup"><span data-stu-id="a0697-161">1</span></span>|  
|<span data-ttu-id="a0697-162">Owner</span><span class="sxs-lookup"><span data-stu-id="a0697-162">Owner</span></span>|@Owner|<span data-ttu-id="a0697-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a0697-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="a0697-164">2</span><span class="sxs-lookup"><span data-stu-id="a0697-164">2</span></span>|  
|<span data-ttu-id="a0697-165">表</span><span class="sxs-lookup"><span data-stu-id="a0697-165">Table</span></span>|@Name|<span data-ttu-id="a0697-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a0697-166">TABLE_NAME</span></span>|<span data-ttu-id="a0697-167">3</span><span class="sxs-lookup"><span data-stu-id="a0697-167">3</span></span>|  
|<span data-ttu-id="a0697-168">TableType</span><span class="sxs-lookup"><span data-stu-id="a0697-168">TableType</span></span>|@TableType|<span data-ttu-id="a0697-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="a0697-169">TABLE_TYPE</span></span>|<span data-ttu-id="a0697-170">4</span><span class="sxs-lookup"><span data-stu-id="a0697-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="a0697-171">Columns</span><span class="sxs-lookup"><span data-stu-id="a0697-171">Columns</span></span>  
  
|<span data-ttu-id="a0697-172">限制名称</span><span class="sxs-lookup"><span data-stu-id="a0697-172">Restriction Name</span></span>|<span data-ttu-id="a0697-173">参数名称</span><span class="sxs-lookup"><span data-stu-id="a0697-173">Parameter Name</span></span>|<span data-ttu-id="a0697-174">限制默认值</span><span class="sxs-lookup"><span data-stu-id="a0697-174">Restriction Default</span></span>|<span data-ttu-id="a0697-175">限制数</span><span class="sxs-lookup"><span data-stu-id="a0697-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a0697-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="a0697-176">Catalog</span></span>|@Catalog|<span data-ttu-id="a0697-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a0697-177">TABLE_CATALOG</span></span>|<span data-ttu-id="a0697-178">1</span><span class="sxs-lookup"><span data-stu-id="a0697-178">1</span></span>|  
|<span data-ttu-id="a0697-179">Owner</span><span class="sxs-lookup"><span data-stu-id="a0697-179">Owner</span></span>|@Owner|<span data-ttu-id="a0697-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a0697-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="a0697-181">2</span><span class="sxs-lookup"><span data-stu-id="a0697-181">2</span></span>|  
|<span data-ttu-id="a0697-182">表</span><span class="sxs-lookup"><span data-stu-id="a0697-182">Table</span></span>|@Table|<span data-ttu-id="a0697-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a0697-183">TABLE_NAME</span></span>|<span data-ttu-id="a0697-184">3</span><span class="sxs-lookup"><span data-stu-id="a0697-184">3</span></span>|  
|<span data-ttu-id="a0697-185">列</span><span class="sxs-lookup"><span data-stu-id="a0697-185">Column</span></span>|@Column|<span data-ttu-id="a0697-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a0697-186">COLUMN_NAME</span></span>|<span data-ttu-id="a0697-187">4</span><span class="sxs-lookup"><span data-stu-id="a0697-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="a0697-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="a0697-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="a0697-189">限制名称</span><span class="sxs-lookup"><span data-stu-id="a0697-189">Restriction Name</span></span>|<span data-ttu-id="a0697-190">参数名称</span><span class="sxs-lookup"><span data-stu-id="a0697-190">Parameter Name</span></span>|<span data-ttu-id="a0697-191">限制默认值</span><span class="sxs-lookup"><span data-stu-id="a0697-191">Restriction Default</span></span>|<span data-ttu-id="a0697-192">限制数</span><span class="sxs-lookup"><span data-stu-id="a0697-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a0697-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="a0697-193">Catalog</span></span>|@Catalog|<span data-ttu-id="a0697-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a0697-194">TABLE_CATALOG</span></span>|<span data-ttu-id="a0697-195">1</span><span class="sxs-lookup"><span data-stu-id="a0697-195">1</span></span>|  
|<span data-ttu-id="a0697-196">Owner</span><span class="sxs-lookup"><span data-stu-id="a0697-196">Owner</span></span>|@Owner|<span data-ttu-id="a0697-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a0697-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="a0697-198">2</span><span class="sxs-lookup"><span data-stu-id="a0697-198">2</span></span>|  
|<span data-ttu-id="a0697-199">表</span><span class="sxs-lookup"><span data-stu-id="a0697-199">Table</span></span>|@Table|<span data-ttu-id="a0697-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a0697-200">TABLE_NAME</span></span>|<span data-ttu-id="a0697-201">3</span><span class="sxs-lookup"><span data-stu-id="a0697-201">3</span></span>|  
|<span data-ttu-id="a0697-202">列</span><span class="sxs-lookup"><span data-stu-id="a0697-202">Column</span></span>|@Column|<span data-ttu-id="a0697-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a0697-203">COLUMN_NAME</span></span>|<span data-ttu-id="a0697-204">4</span><span class="sxs-lookup"><span data-stu-id="a0697-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="a0697-205">视图</span><span class="sxs-lookup"><span data-stu-id="a0697-205">Views</span></span>  
  
|<span data-ttu-id="a0697-206">限制名称</span><span class="sxs-lookup"><span data-stu-id="a0697-206">Restriction Name</span></span>|<span data-ttu-id="a0697-207">参数名称</span><span class="sxs-lookup"><span data-stu-id="a0697-207">Parameter Name</span></span>|<span data-ttu-id="a0697-208">限制默认值</span><span class="sxs-lookup"><span data-stu-id="a0697-208">Restriction Default</span></span>|<span data-ttu-id="a0697-209">限制数</span><span class="sxs-lookup"><span data-stu-id="a0697-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a0697-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="a0697-210">Catalog</span></span>|@Catalog|<span data-ttu-id="a0697-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a0697-211">TABLE_CATALOG</span></span>|<span data-ttu-id="a0697-212">1</span><span class="sxs-lookup"><span data-stu-id="a0697-212">1</span></span>|  
|<span data-ttu-id="a0697-213">Owner</span><span class="sxs-lookup"><span data-stu-id="a0697-213">Owner</span></span>|@Owner|<span data-ttu-id="a0697-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a0697-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="a0697-215">2</span><span class="sxs-lookup"><span data-stu-id="a0697-215">2</span></span>|  
|<span data-ttu-id="a0697-216">表</span><span class="sxs-lookup"><span data-stu-id="a0697-216">Table</span></span>|@Table|<span data-ttu-id="a0697-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a0697-217">TABLE_NAME</span></span>|<span data-ttu-id="a0697-218">3</span><span class="sxs-lookup"><span data-stu-id="a0697-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="a0697-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="a0697-219">ViewColumns</span></span>  
  
|<span data-ttu-id="a0697-220">限制名称</span><span class="sxs-lookup"><span data-stu-id="a0697-220">Restriction Name</span></span>|<span data-ttu-id="a0697-221">参数名称</span><span class="sxs-lookup"><span data-stu-id="a0697-221">Parameter Name</span></span>|<span data-ttu-id="a0697-222">限制默认值</span><span class="sxs-lookup"><span data-stu-id="a0697-222">Restriction Default</span></span>|<span data-ttu-id="a0697-223">限制数</span><span class="sxs-lookup"><span data-stu-id="a0697-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a0697-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="a0697-224">Catalog</span></span>|@Catalog|<span data-ttu-id="a0697-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a0697-225">VIEW_CATALOG</span></span>|<span data-ttu-id="a0697-226">1</span><span class="sxs-lookup"><span data-stu-id="a0697-226">1</span></span>|  
|<span data-ttu-id="a0697-227">Owner</span><span class="sxs-lookup"><span data-stu-id="a0697-227">Owner</span></span>|@Owner|<span data-ttu-id="a0697-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a0697-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="a0697-229">2</span><span class="sxs-lookup"><span data-stu-id="a0697-229">2</span></span>|  
|<span data-ttu-id="a0697-230">表</span><span class="sxs-lookup"><span data-stu-id="a0697-230">Table</span></span>|@Table|<span data-ttu-id="a0697-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="a0697-231">VIEW_NAME</span></span>|<span data-ttu-id="a0697-232">3</span><span class="sxs-lookup"><span data-stu-id="a0697-232">3</span></span>|  
|<span data-ttu-id="a0697-233">列</span><span class="sxs-lookup"><span data-stu-id="a0697-233">Column</span></span>|@Column|<span data-ttu-id="a0697-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a0697-234">COLUMN_NAME</span></span>|<span data-ttu-id="a0697-235">4</span><span class="sxs-lookup"><span data-stu-id="a0697-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="a0697-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="a0697-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="a0697-237">限制名称</span><span class="sxs-lookup"><span data-stu-id="a0697-237">Restriction Name</span></span>|<span data-ttu-id="a0697-238">参数名称</span><span class="sxs-lookup"><span data-stu-id="a0697-238">Parameter Name</span></span>|<span data-ttu-id="a0697-239">限制默认值</span><span class="sxs-lookup"><span data-stu-id="a0697-239">Restriction Default</span></span>|<span data-ttu-id="a0697-240">限制数</span><span class="sxs-lookup"><span data-stu-id="a0697-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a0697-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="a0697-241">Catalog</span></span>|@Catalog|<span data-ttu-id="a0697-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a0697-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="a0697-243">1</span><span class="sxs-lookup"><span data-stu-id="a0697-243">1</span></span>|  
|<span data-ttu-id="a0697-244">Owner</span><span class="sxs-lookup"><span data-stu-id="a0697-244">Owner</span></span>|@Owner|<span data-ttu-id="a0697-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a0697-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="a0697-246">2</span><span class="sxs-lookup"><span data-stu-id="a0697-246">2</span></span>|  
|<span data-ttu-id="a0697-247">name</span><span class="sxs-lookup"><span data-stu-id="a0697-247">Name</span></span>|@Name|<span data-ttu-id="a0697-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="a0697-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="a0697-249">3</span><span class="sxs-lookup"><span data-stu-id="a0697-249">3</span></span>|  
|<span data-ttu-id="a0697-250">参数</span><span class="sxs-lookup"><span data-stu-id="a0697-250">Parameter</span></span>|@Parameter|<span data-ttu-id="a0697-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="a0697-251">PARAMETER_NAME</span></span>|<span data-ttu-id="a0697-252">4</span><span class="sxs-lookup"><span data-stu-id="a0697-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="a0697-253">过程</span><span class="sxs-lookup"><span data-stu-id="a0697-253">Procedures</span></span>  
  
|<span data-ttu-id="a0697-254">限制名称</span><span class="sxs-lookup"><span data-stu-id="a0697-254">Restriction Name</span></span>|<span data-ttu-id="a0697-255">参数名称</span><span class="sxs-lookup"><span data-stu-id="a0697-255">Parameter Name</span></span>|<span data-ttu-id="a0697-256">限制默认值</span><span class="sxs-lookup"><span data-stu-id="a0697-256">Restriction Default</span></span>|<span data-ttu-id="a0697-257">限制数</span><span class="sxs-lookup"><span data-stu-id="a0697-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a0697-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="a0697-258">Catalog</span></span>|@Catalog|<span data-ttu-id="a0697-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a0697-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="a0697-260">1</span><span class="sxs-lookup"><span data-stu-id="a0697-260">1</span></span>|  
|<span data-ttu-id="a0697-261">Owner</span><span class="sxs-lookup"><span data-stu-id="a0697-261">Owner</span></span>|@Owner|<span data-ttu-id="a0697-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a0697-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="a0697-263">2</span><span class="sxs-lookup"><span data-stu-id="a0697-263">2</span></span>|  
|<span data-ttu-id="a0697-264">name</span><span class="sxs-lookup"><span data-stu-id="a0697-264">Name</span></span>|@Name|<span data-ttu-id="a0697-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="a0697-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="a0697-266">3</span><span class="sxs-lookup"><span data-stu-id="a0697-266">3</span></span>|  
|<span data-ttu-id="a0697-267">类型</span><span class="sxs-lookup"><span data-stu-id="a0697-267">Type</span></span>|@Type|<span data-ttu-id="a0697-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="a0697-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="a0697-269">4</span><span class="sxs-lookup"><span data-stu-id="a0697-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="a0697-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="a0697-270">IndexColumns</span></span>  
  
|<span data-ttu-id="a0697-271">限制名称</span><span class="sxs-lookup"><span data-stu-id="a0697-271">Restriction Name</span></span>|<span data-ttu-id="a0697-272">参数名称</span><span class="sxs-lookup"><span data-stu-id="a0697-272">Parameter Name</span></span>|<span data-ttu-id="a0697-273">限制默认值</span><span class="sxs-lookup"><span data-stu-id="a0697-273">Restriction Default</span></span>|<span data-ttu-id="a0697-274">限制数</span><span class="sxs-lookup"><span data-stu-id="a0697-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a0697-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="a0697-275">Catalog</span></span>|@Catalog|<span data-ttu-id="a0697-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="a0697-276">db_name()</span></span>|<span data-ttu-id="a0697-277">1</span><span class="sxs-lookup"><span data-stu-id="a0697-277">1</span></span>|  
|<span data-ttu-id="a0697-278">Owner</span><span class="sxs-lookup"><span data-stu-id="a0697-278">Owner</span></span>|@Owner|<span data-ttu-id="a0697-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="a0697-279">user_name()</span></span>|<span data-ttu-id="a0697-280">2</span><span class="sxs-lookup"><span data-stu-id="a0697-280">2</span></span>|  
|<span data-ttu-id="a0697-281">表</span><span class="sxs-lookup"><span data-stu-id="a0697-281">Table</span></span>|@Table|<span data-ttu-id="a0697-282">o.name</span><span class="sxs-lookup"><span data-stu-id="a0697-282">o.name</span></span>|<span data-ttu-id="a0697-283">3</span><span class="sxs-lookup"><span data-stu-id="a0697-283">3</span></span>|  
|<span data-ttu-id="a0697-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="a0697-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="a0697-285">x.name</span><span class="sxs-lookup"><span data-stu-id="a0697-285">x.name</span></span>|<span data-ttu-id="a0697-286">4</span><span class="sxs-lookup"><span data-stu-id="a0697-286">4</span></span>|  
|<span data-ttu-id="a0697-287">列</span><span class="sxs-lookup"><span data-stu-id="a0697-287">Column</span></span>|@Column|<span data-ttu-id="a0697-288">c.name</span><span class="sxs-lookup"><span data-stu-id="a0697-288">c.name</span></span>|<span data-ttu-id="a0697-289">5</span><span class="sxs-lookup"><span data-stu-id="a0697-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="a0697-290">索引</span><span class="sxs-lookup"><span data-stu-id="a0697-290">Indexes</span></span>  
  
|<span data-ttu-id="a0697-291">限制名称</span><span class="sxs-lookup"><span data-stu-id="a0697-291">Restriction Name</span></span>|<span data-ttu-id="a0697-292">参数名称</span><span class="sxs-lookup"><span data-stu-id="a0697-292">Parameter Name</span></span>|<span data-ttu-id="a0697-293">限制默认值</span><span class="sxs-lookup"><span data-stu-id="a0697-293">Restriction Default</span></span>|<span data-ttu-id="a0697-294">限制数</span><span class="sxs-lookup"><span data-stu-id="a0697-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a0697-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="a0697-295">Catalog</span></span>|@Catalog|<span data-ttu-id="a0697-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="a0697-296">db_name()</span></span>|<span data-ttu-id="a0697-297">1</span><span class="sxs-lookup"><span data-stu-id="a0697-297">1</span></span>|  
|<span data-ttu-id="a0697-298">Owner</span><span class="sxs-lookup"><span data-stu-id="a0697-298">Owner</span></span>|@Owner|<span data-ttu-id="a0697-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="a0697-299">user_name()</span></span>|<span data-ttu-id="a0697-300">2</span><span class="sxs-lookup"><span data-stu-id="a0697-300">2</span></span>|  
|<span data-ttu-id="a0697-301">表</span><span class="sxs-lookup"><span data-stu-id="a0697-301">Table</span></span>|@Table|<span data-ttu-id="a0697-302">o.name</span><span class="sxs-lookup"><span data-stu-id="a0697-302">o.name</span></span>|<span data-ttu-id="a0697-303">3</span><span class="sxs-lookup"><span data-stu-id="a0697-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="a0697-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="a0697-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="a0697-305">限制名称</span><span class="sxs-lookup"><span data-stu-id="a0697-305">Restriction Name</span></span>|<span data-ttu-id="a0697-306">参数名称</span><span class="sxs-lookup"><span data-stu-id="a0697-306">Parameter Name</span></span>|<span data-ttu-id="a0697-307">限制默认值</span><span class="sxs-lookup"><span data-stu-id="a0697-307">Restriction Default</span></span>|<span data-ttu-id="a0697-308">限制数</span><span class="sxs-lookup"><span data-stu-id="a0697-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a0697-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="a0697-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="a0697-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="a0697-310">assemblies.name</span></span>|<span data-ttu-id="a0697-311">1</span><span class="sxs-lookup"><span data-stu-id="a0697-311">1</span></span>|  
|<span data-ttu-id="a0697-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="a0697-312">udt_name</span></span>|@UDTName|<span data-ttu-id="a0697-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="a0697-313">types.assembly_class</span></span>|<span data-ttu-id="a0697-314">2</span><span class="sxs-lookup"><span data-stu-id="a0697-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="a0697-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="a0697-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="a0697-316">限制名称</span><span class="sxs-lookup"><span data-stu-id="a0697-316">Restriction Name</span></span>|<span data-ttu-id="a0697-317">参数名称</span><span class="sxs-lookup"><span data-stu-id="a0697-317">Parameter Name</span></span>|<span data-ttu-id="a0697-318">限制默认值</span><span class="sxs-lookup"><span data-stu-id="a0697-318">Restriction Default</span></span>|<span data-ttu-id="a0697-319">限制数</span><span class="sxs-lookup"><span data-stu-id="a0697-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a0697-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="a0697-320">Catalog</span></span>|@Catalog|<span data-ttu-id="a0697-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a0697-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="a0697-322">1</span><span class="sxs-lookup"><span data-stu-id="a0697-322">1</span></span>|  
|<span data-ttu-id="a0697-323">Owner</span><span class="sxs-lookup"><span data-stu-id="a0697-323">Owner</span></span>|@Owner|<span data-ttu-id="a0697-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a0697-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="a0697-325">2</span><span class="sxs-lookup"><span data-stu-id="a0697-325">2</span></span>|  
|<span data-ttu-id="a0697-326">表</span><span class="sxs-lookup"><span data-stu-id="a0697-326">Table</span></span>|@Table|<span data-ttu-id="a0697-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a0697-327">TABLE_NAME</span></span>|<span data-ttu-id="a0697-328">3</span><span class="sxs-lookup"><span data-stu-id="a0697-328">3</span></span>|  
|<span data-ttu-id="a0697-329">name</span><span class="sxs-lookup"><span data-stu-id="a0697-329">Name</span></span>|@Name|<span data-ttu-id="a0697-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="a0697-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="a0697-331">4</span><span class="sxs-lookup"><span data-stu-id="a0697-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="a0697-332">SQL Server 2008     </span><span class="sxs-lookup"><span data-stu-id="a0697-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="a0697-333">下表列出了 SQL Server 2008 架构集合的限制。</span><span class="sxs-lookup"><span data-stu-id="a0697-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="a0697-334">这些限制从 .NET Framework 版本 3.5 SP1 和 SQL Server 2008 开始生效。</span><span class="sxs-lookup"><span data-stu-id="a0697-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="a0697-335">.NET Framework 和 SQL Server 的早期版本不支持这些限制。</span><span class="sxs-lookup"><span data-stu-id="a0697-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="a0697-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="a0697-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="a0697-337">限制名称</span><span class="sxs-lookup"><span data-stu-id="a0697-337">Restriction Name</span></span>|<span data-ttu-id="a0697-338">参数名称</span><span class="sxs-lookup"><span data-stu-id="a0697-338">Parameter Name</span></span>|<span data-ttu-id="a0697-339">限制默认值</span><span class="sxs-lookup"><span data-stu-id="a0697-339">Restriction Default</span></span>|<span data-ttu-id="a0697-340">限制数</span><span class="sxs-lookup"><span data-stu-id="a0697-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a0697-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="a0697-341">Catalog</span></span>|@Catalog|<span data-ttu-id="a0697-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a0697-342">TABLE_CATALOG</span></span>|<span data-ttu-id="a0697-343">1</span><span class="sxs-lookup"><span data-stu-id="a0697-343">1</span></span>|  
|<span data-ttu-id="a0697-344">Owner</span><span class="sxs-lookup"><span data-stu-id="a0697-344">Owner</span></span>|@Owner|<span data-ttu-id="a0697-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a0697-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="a0697-346">2</span><span class="sxs-lookup"><span data-stu-id="a0697-346">2</span></span>|  
|<span data-ttu-id="a0697-347">表</span><span class="sxs-lookup"><span data-stu-id="a0697-347">Table</span></span>|@Table|<span data-ttu-id="a0697-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a0697-348">TABLE_NAME</span></span>|<span data-ttu-id="a0697-349">3</span><span class="sxs-lookup"><span data-stu-id="a0697-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="a0697-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="a0697-350">AllColumns</span></span>  
  
|<span data-ttu-id="a0697-351">限制名称</span><span class="sxs-lookup"><span data-stu-id="a0697-351">Restriction Name</span></span>|<span data-ttu-id="a0697-352">参数名称</span><span class="sxs-lookup"><span data-stu-id="a0697-352">Parameter Name</span></span>|<span data-ttu-id="a0697-353">限制默认值</span><span class="sxs-lookup"><span data-stu-id="a0697-353">Restriction Default</span></span>|<span data-ttu-id="a0697-354">限制数</span><span class="sxs-lookup"><span data-stu-id="a0697-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="a0697-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="a0697-355">Catalog</span></span>|@Catalog|<span data-ttu-id="a0697-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a0697-356">TABLE_CATALOG</span></span>|<span data-ttu-id="a0697-357">1</span><span class="sxs-lookup"><span data-stu-id="a0697-357">1</span></span>|  
|<span data-ttu-id="a0697-358">Owner</span><span class="sxs-lookup"><span data-stu-id="a0697-358">Owner</span></span>|@Owner|<span data-ttu-id="a0697-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="a0697-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="a0697-360">2</span><span class="sxs-lookup"><span data-stu-id="a0697-360">2</span></span>|  
|<span data-ttu-id="a0697-361">表</span><span class="sxs-lookup"><span data-stu-id="a0697-361">Table</span></span>|@Table|<span data-ttu-id="a0697-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="a0697-362">TABLE_NAME</span></span>|<span data-ttu-id="a0697-363">3</span><span class="sxs-lookup"><span data-stu-id="a0697-363">3</span></span>|  
|<span data-ttu-id="a0697-364">列</span><span class="sxs-lookup"><span data-stu-id="a0697-364">Column</span></span>|@Column|<span data-ttu-id="a0697-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="a0697-365">COLUMN_NAME</span></span>|<span data-ttu-id="a0697-366">4</span><span class="sxs-lookup"><span data-stu-id="a0697-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a0697-367">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0697-367">See Also</span></span>  
 [<span data-ttu-id="a0697-368">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="a0697-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
