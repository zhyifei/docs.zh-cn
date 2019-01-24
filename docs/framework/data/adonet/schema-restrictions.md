---
title: 架构限制
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 7bc5f3fc1c87b8acbbfeb0bad0c7766c0a2ef1dc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688293"
---
# <a name="schema-restrictions"></a><span data-ttu-id="82ccf-102">架构限制</span><span class="sxs-lookup"><span data-stu-id="82ccf-102">Schema Restrictions</span></span>
<span data-ttu-id="82ccf-103">第二个可选参数**GetSchema**方法将返回用于限制架构信息的量的限制，并将它传递到**GetSchema**方法作为一个字符串数组.</span><span class="sxs-lookup"><span data-stu-id="82ccf-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="82ccf-104">在数组中的位置确定可以传递的值，这等效于限制数。</span><span class="sxs-lookup"><span data-stu-id="82ccf-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="82ccf-105">例如，下表说明使用适用于 SQL Server 的 .NET Framework 数据提供程序时“Tables”架构集合支持的限制。</span><span class="sxs-lookup"><span data-stu-id="82ccf-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="82ccf-106">SQL Server 架构集合的其他限制在本主题的结尾处列出。</span><span class="sxs-lookup"><span data-stu-id="82ccf-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="82ccf-107">限制名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-107">Restriction Name</span></span>|<span data-ttu-id="82ccf-108">参数名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-108">Parameter Name</span></span>|<span data-ttu-id="82ccf-109">限制默认值</span><span class="sxs-lookup"><span data-stu-id="82ccf-109">Restriction Default</span></span>|<span data-ttu-id="82ccf-110">限制数</span><span class="sxs-lookup"><span data-stu-id="82ccf-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="82ccf-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="82ccf-111">Catalog</span></span>|@Catalog|<span data-ttu-id="82ccf-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82ccf-112">TABLE_CATALOG</span></span>|<span data-ttu-id="82ccf-113">1</span><span class="sxs-lookup"><span data-stu-id="82ccf-113">1</span></span>|  
|<span data-ttu-id="82ccf-114">Owner</span><span class="sxs-lookup"><span data-stu-id="82ccf-114">Owner</span></span>|@Owner|<span data-ttu-id="82ccf-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82ccf-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="82ccf-116">2</span><span class="sxs-lookup"><span data-stu-id="82ccf-116">2</span></span>|  
|<span data-ttu-id="82ccf-117">表</span><span class="sxs-lookup"><span data-stu-id="82ccf-117">Table</span></span>|@Name|<span data-ttu-id="82ccf-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="82ccf-118">TABLE_NAME</span></span>|<span data-ttu-id="82ccf-119">3</span><span class="sxs-lookup"><span data-stu-id="82ccf-119">3</span></span>|  
|<span data-ttu-id="82ccf-120">TableType</span><span class="sxs-lookup"><span data-stu-id="82ccf-120">TableType</span></span>|@TableType|<span data-ttu-id="82ccf-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="82ccf-121">TABLE_TYPE</span></span>|<span data-ttu-id="82ccf-122">4</span><span class="sxs-lookup"><span data-stu-id="82ccf-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="82ccf-123">指定限制值</span><span class="sxs-lookup"><span data-stu-id="82ccf-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="82ccf-124">要使用“Tables”架构集合的一个限制，只需创建一个包含四个元素的字符串数组，然后在与限制数匹配的元素中填充值。</span><span class="sxs-lookup"><span data-stu-id="82ccf-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="82ccf-125">例如，若要限制的表返回的**GetSchema**仅在"Sales"架构中，这些表的方法将其传递给之前设置为"Sales"数组的第二个元素**GetSchema**方法。</span><span class="sxs-lookup"><span data-stu-id="82ccf-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82ccf-126">`SqlClient` 和 `OracleClient` 的限制集合还有附加的 `ParameterName` 列。</span><span class="sxs-lookup"><span data-stu-id="82ccf-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="82ccf-127">为了向后兼容，仍提供限制默认列，但是目前忽略该列。</span><span class="sxs-lookup"><span data-stu-id="82ccf-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="82ccf-128">在指定限制值时，应使用参数化查询（而不是字符串替换）来最大程度地降低受到 SQL 注入式攻击的风险。</span><span class="sxs-lookup"><span data-stu-id="82ccf-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82ccf-129">数组中的元素数必须小于或等于指定架构集合支持的限制数，否则，将引发 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="82ccf-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="82ccf-130">可以小于最大限制数。</span><span class="sxs-lookup"><span data-stu-id="82ccf-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="82ccf-131">缺少的限制假定为空（无限制）。</span><span class="sxs-lookup"><span data-stu-id="82ccf-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="82ccf-132">您可以查询的.NET Framework 托管提供程序来确定受支持的限制列表中，通过调用**GetSchema**方法替换为"限制"限制架构集合的名称。</span><span class="sxs-lookup"><span data-stu-id="82ccf-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="82ccf-133">此时将返回 <xref:System.Data.DataTable>，包含集合名称、限制名称、默认限制值和限制数的列表。</span><span class="sxs-lookup"><span data-stu-id="82ccf-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="82ccf-134">示例</span><span class="sxs-lookup"><span data-stu-id="82ccf-134">Example</span></span>  
 <span data-ttu-id="82ccf-135">下面的示例演示如何使用<xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>的 SQL Server 的.NET Framework 数据提供程序方法<xref:System.Data.SqlClient.SqlConnection>类来检索有关的所有表中包含的架构信息**AdventureWorks**示例数据库，并且能够限制的信息返回到"Sales"的架构中的这些表：</span><span class="sxs-lookup"><span data-stu-id="82ccf-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="82ccf-136">SQL Server 架构限制</span><span class="sxs-lookup"><span data-stu-id="82ccf-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="82ccf-137">下表列出了 SQL Server 架构集合的限制。</span><span class="sxs-lookup"><span data-stu-id="82ccf-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="82ccf-138">Users</span><span class="sxs-lookup"><span data-stu-id="82ccf-138">Users</span></span>  
  
