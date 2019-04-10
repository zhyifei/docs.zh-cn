---
title: 架构限制
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: b5044d39d1dc5d2fa7d2ce691cdda7075fa0e32a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151198"
---
# <a name="schema-restrictions"></a><span data-ttu-id="65512-102">架构限制</span><span class="sxs-lookup"><span data-stu-id="65512-102">Schema Restrictions</span></span>
<span data-ttu-id="65512-103">第二个可选参数**GetSchema**方法将返回用于限制架构信息的量的限制，并将它传递到**GetSchema**方法作为一个字符串数组.</span><span class="sxs-lookup"><span data-stu-id="65512-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="65512-104">在数组中的位置确定可以传递的值，这等效于限制数。</span><span class="sxs-lookup"><span data-stu-id="65512-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="65512-105">例如，下表说明使用适用于 SQL Server 的 .NET Framework 数据提供程序时“Tables”架构集合支持的限制。</span><span class="sxs-lookup"><span data-stu-id="65512-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="65512-106">SQL Server 架构集合的其他限制在本主题的结尾处列出。</span><span class="sxs-lookup"><span data-stu-id="65512-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="65512-107">限制名称</span><span class="sxs-lookup"><span data-stu-id="65512-107">Restriction Name</span></span>|<span data-ttu-id="65512-108">参数名称</span><span class="sxs-lookup"><span data-stu-id="65512-108">Parameter Name</span></span>|<span data-ttu-id="65512-109">限制默认值</span><span class="sxs-lookup"><span data-stu-id="65512-109">Restriction Default</span></span>|<span data-ttu-id="65512-110">限制数</span><span class="sxs-lookup"><span data-stu-id="65512-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="65512-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="65512-111">Catalog</span></span>|@Catalog|<span data-ttu-id="65512-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="65512-112">TABLE_CATALOG</span></span>|<span data-ttu-id="65512-113">1</span><span class="sxs-lookup"><span data-stu-id="65512-113">1</span></span>|  
|<span data-ttu-id="65512-114">Owner</span><span class="sxs-lookup"><span data-stu-id="65512-114">Owner</span></span>|@Owner|<span data-ttu-id="65512-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="65512-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="65512-116">2</span><span class="sxs-lookup"><span data-stu-id="65512-116">2</span></span>|  
|<span data-ttu-id="65512-117">表</span><span class="sxs-lookup"><span data-stu-id="65512-117">Table</span></span>|@Name|<span data-ttu-id="65512-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="65512-118">TABLE_NAME</span></span>|<span data-ttu-id="65512-119">3</span><span class="sxs-lookup"><span data-stu-id="65512-119">3</span></span>|  
|<span data-ttu-id="65512-120">TableType</span><span class="sxs-lookup"><span data-stu-id="65512-120">TableType</span></span>|@TableType|<span data-ttu-id="65512-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="65512-121">TABLE_TYPE</span></span>|<span data-ttu-id="65512-122">4</span><span class="sxs-lookup"><span data-stu-id="65512-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="65512-123">指定限制值</span><span class="sxs-lookup"><span data-stu-id="65512-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="65512-124">要使用“Tables”架构集合的一个限制，只需创建一个包含四个元素的字符串数组，然后在与限制数匹配的元素中填充值。</span><span class="sxs-lookup"><span data-stu-id="65512-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="65512-125">例如，若要限制的表返回的**GetSchema**仅在"Sales"架构中，这些表的方法将其传递给之前设置为"Sales"数组的第二个元素**GetSchema**方法。</span><span class="sxs-lookup"><span data-stu-id="65512-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65512-126">`SqlClient` 和 `OracleClient` 的限制集合还有附加的 `ParameterName` 列。</span><span class="sxs-lookup"><span data-stu-id="65512-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="65512-127">为了向后兼容，仍提供限制默认列，但是目前忽略该列。</span><span class="sxs-lookup"><span data-stu-id="65512-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="65512-128">在指定限制值时，应使用参数化查询（而不是字符串替换）来最大程度地降低受到 SQL 注入式攻击的风险。</span><span class="sxs-lookup"><span data-stu-id="65512-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65512-129">数组中的元素数必须小于或等于指定架构集合支持的限制数，否则，将引发 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="65512-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="65512-130">可以小于最大限制数。</span><span class="sxs-lookup"><span data-stu-id="65512-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="65512-131">缺少的限制假定为空（无限制）。</span><span class="sxs-lookup"><span data-stu-id="65512-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="65512-132">您可以查询的.NET Framework 托管提供程序来确定受支持的限制列表中，通过调用**GetSchema**方法替换为"限制"限制架构集合的名称。</span><span class="sxs-lookup"><span data-stu-id="65512-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="65512-133">此时将返回 <xref:System.Data.DataTable>，包含集合名称、限制名称、默认限制值和限制数的列表。</span><span class="sxs-lookup"><span data-stu-id="65512-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="65512-134">示例</span><span class="sxs-lookup"><span data-stu-id="65512-134">Example</span></span>  
 <span data-ttu-id="65512-135">下面的示例演示如何使用<xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>的 SQL Server 的.NET Framework 数据提供程序方法<xref:System.Data.SqlClient.SqlConnection>类来检索有关的所有表中包含的架构信息**AdventureWorks**示例数据库，并且能够限制的信息返回到"Sales"的架构中的这些表：</span><span class="sxs-lookup"><span data-stu-id="65512-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="65512-136">SQL Server 架构限制</span><span class="sxs-lookup"><span data-stu-id="65512-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="65512-137">下表列出了 SQL Server 架构集合的限制。</span><span class="sxs-lookup"><span data-stu-id="65512-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="65512-138">用户</span><span class="sxs-lookup"><span data-stu-id="65512-138">Users</span></span>  
  