|<span data-ttu-id="82ccf-139">限制名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-139">Restriction Name</span></span>|<span data-ttu-id="82ccf-140">参数名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-140">Parameter Name</span></span>|<span data-ttu-id="82ccf-141">限制默认值</span><span class="sxs-lookup"><span data-stu-id="82ccf-141">Restriction Default</span></span>|<span data-ttu-id="82ccf-142">限制数</span><span class="sxs-lookup"><span data-stu-id="82ccf-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="82ccf-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="82ccf-143">User_Name</span></span>|@Name|<span data-ttu-id="82ccf-144">name</span><span class="sxs-lookup"><span data-stu-id="82ccf-144">name</span></span>|<span data-ttu-id="82ccf-145">1</span><span class="sxs-lookup"><span data-stu-id="82ccf-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="82ccf-146">数据库</span><span class="sxs-lookup"><span data-stu-id="82ccf-146">Databases</span></span>  
  
|<span data-ttu-id="82ccf-147">限制名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-147">Restriction Name</span></span>|<span data-ttu-id="82ccf-148">参数名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-148">Parameter Name</span></span>|<span data-ttu-id="82ccf-149">限制默认值</span><span class="sxs-lookup"><span data-stu-id="82ccf-149">Restriction Default</span></span>|<span data-ttu-id="82ccf-150">限制数</span><span class="sxs-lookup"><span data-stu-id="82ccf-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="82ccf-151">name</span><span class="sxs-lookup"><span data-stu-id="82ccf-151">Name</span></span>|@Name|<span data-ttu-id="82ccf-152">name</span><span class="sxs-lookup"><span data-stu-id="82ccf-152">Name</span></span>|<span data-ttu-id="82ccf-153">1</span><span class="sxs-lookup"><span data-stu-id="82ccf-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="82ccf-154">表</span><span class="sxs-lookup"><span data-stu-id="82ccf-154">Tables</span></span>  
  
|<span data-ttu-id="82ccf-155">限制名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-155">Restriction Name</span></span>|<span data-ttu-id="82ccf-156">参数名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-156">Parameter Name</span></span>|<span data-ttu-id="82ccf-157">限制默认值</span><span class="sxs-lookup"><span data-stu-id="82ccf-157">Restriction Default</span></span>|<span data-ttu-id="82ccf-158">限制数</span><span class="sxs-lookup"><span data-stu-id="82ccf-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="82ccf-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="82ccf-159">Catalog</span></span>|@Catalog|<span data-ttu-id="82ccf-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82ccf-160">TABLE_CATALOG</span></span>|<span data-ttu-id="82ccf-161">1</span><span class="sxs-lookup"><span data-stu-id="82ccf-161">1</span></span>|  
|<span data-ttu-id="82ccf-162">Owner</span><span class="sxs-lookup"><span data-stu-id="82ccf-162">Owner</span></span>|@Owner|<span data-ttu-id="82ccf-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82ccf-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="82ccf-164">2</span><span class="sxs-lookup"><span data-stu-id="82ccf-164">2</span></span>|  
|<span data-ttu-id="82ccf-165">表</span><span class="sxs-lookup"><span data-stu-id="82ccf-165">Table</span></span>|@Name|<span data-ttu-id="82ccf-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="82ccf-166">TABLE_NAME</span></span>|<span data-ttu-id="82ccf-167">3</span><span class="sxs-lookup"><span data-stu-id="82ccf-167">3</span></span>|  
|<span data-ttu-id="82ccf-168">TableType</span><span class="sxs-lookup"><span data-stu-id="82ccf-168">TableType</span></span>|@TableType|<span data-ttu-id="82ccf-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="82ccf-169">TABLE_TYPE</span></span>|<span data-ttu-id="82ccf-170">4</span><span class="sxs-lookup"><span data-stu-id="82ccf-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="82ccf-171">Columns</span><span class="sxs-lookup"><span data-stu-id="82ccf-171">Columns</span></span>  
  
|<span data-ttu-id="82ccf-172">限制名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-172">Restriction Name</span></span>|<span data-ttu-id="82ccf-173">参数名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-173">Parameter Name</span></span>|<span data-ttu-id="82ccf-174">限制默认值</span><span class="sxs-lookup"><span data-stu-id="82ccf-174">Restriction Default</span></span>|<span data-ttu-id="82ccf-175">限制数</span><span class="sxs-lookup"><span data-stu-id="82ccf-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="82ccf-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="82ccf-176">Catalog</span></span>|@Catalog|<span data-ttu-id="82ccf-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82ccf-177">TABLE_CATALOG</span></span>|<span data-ttu-id="82ccf-178">1</span><span class="sxs-lookup"><span data-stu-id="82ccf-178">1</span></span>|  
|<span data-ttu-id="82ccf-179">Owner</span><span class="sxs-lookup"><span data-stu-id="82ccf-179">Owner</span></span>|@Owner|<span data-ttu-id="82ccf-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82ccf-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="82ccf-181">2</span><span class="sxs-lookup"><span data-stu-id="82ccf-181">2</span></span>|  
|<span data-ttu-id="82ccf-182">表</span><span class="sxs-lookup"><span data-stu-id="82ccf-182">Table</span></span>|@Table|<span data-ttu-id="82ccf-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="82ccf-183">TABLE_NAME</span></span>|<span data-ttu-id="82ccf-184">3</span><span class="sxs-lookup"><span data-stu-id="82ccf-184">3</span></span>|  
|<span data-ttu-id="82ccf-185">列</span><span class="sxs-lookup"><span data-stu-id="82ccf-185">Column</span></span>|@Column|<span data-ttu-id="82ccf-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="82ccf-186">COLUMN_NAME</span></span>|<span data-ttu-id="82ccf-187">4</span><span class="sxs-lookup"><span data-stu-id="82ccf-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="82ccf-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="82ccf-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="82ccf-189">限制名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-189">Restriction Name</span></span>|<span data-ttu-id="82ccf-190">参数名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-190">Parameter Name</span></span>|<span data-ttu-id="82ccf-191">限制默认值</span><span class="sxs-lookup"><span data-stu-id="82ccf-191">Restriction Default</span></span>|<span data-ttu-id="82ccf-192">限制数</span><span class="sxs-lookup"><span data-stu-id="82ccf-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="82ccf-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="82ccf-193">Catalog</span></span>|@Catalog|<span data-ttu-id="82ccf-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82ccf-194">TABLE_CATALOG</span></span>|<span data-ttu-id="82ccf-195">1</span><span class="sxs-lookup"><span data-stu-id="82ccf-195">1</span></span>|  
|<span data-ttu-id="82ccf-196">Owner</span><span class="sxs-lookup"><span data-stu-id="82ccf-196">Owner</span></span>|@Owner|<span data-ttu-id="82ccf-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82ccf-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="82ccf-198">2</span><span class="sxs-lookup"><span data-stu-id="82ccf-198">2</span></span>|  
|<span data-ttu-id="82ccf-199">表</span><span class="sxs-lookup"><span data-stu-id="82ccf-199">Table</span></span>|@Table|<span data-ttu-id="82ccf-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="82ccf-200">TABLE_NAME</span></span>|<span data-ttu-id="82ccf-201">3</span><span class="sxs-lookup"><span data-stu-id="82ccf-201">3</span></span>|  
|<span data-ttu-id="82ccf-202">列</span><span class="sxs-lookup"><span data-stu-id="82ccf-202">Column</span></span>|@Column|<span data-ttu-id="82ccf-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="82ccf-203">COLUMN_NAME</span></span>|<span data-ttu-id="82ccf-204">4</span><span class="sxs-lookup"><span data-stu-id="82ccf-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="82ccf-205">视图</span><span class="sxs-lookup"><span data-stu-id="82ccf-205">Views</span></span>  
  