|<span data-ttu-id="65512-139">限制名称</span><span class="sxs-lookup"><span data-stu-id="65512-139">Restriction Name</span></span>|<span data-ttu-id="65512-140">参数名称</span><span class="sxs-lookup"><span data-stu-id="65512-140">Parameter Name</span></span>|<span data-ttu-id="65512-141">限制默认值</span><span class="sxs-lookup"><span data-stu-id="65512-141">Restriction Default</span></span>|<span data-ttu-id="65512-142">限制数</span><span class="sxs-lookup"><span data-stu-id="65512-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="65512-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="65512-143">User_Name</span></span>|@Name|<span data-ttu-id="65512-144">name</span><span class="sxs-lookup"><span data-stu-id="65512-144">name</span></span>|<span data-ttu-id="65512-145">1</span><span class="sxs-lookup"><span data-stu-id="65512-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="65512-146">数据库</span><span class="sxs-lookup"><span data-stu-id="65512-146">Databases</span></span>  
  
|<span data-ttu-id="65512-147">限制名称</span><span class="sxs-lookup"><span data-stu-id="65512-147">Restriction Name</span></span>|<span data-ttu-id="65512-148">参数名称</span><span class="sxs-lookup"><span data-stu-id="65512-148">Parameter Name</span></span>|<span data-ttu-id="65512-149">限制默认值</span><span class="sxs-lookup"><span data-stu-id="65512-149">Restriction Default</span></span>|<span data-ttu-id="65512-150">限制数</span><span class="sxs-lookup"><span data-stu-id="65512-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="65512-151">名称</span><span class="sxs-lookup"><span data-stu-id="65512-151">Name</span></span>|@Name|<span data-ttu-id="65512-152">名称</span><span class="sxs-lookup"><span data-stu-id="65512-152">Name</span></span>|<span data-ttu-id="65512-153">1</span><span class="sxs-lookup"><span data-stu-id="65512-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="65512-154">表</span><span class="sxs-lookup"><span data-stu-id="65512-154">Tables</span></span>  
  
|<span data-ttu-id="65512-155">限制名称</span><span class="sxs-lookup"><span data-stu-id="65512-155">Restriction Name</span></span>|<span data-ttu-id="65512-156">参数名称</span><span class="sxs-lookup"><span data-stu-id="65512-156">Parameter Name</span></span>|<span data-ttu-id="65512-157">限制默认值</span><span class="sxs-lookup"><span data-stu-id="65512-157">Restriction Default</span></span>|<span data-ttu-id="65512-158">限制数</span><span class="sxs-lookup"><span data-stu-id="65512-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="65512-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="65512-159">Catalog</span></span>|@Catalog|<span data-ttu-id="65512-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="65512-160">TABLE_CATALOG</span></span>|<span data-ttu-id="65512-161">1</span><span class="sxs-lookup"><span data-stu-id="65512-161">1</span></span>|  
|<span data-ttu-id="65512-162">Owner</span><span class="sxs-lookup"><span data-stu-id="65512-162">Owner</span></span>|@Owner|<span data-ttu-id="65512-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="65512-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="65512-164">2</span><span class="sxs-lookup"><span data-stu-id="65512-164">2</span></span>|  
|<span data-ttu-id="65512-165">表</span><span class="sxs-lookup"><span data-stu-id="65512-165">Table</span></span>|@Name|<span data-ttu-id="65512-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="65512-166">TABLE_NAME</span></span>|<span data-ttu-id="65512-167">3</span><span class="sxs-lookup"><span data-stu-id="65512-167">3</span></span>|  
|<span data-ttu-id="65512-168">TableType</span><span class="sxs-lookup"><span data-stu-id="65512-168">TableType</span></span>|@TableType|<span data-ttu-id="65512-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="65512-169">TABLE_TYPE</span></span>|<span data-ttu-id="65512-170">4</span><span class="sxs-lookup"><span data-stu-id="65512-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="65512-171">列</span><span class="sxs-lookup"><span data-stu-id="65512-171">Columns</span></span>  
  
|<span data-ttu-id="65512-172">限制名称</span><span class="sxs-lookup"><span data-stu-id="65512-172">Restriction Name</span></span>|<span data-ttu-id="65512-173">参数名称</span><span class="sxs-lookup"><span data-stu-id="65512-173">Parameter Name</span></span>|<span data-ttu-id="65512-174">限制默认值</span><span class="sxs-lookup"><span data-stu-id="65512-174">Restriction Default</span></span>|<span data-ttu-id="65512-175">限制数</span><span class="sxs-lookup"><span data-stu-id="65512-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="65512-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="65512-176">Catalog</span></span>|@Catalog|<span data-ttu-id="65512-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="65512-177">TABLE_CATALOG</span></span>|<span data-ttu-id="65512-178">1</span><span class="sxs-lookup"><span data-stu-id="65512-178">1</span></span>|  
|<span data-ttu-id="65512-179">Owner</span><span class="sxs-lookup"><span data-stu-id="65512-179">Owner</span></span>|@Owner|<span data-ttu-id="65512-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="65512-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="65512-181">2</span><span class="sxs-lookup"><span data-stu-id="65512-181">2</span></span>|  
|<span data-ttu-id="65512-182">表</span><span class="sxs-lookup"><span data-stu-id="65512-182">Table</span></span>|@Table|<span data-ttu-id="65512-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="65512-183">TABLE_NAME</span></span>|<span data-ttu-id="65512-184">3</span><span class="sxs-lookup"><span data-stu-id="65512-184">3</span></span>|  
|<span data-ttu-id="65512-185">列</span><span class="sxs-lookup"><span data-stu-id="65512-185">Column</span></span>|@Column|<span data-ttu-id="65512-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="65512-186">COLUMN_NAME</span></span>|<span data-ttu-id="65512-187">4</span><span class="sxs-lookup"><span data-stu-id="65512-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="65512-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="65512-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="65512-189">限制名称</span><span class="sxs-lookup"><span data-stu-id="65512-189">Restriction Name</span></span>|<span data-ttu-id="65512-190">参数名称</span><span class="sxs-lookup"><span data-stu-id="65512-190">Parameter Name</span></span>|<span data-ttu-id="65512-191">限制默认值</span><span class="sxs-lookup"><span data-stu-id="65512-191">Restriction Default</span></span>|<span data-ttu-id="65512-192">限制数</span><span class="sxs-lookup"><span data-stu-id="65512-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="65512-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="65512-193">Catalog</span></span>|@Catalog|<span data-ttu-id="65512-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="65512-194">TABLE_CATALOG</span></span>|<span data-ttu-id="65512-195">1</span><span class="sxs-lookup"><span data-stu-id="65512-195">1</span></span>|  
|<span data-ttu-id="65512-196">Owner</span><span class="sxs-lookup"><span data-stu-id="65512-196">Owner</span></span>|@Owner|<span data-ttu-id="65512-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="65512-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="65512-198">2</span><span class="sxs-lookup"><span data-stu-id="65512-198">2</span></span>|  
|<span data-ttu-id="65512-199">表</span><span class="sxs-lookup"><span data-stu-id="65512-199">Table</span></span>|@Table|<span data-ttu-id="65512-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="65512-200">TABLE_NAME</span></span>|<span data-ttu-id="65512-201">3</span><span class="sxs-lookup"><span data-stu-id="65512-201">3</span></span>|  
|<span data-ttu-id="65512-202">列</span><span class="sxs-lookup"><span data-stu-id="65512-202">Column</span></span>|@Column|<span data-ttu-id="65512-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="65512-203">COLUMN_NAME</span></span>|<span data-ttu-id="65512-204">4</span><span class="sxs-lookup"><span data-stu-id="65512-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="65512-205">Views</span><span class="sxs-lookup"><span data-stu-id="65512-205">Views</span></span>  
  