|<span data-ttu-id="82ccf-206">限制名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-206">Restriction Name</span></span>|<span data-ttu-id="82ccf-207">参数名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-207">Parameter Name</span></span>|<span data-ttu-id="82ccf-208">限制默认值</span><span class="sxs-lookup"><span data-stu-id="82ccf-208">Restriction Default</span></span>|<span data-ttu-id="82ccf-209">限制数</span><span class="sxs-lookup"><span data-stu-id="82ccf-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="82ccf-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="82ccf-210">Catalog</span></span>|@Catalog|<span data-ttu-id="82ccf-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82ccf-211">TABLE_CATALOG</span></span>|<span data-ttu-id="82ccf-212">1</span><span class="sxs-lookup"><span data-stu-id="82ccf-212">1</span></span>|  
|<span data-ttu-id="82ccf-213">Owner</span><span class="sxs-lookup"><span data-stu-id="82ccf-213">Owner</span></span>|@Owner|<span data-ttu-id="82ccf-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82ccf-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="82ccf-215">2</span><span class="sxs-lookup"><span data-stu-id="82ccf-215">2</span></span>|  
|<span data-ttu-id="82ccf-216">表</span><span class="sxs-lookup"><span data-stu-id="82ccf-216">Table</span></span>|@Table|<span data-ttu-id="82ccf-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="82ccf-217">TABLE_NAME</span></span>|<span data-ttu-id="82ccf-218">3</span><span class="sxs-lookup"><span data-stu-id="82ccf-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="82ccf-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="82ccf-219">ViewColumns</span></span>  
  