|<span data-ttu-id="65512-206">限制名称</span><span class="sxs-lookup"><span data-stu-id="65512-206">Restriction Name</span></span>|<span data-ttu-id="65512-207">参数名称</span><span class="sxs-lookup"><span data-stu-id="65512-207">Parameter Name</span></span>|<span data-ttu-id="65512-208">限制默认值</span><span class="sxs-lookup"><span data-stu-id="65512-208">Restriction Default</span></span>|<span data-ttu-id="65512-209">限制数</span><span class="sxs-lookup"><span data-stu-id="65512-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="65512-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="65512-210">Catalog</span></span>|@Catalog|<span data-ttu-id="65512-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="65512-211">TABLE_CATALOG</span></span>|<span data-ttu-id="65512-212">1</span><span class="sxs-lookup"><span data-stu-id="65512-212">1</span></span>|  
|<span data-ttu-id="65512-213">Owner</span><span class="sxs-lookup"><span data-stu-id="65512-213">Owner</span></span>|@Owner|<span data-ttu-id="65512-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="65512-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="65512-215">2</span><span class="sxs-lookup"><span data-stu-id="65512-215">2</span></span>|  
|<span data-ttu-id="65512-216">表</span><span class="sxs-lookup"><span data-stu-id="65512-216">Table</span></span>|@Table|<span data-ttu-id="65512-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="65512-217">TABLE_NAME</span></span>|<span data-ttu-id="65512-218">3</span><span class="sxs-lookup"><span data-stu-id="65512-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="65512-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="65512-219">ViewColumns</span></span>  
  
|<span data-ttu-id="65512-220">限制名称</span><span class="sxs-lookup"><span data-stu-id="65512-220">Restriction Name</span></span>|<span data-ttu-id="65512-221">参数名称</span><span class="sxs-lookup"><span data-stu-id="65512-221">Parameter Name</span></span>|<span data-ttu-id="65512-222">限制默认值</span><span class="sxs-lookup"><span data-stu-id="65512-222">Restriction Default</span></span>|<span data-ttu-id="65512-223">限制数</span><span class="sxs-lookup"><span data-stu-id="65512-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="65512-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="65512-224">Catalog</span></span>|@Catalog|<span data-ttu-id="65512-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="65512-225">VIEW_CATALOG</span></span>|<span data-ttu-id="65512-226">1</span><span class="sxs-lookup"><span data-stu-id="65512-226">1</span></span>|  
|<span data-ttu-id="65512-227">Owner</span><span class="sxs-lookup"><span data-stu-id="65512-227">Owner</span></span>|@Owner|<span data-ttu-id="65512-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="65512-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="65512-229">2</span><span class="sxs-lookup"><span data-stu-id="65512-229">2</span></span>|  
|<span data-ttu-id="65512-230">表</span><span class="sxs-lookup"><span data-stu-id="65512-230">Table</span></span>|@Table|<span data-ttu-id="65512-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="65512-231">VIEW_NAME</span></span>|<span data-ttu-id="65512-232">3</span><span class="sxs-lookup"><span data-stu-id="65512-232">3</span></span>|  
|<span data-ttu-id="65512-233">列</span><span class="sxs-lookup"><span data-stu-id="65512-233">Column</span></span>|@Column|<span data-ttu-id="65512-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="65512-234">COLUMN_NAME</span></span>|<span data-ttu-id="65512-235">4</span><span class="sxs-lookup"><span data-stu-id="65512-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="65512-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="65512-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="65512-237">限制名称</span><span class="sxs-lookup"><span data-stu-id="65512-237">Restriction Name</span></span>|<span data-ttu-id="65512-238">参数名称</span><span class="sxs-lookup"><span data-stu-id="65512-238">Parameter Name</span></span>|<span data-ttu-id="65512-239">限制默认值</span><span class="sxs-lookup"><span data-stu-id="65512-239">Restriction Default</span></span>|<span data-ttu-id="65512-240">限制数</span><span class="sxs-lookup"><span data-stu-id="65512-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="65512-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="65512-241">Catalog</span></span>|@Catalog|<span data-ttu-id="65512-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="65512-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="65512-243">1</span><span class="sxs-lookup"><span data-stu-id="65512-243">1</span></span>|  
|<span data-ttu-id="65512-244">Owner</span><span class="sxs-lookup"><span data-stu-id="65512-244">Owner</span></span>|@Owner|<span data-ttu-id="65512-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="65512-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="65512-246">2</span><span class="sxs-lookup"><span data-stu-id="65512-246">2</span></span>|  
|<span data-ttu-id="65512-247">名称</span><span class="sxs-lookup"><span data-stu-id="65512-247">Name</span></span>|@Name|<span data-ttu-id="65512-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="65512-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="65512-249">3</span><span class="sxs-lookup"><span data-stu-id="65512-249">3</span></span>|  
|<span data-ttu-id="65512-250">参数</span><span class="sxs-lookup"><span data-stu-id="65512-250">Parameter</span></span>|@Parameter|<span data-ttu-id="65512-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="65512-251">PARAMETER_NAME</span></span>|<span data-ttu-id="65512-252">4</span><span class="sxs-lookup"><span data-stu-id="65512-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="65512-253">过程</span><span class="sxs-lookup"><span data-stu-id="65512-253">Procedures</span></span>  
  
|<span data-ttu-id="65512-254">限制名称</span><span class="sxs-lookup"><span data-stu-id="65512-254">Restriction Name</span></span>|<span data-ttu-id="65512-255">参数名称</span><span class="sxs-lookup"><span data-stu-id="65512-255">Parameter Name</span></span>|<span data-ttu-id="65512-256">限制默认值</span><span class="sxs-lookup"><span data-stu-id="65512-256">Restriction Default</span></span>|<span data-ttu-id="65512-257">限制数</span><span class="sxs-lookup"><span data-stu-id="65512-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="65512-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="65512-258">Catalog</span></span>|@Catalog|<span data-ttu-id="65512-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="65512-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="65512-260">1</span><span class="sxs-lookup"><span data-stu-id="65512-260">1</span></span>|  
|<span data-ttu-id="65512-261">Owner</span><span class="sxs-lookup"><span data-stu-id="65512-261">Owner</span></span>|@Owner|<span data-ttu-id="65512-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="65512-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="65512-263">2</span><span class="sxs-lookup"><span data-stu-id="65512-263">2</span></span>|  
|<span data-ttu-id="65512-264">名称</span><span class="sxs-lookup"><span data-stu-id="65512-264">Name</span></span>|@Name|<span data-ttu-id="65512-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="65512-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="65512-266">3</span><span class="sxs-lookup"><span data-stu-id="65512-266">3</span></span>|  
|<span data-ttu-id="65512-267">类型</span><span class="sxs-lookup"><span data-stu-id="65512-267">Type</span></span>|@Type|<span data-ttu-id="65512-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="65512-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="65512-269">4</span><span class="sxs-lookup"><span data-stu-id="65512-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="65512-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="65512-270">IndexColumns</span></span>  
  