|<span data-ttu-id="82ccf-220">限制名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-220">Restriction Name</span></span>|<span data-ttu-id="82ccf-221">参数名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-221">Parameter Name</span></span>|<span data-ttu-id="82ccf-222">限制默认值</span><span class="sxs-lookup"><span data-stu-id="82ccf-222">Restriction Default</span></span>|<span data-ttu-id="82ccf-223">限制数</span><span class="sxs-lookup"><span data-stu-id="82ccf-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="82ccf-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="82ccf-224">Catalog</span></span>|@Catalog|<span data-ttu-id="82ccf-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82ccf-225">VIEW_CATALOG</span></span>|<span data-ttu-id="82ccf-226">1</span><span class="sxs-lookup"><span data-stu-id="82ccf-226">1</span></span>|  
|<span data-ttu-id="82ccf-227">Owner</span><span class="sxs-lookup"><span data-stu-id="82ccf-227">Owner</span></span>|@Owner|<span data-ttu-id="82ccf-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82ccf-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="82ccf-229">2</span><span class="sxs-lookup"><span data-stu-id="82ccf-229">2</span></span>|  
|<span data-ttu-id="82ccf-230">表</span><span class="sxs-lookup"><span data-stu-id="82ccf-230">Table</span></span>|@Table|<span data-ttu-id="82ccf-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="82ccf-231">VIEW_NAME</span></span>|<span data-ttu-id="82ccf-232">3</span><span class="sxs-lookup"><span data-stu-id="82ccf-232">3</span></span>|  
|<span data-ttu-id="82ccf-233">列</span><span class="sxs-lookup"><span data-stu-id="82ccf-233">Column</span></span>|@Column|<span data-ttu-id="82ccf-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="82ccf-234">COLUMN_NAME</span></span>|<span data-ttu-id="82ccf-235">4</span><span class="sxs-lookup"><span data-stu-id="82ccf-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="82ccf-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="82ccf-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="82ccf-237">限制名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-237">Restriction Name</span></span>|<span data-ttu-id="82ccf-238">参数名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-238">Parameter Name</span></span>|<span data-ttu-id="82ccf-239">限制默认值</span><span class="sxs-lookup"><span data-stu-id="82ccf-239">Restriction Default</span></span>|<span data-ttu-id="82ccf-240">限制数</span><span class="sxs-lookup"><span data-stu-id="82ccf-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="82ccf-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="82ccf-241">Catalog</span></span>|@Catalog|<span data-ttu-id="82ccf-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82ccf-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="82ccf-243">1</span><span class="sxs-lookup"><span data-stu-id="82ccf-243">1</span></span>|  
|<span data-ttu-id="82ccf-244">Owner</span><span class="sxs-lookup"><span data-stu-id="82ccf-244">Owner</span></span>|@Owner|<span data-ttu-id="82ccf-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82ccf-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="82ccf-246">2</span><span class="sxs-lookup"><span data-stu-id="82ccf-246">2</span></span>|  
|<span data-ttu-id="82ccf-247">name</span><span class="sxs-lookup"><span data-stu-id="82ccf-247">Name</span></span>|@Name|<span data-ttu-id="82ccf-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="82ccf-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="82ccf-249">3</span><span class="sxs-lookup"><span data-stu-id="82ccf-249">3</span></span>|  
|<span data-ttu-id="82ccf-250">参数</span><span class="sxs-lookup"><span data-stu-id="82ccf-250">Parameter</span></span>|@Parameter|<span data-ttu-id="82ccf-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="82ccf-251">PARAMETER_NAME</span></span>|<span data-ttu-id="82ccf-252">4</span><span class="sxs-lookup"><span data-stu-id="82ccf-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="82ccf-253">过程</span><span class="sxs-lookup"><span data-stu-id="82ccf-253">Procedures</span></span>  
  
|<span data-ttu-id="82ccf-254">限制名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-254">Restriction Name</span></span>|<span data-ttu-id="82ccf-255">参数名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-255">Parameter Name</span></span>|<span data-ttu-id="82ccf-256">限制默认值</span><span class="sxs-lookup"><span data-stu-id="82ccf-256">Restriction Default</span></span>|<span data-ttu-id="82ccf-257">限制数</span><span class="sxs-lookup"><span data-stu-id="82ccf-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="82ccf-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="82ccf-258">Catalog</span></span>|@Catalog|<span data-ttu-id="82ccf-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82ccf-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="82ccf-260">1</span><span class="sxs-lookup"><span data-stu-id="82ccf-260">1</span></span>|  
|<span data-ttu-id="82ccf-261">Owner</span><span class="sxs-lookup"><span data-stu-id="82ccf-261">Owner</span></span>|@Owner|<span data-ttu-id="82ccf-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82ccf-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="82ccf-263">2</span><span class="sxs-lookup"><span data-stu-id="82ccf-263">2</span></span>|  
|<span data-ttu-id="82ccf-264">name</span><span class="sxs-lookup"><span data-stu-id="82ccf-264">Name</span></span>|@Name|<span data-ttu-id="82ccf-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="82ccf-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="82ccf-266">3</span><span class="sxs-lookup"><span data-stu-id="82ccf-266">3</span></span>|  
|<span data-ttu-id="82ccf-267">类型</span><span class="sxs-lookup"><span data-stu-id="82ccf-267">Type</span></span>|@Type|<span data-ttu-id="82ccf-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="82ccf-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="82ccf-269">4</span><span class="sxs-lookup"><span data-stu-id="82ccf-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="82ccf-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="82ccf-270">IndexColumns</span></span>  
  