|<span data-ttu-id="65512-271">限制名称</span><span class="sxs-lookup"><span data-stu-id="65512-271">Restriction Name</span></span>|<span data-ttu-id="65512-272">参数名称</span><span class="sxs-lookup"><span data-stu-id="65512-272">Parameter Name</span></span>|<span data-ttu-id="65512-273">限制默认值</span><span class="sxs-lookup"><span data-stu-id="65512-273">Restriction Default</span></span>|<span data-ttu-id="65512-274">限制数</span><span class="sxs-lookup"><span data-stu-id="65512-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="65512-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="65512-275">Catalog</span></span>|@Catalog|<span data-ttu-id="65512-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="65512-276">db_name()</span></span>|<span data-ttu-id="65512-277">1</span><span class="sxs-lookup"><span data-stu-id="65512-277">1</span></span>|  
|<span data-ttu-id="65512-278">Owner</span><span class="sxs-lookup"><span data-stu-id="65512-278">Owner</span></span>|@Owner|<span data-ttu-id="65512-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="65512-279">user_name()</span></span>|<span data-ttu-id="65512-280">2</span><span class="sxs-lookup"><span data-stu-id="65512-280">2</span></span>|  
|<span data-ttu-id="65512-281">表</span><span class="sxs-lookup"><span data-stu-id="65512-281">Table</span></span>|@Table|<span data-ttu-id="65512-282">o.name</span><span class="sxs-lookup"><span data-stu-id="65512-282">o.name</span></span>|<span data-ttu-id="65512-283">3</span><span class="sxs-lookup"><span data-stu-id="65512-283">3</span></span>|  
|<span data-ttu-id="65512-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="65512-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="65512-285">x.name</span><span class="sxs-lookup"><span data-stu-id="65512-285">x.name</span></span>|<span data-ttu-id="65512-286">4</span><span class="sxs-lookup"><span data-stu-id="65512-286">4</span></span>|  
|<span data-ttu-id="65512-287">列</span><span class="sxs-lookup"><span data-stu-id="65512-287">Column</span></span>|@Column|<span data-ttu-id="65512-288">c.name</span><span class="sxs-lookup"><span data-stu-id="65512-288">c.name</span></span>|<span data-ttu-id="65512-289">5</span><span class="sxs-lookup"><span data-stu-id="65512-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="65512-290">索引</span><span class="sxs-lookup"><span data-stu-id="65512-290">Indexes</span></span>  
  