|<span data-ttu-id="82ccf-271">限制名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-271">Restriction Name</span></span>|<span data-ttu-id="82ccf-272">参数名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-272">Parameter Name</span></span>|<span data-ttu-id="82ccf-273">限制默认值</span><span class="sxs-lookup"><span data-stu-id="82ccf-273">Restriction Default</span></span>|<span data-ttu-id="82ccf-274">限制数</span><span class="sxs-lookup"><span data-stu-id="82ccf-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="82ccf-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="82ccf-275">Catalog</span></span>|@Catalog|<span data-ttu-id="82ccf-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="82ccf-276">db_name()</span></span>|<span data-ttu-id="82ccf-277">1</span><span class="sxs-lookup"><span data-stu-id="82ccf-277">1</span></span>|  
|<span data-ttu-id="82ccf-278">Owner</span><span class="sxs-lookup"><span data-stu-id="82ccf-278">Owner</span></span>|@Owner|<span data-ttu-id="82ccf-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="82ccf-279">user_name()</span></span>|<span data-ttu-id="82ccf-280">2</span><span class="sxs-lookup"><span data-stu-id="82ccf-280">2</span></span>|  
|<span data-ttu-id="82ccf-281">表</span><span class="sxs-lookup"><span data-stu-id="82ccf-281">Table</span></span>|@Table|<span data-ttu-id="82ccf-282">o.name</span><span class="sxs-lookup"><span data-stu-id="82ccf-282">o.name</span></span>|<span data-ttu-id="82ccf-283">3</span><span class="sxs-lookup"><span data-stu-id="82ccf-283">3</span></span>|  
|<span data-ttu-id="82ccf-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="82ccf-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="82ccf-285">x.name</span><span class="sxs-lookup"><span data-stu-id="82ccf-285">x.name</span></span>|<span data-ttu-id="82ccf-286">4</span><span class="sxs-lookup"><span data-stu-id="82ccf-286">4</span></span>|  
|<span data-ttu-id="82ccf-287">列</span><span class="sxs-lookup"><span data-stu-id="82ccf-287">Column</span></span>|@Column|<span data-ttu-id="82ccf-288">c.name</span><span class="sxs-lookup"><span data-stu-id="82ccf-288">c.name</span></span>|<span data-ttu-id="82ccf-289">5</span><span class="sxs-lookup"><span data-stu-id="82ccf-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="82ccf-290">索引</span><span class="sxs-lookup"><span data-stu-id="82ccf-290">Indexes</span></span>  
  