|<span data-ttu-id="65512-291">限制名称</span><span class="sxs-lookup"><span data-stu-id="65512-291">Restriction Name</span></span>|<span data-ttu-id="65512-292">参数名称</span><span class="sxs-lookup"><span data-stu-id="65512-292">Parameter Name</span></span>|<span data-ttu-id="65512-293">限制默认值</span><span class="sxs-lookup"><span data-stu-id="65512-293">Restriction Default</span></span>|<span data-ttu-id="65512-294">限制数</span><span class="sxs-lookup"><span data-stu-id="65512-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="65512-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="65512-295">Catalog</span></span>|@Catalog|<span data-ttu-id="65512-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="65512-296">db_name()</span></span>|<span data-ttu-id="65512-297">1</span><span class="sxs-lookup"><span data-stu-id="65512-297">1</span></span>|  
|<span data-ttu-id="65512-298">Owner</span><span class="sxs-lookup"><span data-stu-id="65512-298">Owner</span></span>|@Owner|<span data-ttu-id="65512-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="65512-299">user_name()</span></span>|<span data-ttu-id="65512-300">2</span><span class="sxs-lookup"><span data-stu-id="65512-300">2</span></span>|  
|<span data-ttu-id="65512-301">表</span><span class="sxs-lookup"><span data-stu-id="65512-301">Table</span></span>|@Table|<span data-ttu-id="65512-302">o.name</span><span class="sxs-lookup"><span data-stu-id="65512-302">o.name</span></span>|<span data-ttu-id="65512-303">3</span><span class="sxs-lookup"><span data-stu-id="65512-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="65512-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="65512-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="65512-305">限制名称</span><span class="sxs-lookup"><span data-stu-id="65512-305">Restriction Name</span></span>|<span data-ttu-id="65512-306">参数名称</span><span class="sxs-lookup"><span data-stu-id="65512-306">Parameter Name</span></span>|<span data-ttu-id="65512-307">限制默认值</span><span class="sxs-lookup"><span data-stu-id="65512-307">Restriction Default</span></span>|<span data-ttu-id="65512-308">限制数</span><span class="sxs-lookup"><span data-stu-id="65512-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="65512-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="65512-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="65512-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="65512-310">assemblies.name</span></span>|<span data-ttu-id="65512-311">1</span><span class="sxs-lookup"><span data-stu-id="65512-311">1</span></span>|  
|<span data-ttu-id="65512-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="65512-312">udt_name</span></span>|@UDTName|<span data-ttu-id="65512-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="65512-313">types.assembly_class</span></span>|<span data-ttu-id="65512-314">2</span><span class="sxs-lookup"><span data-stu-id="65512-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="65512-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="65512-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="65512-316">限制名称</span><span class="sxs-lookup"><span data-stu-id="65512-316">Restriction Name</span></span>|<span data-ttu-id="65512-317">参数名称</span><span class="sxs-lookup"><span data-stu-id="65512-317">Parameter Name</span></span>|<span data-ttu-id="65512-318">限制默认值</span><span class="sxs-lookup"><span data-stu-id="65512-318">Restriction Default</span></span>|<span data-ttu-id="65512-319">限制数</span><span class="sxs-lookup"><span data-stu-id="65512-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="65512-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="65512-320">Catalog</span></span>|@Catalog|<span data-ttu-id="65512-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="65512-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="65512-322">1</span><span class="sxs-lookup"><span data-stu-id="65512-322">1</span></span>|  
|<span data-ttu-id="65512-323">Owner</span><span class="sxs-lookup"><span data-stu-id="65512-323">Owner</span></span>|@Owner|<span data-ttu-id="65512-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="65512-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="65512-325">2</span><span class="sxs-lookup"><span data-stu-id="65512-325">2</span></span>|  
|<span data-ttu-id="65512-326">表</span><span class="sxs-lookup"><span data-stu-id="65512-326">Table</span></span>|@Table|<span data-ttu-id="65512-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="65512-327">TABLE_NAME</span></span>|<span data-ttu-id="65512-328">3</span><span class="sxs-lookup"><span data-stu-id="65512-328">3</span></span>|  
|<span data-ttu-id="65512-329">名称</span><span class="sxs-lookup"><span data-stu-id="65512-329">Name</span></span>|@Name|<span data-ttu-id="65512-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="65512-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="65512-331">4</span><span class="sxs-lookup"><span data-stu-id="65512-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="65512-332">SQL Server 2008     </span><span class="sxs-lookup"><span data-stu-id="65512-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="65512-333">下表列出了 SQL Server 2008 架构集合的限制。</span><span class="sxs-lookup"><span data-stu-id="65512-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="65512-334">这些限制从 .NET Framework 版本 3.5 SP1 和 SQL Server 2008 开始生效。</span><span class="sxs-lookup"><span data-stu-id="65512-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="65512-335">.NET Framework 和 SQL Server 的早期版本不支持这些限制。</span><span class="sxs-lookup"><span data-stu-id="65512-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="65512-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="65512-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="65512-337">限制名称</span><span class="sxs-lookup"><span data-stu-id="65512-337">Restriction Name</span></span>|<span data-ttu-id="65512-338">参数名称</span><span class="sxs-lookup"><span data-stu-id="65512-338">Parameter Name</span></span>|<span data-ttu-id="65512-339">限制默认值</span><span class="sxs-lookup"><span data-stu-id="65512-339">Restriction Default</span></span>|<span data-ttu-id="65512-340">限制数</span><span class="sxs-lookup"><span data-stu-id="65512-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="65512-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="65512-341">Catalog</span></span>|@Catalog|<span data-ttu-id="65512-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="65512-342">TABLE_CATALOG</span></span>|<span data-ttu-id="65512-343">1</span><span class="sxs-lookup"><span data-stu-id="65512-343">1</span></span>|  
|<span data-ttu-id="65512-344">Owner</span><span class="sxs-lookup"><span data-stu-id="65512-344">Owner</span></span>|@Owner|<span data-ttu-id="65512-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="65512-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="65512-346">2</span><span class="sxs-lookup"><span data-stu-id="65512-346">2</span></span>|  
|<span data-ttu-id="65512-347">表</span><span class="sxs-lookup"><span data-stu-id="65512-347">Table</span></span>|@Table|<span data-ttu-id="65512-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="65512-348">TABLE_NAME</span></span>|<span data-ttu-id="65512-349">3</span><span class="sxs-lookup"><span data-stu-id="65512-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="65512-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="65512-350">AllColumns</span></span>  
  