|<span data-ttu-id="82ccf-291">限制名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-291">Restriction Name</span></span>|<span data-ttu-id="82ccf-292">参数名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-292">Parameter Name</span></span>|<span data-ttu-id="82ccf-293">限制默认值</span><span class="sxs-lookup"><span data-stu-id="82ccf-293">Restriction Default</span></span>|<span data-ttu-id="82ccf-294">限制数</span><span class="sxs-lookup"><span data-stu-id="82ccf-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="82ccf-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="82ccf-295">Catalog</span></span>|@Catalog|<span data-ttu-id="82ccf-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="82ccf-296">db_name()</span></span>|<span data-ttu-id="82ccf-297">1</span><span class="sxs-lookup"><span data-stu-id="82ccf-297">1</span></span>|  
|<span data-ttu-id="82ccf-298">Owner</span><span class="sxs-lookup"><span data-stu-id="82ccf-298">Owner</span></span>|@Owner|<span data-ttu-id="82ccf-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="82ccf-299">user_name()</span></span>|<span data-ttu-id="82ccf-300">2</span><span class="sxs-lookup"><span data-stu-id="82ccf-300">2</span></span>|  
|<span data-ttu-id="82ccf-301">表</span><span class="sxs-lookup"><span data-stu-id="82ccf-301">Table</span></span>|@Table|<span data-ttu-id="82ccf-302">o.name</span><span class="sxs-lookup"><span data-stu-id="82ccf-302">o.name</span></span>|<span data-ttu-id="82ccf-303">3</span><span class="sxs-lookup"><span data-stu-id="82ccf-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="82ccf-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="82ccf-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="82ccf-305">限制名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-305">Restriction Name</span></span>|<span data-ttu-id="82ccf-306">参数名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-306">Parameter Name</span></span>|<span data-ttu-id="82ccf-307">限制默认值</span><span class="sxs-lookup"><span data-stu-id="82ccf-307">Restriction Default</span></span>|<span data-ttu-id="82ccf-308">限制数</span><span class="sxs-lookup"><span data-stu-id="82ccf-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="82ccf-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="82ccf-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="82ccf-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="82ccf-310">assemblies.name</span></span>|<span data-ttu-id="82ccf-311">1</span><span class="sxs-lookup"><span data-stu-id="82ccf-311">1</span></span>|  
|<span data-ttu-id="82ccf-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="82ccf-312">udt_name</span></span>|@UDTName|<span data-ttu-id="82ccf-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="82ccf-313">types.assembly_class</span></span>|<span data-ttu-id="82ccf-314">2</span><span class="sxs-lookup"><span data-stu-id="82ccf-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="82ccf-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="82ccf-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="82ccf-316">限制名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-316">Restriction Name</span></span>|<span data-ttu-id="82ccf-317">参数名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-317">Parameter Name</span></span>|<span data-ttu-id="82ccf-318">限制默认值</span><span class="sxs-lookup"><span data-stu-id="82ccf-318">Restriction Default</span></span>|<span data-ttu-id="82ccf-319">限制数</span><span class="sxs-lookup"><span data-stu-id="82ccf-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="82ccf-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="82ccf-320">Catalog</span></span>|@Catalog|<span data-ttu-id="82ccf-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82ccf-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="82ccf-322">1</span><span class="sxs-lookup"><span data-stu-id="82ccf-322">1</span></span>|  
|<span data-ttu-id="82ccf-323">Owner</span><span class="sxs-lookup"><span data-stu-id="82ccf-323">Owner</span></span>|@Owner|<span data-ttu-id="82ccf-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82ccf-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="82ccf-325">2</span><span class="sxs-lookup"><span data-stu-id="82ccf-325">2</span></span>|  
|<span data-ttu-id="82ccf-326">表</span><span class="sxs-lookup"><span data-stu-id="82ccf-326">Table</span></span>|@Table|<span data-ttu-id="82ccf-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="82ccf-327">TABLE_NAME</span></span>|<span data-ttu-id="82ccf-328">3</span><span class="sxs-lookup"><span data-stu-id="82ccf-328">3</span></span>|  
|<span data-ttu-id="82ccf-329">name</span><span class="sxs-lookup"><span data-stu-id="82ccf-329">Name</span></span>|@Name|<span data-ttu-id="82ccf-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="82ccf-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="82ccf-331">4</span><span class="sxs-lookup"><span data-stu-id="82ccf-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="82ccf-332">SQL Server 2008     </span><span class="sxs-lookup"><span data-stu-id="82ccf-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="82ccf-333">下表列出了 SQL Server 2008 架构集合的限制。</span><span class="sxs-lookup"><span data-stu-id="82ccf-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="82ccf-334">这些限制从 .NET Framework 版本 3.5 SP1 和 SQL Server 2008 开始生效。</span><span class="sxs-lookup"><span data-stu-id="82ccf-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="82ccf-335">.NET Framework 和 SQL Server 的早期版本不支持这些限制。</span><span class="sxs-lookup"><span data-stu-id="82ccf-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="82ccf-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="82ccf-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="82ccf-337">限制名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-337">Restriction Name</span></span>|<span data-ttu-id="82ccf-338">参数名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-338">Parameter Name</span></span>|<span data-ttu-id="82ccf-339">限制默认值</span><span class="sxs-lookup"><span data-stu-id="82ccf-339">Restriction Default</span></span>|<span data-ttu-id="82ccf-340">限制数</span><span class="sxs-lookup"><span data-stu-id="82ccf-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="82ccf-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="82ccf-341">Catalog</span></span>|@Catalog|<span data-ttu-id="82ccf-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82ccf-342">TABLE_CATALOG</span></span>|<span data-ttu-id="82ccf-343">1</span><span class="sxs-lookup"><span data-stu-id="82ccf-343">1</span></span>|  
|<span data-ttu-id="82ccf-344">Owner</span><span class="sxs-lookup"><span data-stu-id="82ccf-344">Owner</span></span>|@Owner|<span data-ttu-id="82ccf-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82ccf-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="82ccf-346">2</span><span class="sxs-lookup"><span data-stu-id="82ccf-346">2</span></span>|  
|<span data-ttu-id="82ccf-347">表</span><span class="sxs-lookup"><span data-stu-id="82ccf-347">Table</span></span>|@Table|<span data-ttu-id="82ccf-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="82ccf-348">TABLE_NAME</span></span>|<span data-ttu-id="82ccf-349">3</span><span class="sxs-lookup"><span data-stu-id="82ccf-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="82ccf-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="82ccf-350">AllColumns</span></span>  
  