|<span data-ttu-id="65512-351">限制名称</span><span class="sxs-lookup"><span data-stu-id="65512-351">Restriction Name</span></span>|<span data-ttu-id="65512-352">参数名称</span><span class="sxs-lookup"><span data-stu-id="65512-352">Parameter Name</span></span>|<span data-ttu-id="65512-353">限制默认值</span><span class="sxs-lookup"><span data-stu-id="65512-353">Restriction Default</span></span>|<span data-ttu-id="65512-354">限制数</span><span class="sxs-lookup"><span data-stu-id="65512-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="65512-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="65512-355">Catalog</span></span>|@Catalog|<span data-ttu-id="65512-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="65512-356">TABLE_CATALOG</span></span>|<span data-ttu-id="65512-357">1</span><span class="sxs-lookup"><span data-stu-id="65512-357">1</span></span>|  
|<span data-ttu-id="65512-358">Owner</span><span class="sxs-lookup"><span data-stu-id="65512-358">Owner</span></span>|@Owner|<span data-ttu-id="65512-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="65512-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="65512-360">2</span><span class="sxs-lookup"><span data-stu-id="65512-360">2</span></span>|  
|<span data-ttu-id="65512-361">表</span><span class="sxs-lookup"><span data-stu-id="65512-361">Table</span></span>|@Table|<span data-ttu-id="65512-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="65512-362">TABLE_NAME</span></span>|<span data-ttu-id="65512-363">3</span><span class="sxs-lookup"><span data-stu-id="65512-363">3</span></span>|  
|<span data-ttu-id="65512-364">列</span><span class="sxs-lookup"><span data-stu-id="65512-364">Column</span></span>|@Column|<span data-ttu-id="65512-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="65512-365">COLUMN_NAME</span></span>|<span data-ttu-id="65512-366">4</span><span class="sxs-lookup"><span data-stu-id="65512-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="65512-367">请参阅</span><span class="sxs-lookup"><span data-stu-id="65512-367">See also</span></span>

- [<span data-ttu-id="65512-368">ADO.NET 托管提供程序和 DataSet 开发人员中心</span><span class="sxs-lookup"><span data-stu-id="65512-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