|<span data-ttu-id="82ccf-351">限制名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-351">Restriction Name</span></span>|<span data-ttu-id="82ccf-352">参数名称</span><span class="sxs-lookup"><span data-stu-id="82ccf-352">Parameter Name</span></span>|<span data-ttu-id="82ccf-353">限制默认值</span><span class="sxs-lookup"><span data-stu-id="82ccf-353">Restriction Default</span></span>|<span data-ttu-id="82ccf-354">限制数</span><span class="sxs-lookup"><span data-stu-id="82ccf-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="82ccf-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="82ccf-355">Catalog</span></span>|@Catalog|<span data-ttu-id="82ccf-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="82ccf-356">TABLE_CATALOG</span></span>|<span data-ttu-id="82ccf-357">1</span><span class="sxs-lookup"><span data-stu-id="82ccf-357">1</span></span>|  
|<span data-ttu-id="82ccf-358">Owner</span><span class="sxs-lookup"><span data-stu-id="82ccf-358">Owner</span></span>|@Owner|<span data-ttu-id="82ccf-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="82ccf-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="82ccf-360">2</span><span class="sxs-lookup"><span data-stu-id="82ccf-360">2</span></span>|  
|<span data-ttu-id="82ccf-361">表</span><span class="sxs-lookup"><span data-stu-id="82ccf-361">Table</span></span>|@Table|<span data-ttu-id="82ccf-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="82ccf-362">TABLE_NAME</span></span>|<span data-ttu-id="82ccf-363">3</span><span class="sxs-lookup"><span data-stu-id="82ccf-363">3</span></span>|  
|<span data-ttu-id="82ccf-364">列</span><span class="sxs-lookup"><span data-stu-id="82ccf-364">Column</span></span>|@Column|<span data-ttu-id="82ccf-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="82ccf-365">COLUMN_NAME</span></span>|<span data-ttu-id="82ccf-366">4</span><span class="sxs-lookup"><span data-stu-id="82ccf-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="82ccf-367">请参阅</span><span class="sxs-lookup"><span data-stu-id="82ccf-367">See also</span></span>
- [<span data-ttu-id="82ccf-368">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="82ccf-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
