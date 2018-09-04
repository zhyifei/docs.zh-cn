---
title: 架构限制
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 040ecd8a2ce223f89601de735b77ccc81638c7af
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43563424"
---
# <a name="schema-restrictions"></a><span data-ttu-id="df362-102">架构限制</span><span class="sxs-lookup"><span data-stu-id="df362-102">Schema Restrictions</span></span>
<span data-ttu-id="df362-103">第二个可选参数**GetSchema**方法将返回用于限制架构信息的量的限制，并将它传递到**GetSchema**方法作为一个字符串数组.</span><span class="sxs-lookup"><span data-stu-id="df362-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="df362-104">在数组中的位置确定可以传递的值，这等效于限制数。</span><span class="sxs-lookup"><span data-stu-id="df362-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="df362-105">例如，下表说明使用适用于 SQL Server 的 .NET Framework 数据提供程序时“Tables”架构集合支持的限制。</span><span class="sxs-lookup"><span data-stu-id="df362-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="df362-106">SQL Server 架构集合的其他限制在本主题的结尾处列出。</span><span class="sxs-lookup"><span data-stu-id="df362-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="df362-107">限制名称</span><span class="sxs-lookup"><span data-stu-id="df362-107">Restriction Name</span></span>|<span data-ttu-id="df362-108">参数名称</span><span class="sxs-lookup"><span data-stu-id="df362-108">Parameter Name</span></span>|<span data-ttu-id="df362-109">限制默认值</span><span class="sxs-lookup"><span data-stu-id="df362-109">Restriction Default</span></span>|<span data-ttu-id="df362-110">限制数</span><span class="sxs-lookup"><span data-stu-id="df362-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="df362-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="df362-111">Catalog</span></span>|@Catalog|<span data-ttu-id="df362-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df362-112">TABLE_CATALOG</span></span>|<span data-ttu-id="df362-113">1</span><span class="sxs-lookup"><span data-stu-id="df362-113">1</span></span>|  
|<span data-ttu-id="df362-114">Owner</span><span class="sxs-lookup"><span data-stu-id="df362-114">Owner</span></span>|@Owner|<span data-ttu-id="df362-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df362-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="df362-116">2</span><span class="sxs-lookup"><span data-stu-id="df362-116">2</span></span>|  
|<span data-ttu-id="df362-117">表</span><span class="sxs-lookup"><span data-stu-id="df362-117">Table</span></span>|@Name|<span data-ttu-id="df362-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df362-118">TABLE_NAME</span></span>|<span data-ttu-id="df362-119">3</span><span class="sxs-lookup"><span data-stu-id="df362-119">3</span></span>|  
|<span data-ttu-id="df362-120">TableType</span><span class="sxs-lookup"><span data-stu-id="df362-120">TableType</span></span>|@TableType|<span data-ttu-id="df362-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="df362-121">TABLE_TYPE</span></span>|<span data-ttu-id="df362-122">4</span><span class="sxs-lookup"><span data-stu-id="df362-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="df362-123">指定限制值</span><span class="sxs-lookup"><span data-stu-id="df362-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="df362-124">要使用“Tables”架构集合的一个限制，只需创建一个包含四个元素的字符串数组，然后在与限制数匹配的元素中填充值。</span><span class="sxs-lookup"><span data-stu-id="df362-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="df362-125">例如，若要限制的表返回的**GetSchema**仅在"Sales"架构中，这些表的方法将其传递给之前设置为"Sales"数组的第二个元素**GetSchema**方法。</span><span class="sxs-lookup"><span data-stu-id="df362-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df362-126">`SqlClient` 和 `OracleClient` 的限制集合还有附加的 `ParameterName` 列。</span><span class="sxs-lookup"><span data-stu-id="df362-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="df362-127">为了向后兼容，仍提供限制默认列，但是目前忽略该列。</span><span class="sxs-lookup"><span data-stu-id="df362-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="df362-128">在指定限制值时，应使用参数化查询（而不是字符串替换）来最大程度地降低受到 SQL 注入式攻击的风险。</span><span class="sxs-lookup"><span data-stu-id="df362-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df362-129">数组中的元素数必须小于或等于指定架构集合支持的限制数，否则，将引发 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="df362-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="df362-130">可以小于最大限制数。</span><span class="sxs-lookup"><span data-stu-id="df362-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="df362-131">缺少的限制假定为空（无限制）。</span><span class="sxs-lookup"><span data-stu-id="df362-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="df362-132">您可以查询的.NET Framework 托管提供程序来确定受支持的限制列表中，通过调用**GetSchema**方法替换为"限制"限制架构集合的名称。</span><span class="sxs-lookup"><span data-stu-id="df362-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="df362-133">此时将返回 <xref:System.Data.DataTable>，包含集合名称、限制名称、默认限制值和限制数的列表。</span><span class="sxs-lookup"><span data-stu-id="df362-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="df362-134">示例</span><span class="sxs-lookup"><span data-stu-id="df362-134">Example</span></span>  
 <span data-ttu-id="df362-135">下面的示例演示如何使用<xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>的 SQL Server 的.NET Framework 数据提供程序方法<xref:System.Data.SqlClient.SqlConnection>类来检索有关的所有表中包含的架构信息**AdventureWorks**示例数据库，并且能够限制的信息返回到"Sales"的架构中的这些表：</span><span class="sxs-lookup"><span data-stu-id="df362-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="df362-136">SQL Server 架构限制</span><span class="sxs-lookup"><span data-stu-id="df362-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="df362-137">下表列出了 SQL Server 架构集合的限制。</span><span class="sxs-lookup"><span data-stu-id="df362-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="df362-138">Users</span><span class="sxs-lookup"><span data-stu-id="df362-138">Users</span></span>  
  
|<span data-ttu-id="df362-139">限制名称</span><span class="sxs-lookup"><span data-stu-id="df362-139">Restriction Name</span></span>|<span data-ttu-id="df362-140">参数名称</span><span class="sxs-lookup"><span data-stu-id="df362-140">Parameter Name</span></span>|<span data-ttu-id="df362-141">限制默认值</span><span class="sxs-lookup"><span data-stu-id="df362-141">Restriction Default</span></span>|<span data-ttu-id="df362-142">限制数</span><span class="sxs-lookup"><span data-stu-id="df362-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="df362-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="df362-143">User_Name</span></span>|@Name|<span data-ttu-id="df362-144">name</span><span class="sxs-lookup"><span data-stu-id="df362-144">name</span></span>|<span data-ttu-id="df362-145">1</span><span class="sxs-lookup"><span data-stu-id="df362-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="df362-146">数据库</span><span class="sxs-lookup"><span data-stu-id="df362-146">Databases</span></span>  
  
|<span data-ttu-id="df362-147">限制名称</span><span class="sxs-lookup"><span data-stu-id="df362-147">Restriction Name</span></span>|<span data-ttu-id="df362-148">参数名称</span><span class="sxs-lookup"><span data-stu-id="df362-148">Parameter Name</span></span>|<span data-ttu-id="df362-149">限制默认值</span><span class="sxs-lookup"><span data-stu-id="df362-149">Restriction Default</span></span>|<span data-ttu-id="df362-150">限制数</span><span class="sxs-lookup"><span data-stu-id="df362-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="df362-151">name</span><span class="sxs-lookup"><span data-stu-id="df362-151">Name</span></span>|@Name|<span data-ttu-id="df362-152">name</span><span class="sxs-lookup"><span data-stu-id="df362-152">Name</span></span>|<span data-ttu-id="df362-153">1</span><span class="sxs-lookup"><span data-stu-id="df362-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="df362-154">表</span><span class="sxs-lookup"><span data-stu-id="df362-154">Tables</span></span>  
  
|<span data-ttu-id="df362-155">限制名称</span><span class="sxs-lookup"><span data-stu-id="df362-155">Restriction Name</span></span>|<span data-ttu-id="df362-156">参数名称</span><span class="sxs-lookup"><span data-stu-id="df362-156">Parameter Name</span></span>|<span data-ttu-id="df362-157">限制默认值</span><span class="sxs-lookup"><span data-stu-id="df362-157">Restriction Default</span></span>|<span data-ttu-id="df362-158">限制数</span><span class="sxs-lookup"><span data-stu-id="df362-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="df362-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="df362-159">Catalog</span></span>|@Catalog|<span data-ttu-id="df362-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df362-160">TABLE_CATALOG</span></span>|<span data-ttu-id="df362-161">1</span><span class="sxs-lookup"><span data-stu-id="df362-161">1</span></span>|  
|<span data-ttu-id="df362-162">Owner</span><span class="sxs-lookup"><span data-stu-id="df362-162">Owner</span></span>|@Owner|<span data-ttu-id="df362-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df362-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="df362-164">2</span><span class="sxs-lookup"><span data-stu-id="df362-164">2</span></span>|  
|<span data-ttu-id="df362-165">表</span><span class="sxs-lookup"><span data-stu-id="df362-165">Table</span></span>|@Name|<span data-ttu-id="df362-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df362-166">TABLE_NAME</span></span>|<span data-ttu-id="df362-167">3</span><span class="sxs-lookup"><span data-stu-id="df362-167">3</span></span>|  
|<span data-ttu-id="df362-168">TableType</span><span class="sxs-lookup"><span data-stu-id="df362-168">TableType</span></span>|@TableType|<span data-ttu-id="df362-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="df362-169">TABLE_TYPE</span></span>|<span data-ttu-id="df362-170">4</span><span class="sxs-lookup"><span data-stu-id="df362-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="df362-171">Columns</span><span class="sxs-lookup"><span data-stu-id="df362-171">Columns</span></span>  
  
|<span data-ttu-id="df362-172">限制名称</span><span class="sxs-lookup"><span data-stu-id="df362-172">Restriction Name</span></span>|<span data-ttu-id="df362-173">参数名称</span><span class="sxs-lookup"><span data-stu-id="df362-173">Parameter Name</span></span>|<span data-ttu-id="df362-174">限制默认值</span><span class="sxs-lookup"><span data-stu-id="df362-174">Restriction Default</span></span>|<span data-ttu-id="df362-175">限制数</span><span class="sxs-lookup"><span data-stu-id="df362-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="df362-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="df362-176">Catalog</span></span>|@Catalog|<span data-ttu-id="df362-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df362-177">TABLE_CATALOG</span></span>|<span data-ttu-id="df362-178">1</span><span class="sxs-lookup"><span data-stu-id="df362-178">1</span></span>|  
|<span data-ttu-id="df362-179">Owner</span><span class="sxs-lookup"><span data-stu-id="df362-179">Owner</span></span>|@Owner|<span data-ttu-id="df362-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df362-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="df362-181">2</span><span class="sxs-lookup"><span data-stu-id="df362-181">2</span></span>|  
|<span data-ttu-id="df362-182">表</span><span class="sxs-lookup"><span data-stu-id="df362-182">Table</span></span>|@Table|<span data-ttu-id="df362-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df362-183">TABLE_NAME</span></span>|<span data-ttu-id="df362-184">3</span><span class="sxs-lookup"><span data-stu-id="df362-184">3</span></span>|  
|<span data-ttu-id="df362-185">列</span><span class="sxs-lookup"><span data-stu-id="df362-185">Column</span></span>|@Column|<span data-ttu-id="df362-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="df362-186">COLUMN_NAME</span></span>|<span data-ttu-id="df362-187">4</span><span class="sxs-lookup"><span data-stu-id="df362-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="df362-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="df362-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="df362-189">限制名称</span><span class="sxs-lookup"><span data-stu-id="df362-189">Restriction Name</span></span>|<span data-ttu-id="df362-190">参数名称</span><span class="sxs-lookup"><span data-stu-id="df362-190">Parameter Name</span></span>|<span data-ttu-id="df362-191">限制默认值</span><span class="sxs-lookup"><span data-stu-id="df362-191">Restriction Default</span></span>|<span data-ttu-id="df362-192">限制数</span><span class="sxs-lookup"><span data-stu-id="df362-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="df362-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="df362-193">Catalog</span></span>|@Catalog|<span data-ttu-id="df362-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df362-194">TABLE_CATALOG</span></span>|<span data-ttu-id="df362-195">1</span><span class="sxs-lookup"><span data-stu-id="df362-195">1</span></span>|  
|<span data-ttu-id="df362-196">Owner</span><span class="sxs-lookup"><span data-stu-id="df362-196">Owner</span></span>|@Owner|<span data-ttu-id="df362-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df362-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="df362-198">2</span><span class="sxs-lookup"><span data-stu-id="df362-198">2</span></span>|  
|<span data-ttu-id="df362-199">表</span><span class="sxs-lookup"><span data-stu-id="df362-199">Table</span></span>|@Table|<span data-ttu-id="df362-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df362-200">TABLE_NAME</span></span>|<span data-ttu-id="df362-201">3</span><span class="sxs-lookup"><span data-stu-id="df362-201">3</span></span>|  
|<span data-ttu-id="df362-202">列</span><span class="sxs-lookup"><span data-stu-id="df362-202">Column</span></span>|@Column|<span data-ttu-id="df362-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="df362-203">COLUMN_NAME</span></span>|<span data-ttu-id="df362-204">4</span><span class="sxs-lookup"><span data-stu-id="df362-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="df362-205">视图</span><span class="sxs-lookup"><span data-stu-id="df362-205">Views</span></span>  
  
|<span data-ttu-id="df362-206">限制名称</span><span class="sxs-lookup"><span data-stu-id="df362-206">Restriction Name</span></span>|<span data-ttu-id="df362-207">参数名称</span><span class="sxs-lookup"><span data-stu-id="df362-207">Parameter Name</span></span>|<span data-ttu-id="df362-208">限制默认值</span><span class="sxs-lookup"><span data-stu-id="df362-208">Restriction Default</span></span>|<span data-ttu-id="df362-209">限制数</span><span class="sxs-lookup"><span data-stu-id="df362-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="df362-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="df362-210">Catalog</span></span>|@Catalog|<span data-ttu-id="df362-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df362-211">TABLE_CATALOG</span></span>|<span data-ttu-id="df362-212">1</span><span class="sxs-lookup"><span data-stu-id="df362-212">1</span></span>|  
|<span data-ttu-id="df362-213">Owner</span><span class="sxs-lookup"><span data-stu-id="df362-213">Owner</span></span>|@Owner|<span data-ttu-id="df362-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df362-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="df362-215">2</span><span class="sxs-lookup"><span data-stu-id="df362-215">2</span></span>|  
|<span data-ttu-id="df362-216">表</span><span class="sxs-lookup"><span data-stu-id="df362-216">Table</span></span>|@Table|<span data-ttu-id="df362-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df362-217">TABLE_NAME</span></span>|<span data-ttu-id="df362-218">3</span><span class="sxs-lookup"><span data-stu-id="df362-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="df362-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="df362-219">ViewColumns</span></span>  
  
|<span data-ttu-id="df362-220">限制名称</span><span class="sxs-lookup"><span data-stu-id="df362-220">Restriction Name</span></span>|<span data-ttu-id="df362-221">参数名称</span><span class="sxs-lookup"><span data-stu-id="df362-221">Parameter Name</span></span>|<span data-ttu-id="df362-222">限制默认值</span><span class="sxs-lookup"><span data-stu-id="df362-222">Restriction Default</span></span>|<span data-ttu-id="df362-223">限制数</span><span class="sxs-lookup"><span data-stu-id="df362-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="df362-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="df362-224">Catalog</span></span>|@Catalog|<span data-ttu-id="df362-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df362-225">VIEW_CATALOG</span></span>|<span data-ttu-id="df362-226">1</span><span class="sxs-lookup"><span data-stu-id="df362-226">1</span></span>|  
|<span data-ttu-id="df362-227">Owner</span><span class="sxs-lookup"><span data-stu-id="df362-227">Owner</span></span>|@Owner|<span data-ttu-id="df362-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df362-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="df362-229">2</span><span class="sxs-lookup"><span data-stu-id="df362-229">2</span></span>|  
|<span data-ttu-id="df362-230">表</span><span class="sxs-lookup"><span data-stu-id="df362-230">Table</span></span>|@Table|<span data-ttu-id="df362-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="df362-231">VIEW_NAME</span></span>|<span data-ttu-id="df362-232">3</span><span class="sxs-lookup"><span data-stu-id="df362-232">3</span></span>|  
|<span data-ttu-id="df362-233">列</span><span class="sxs-lookup"><span data-stu-id="df362-233">Column</span></span>|@Column|<span data-ttu-id="df362-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="df362-234">COLUMN_NAME</span></span>|<span data-ttu-id="df362-235">4</span><span class="sxs-lookup"><span data-stu-id="df362-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="df362-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="df362-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="df362-237">限制名称</span><span class="sxs-lookup"><span data-stu-id="df362-237">Restriction Name</span></span>|<span data-ttu-id="df362-238">参数名称</span><span class="sxs-lookup"><span data-stu-id="df362-238">Parameter Name</span></span>|<span data-ttu-id="df362-239">限制默认值</span><span class="sxs-lookup"><span data-stu-id="df362-239">Restriction Default</span></span>|<span data-ttu-id="df362-240">限制数</span><span class="sxs-lookup"><span data-stu-id="df362-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="df362-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="df362-241">Catalog</span></span>|@Catalog|<span data-ttu-id="df362-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df362-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="df362-243">1</span><span class="sxs-lookup"><span data-stu-id="df362-243">1</span></span>|  
|<span data-ttu-id="df362-244">Owner</span><span class="sxs-lookup"><span data-stu-id="df362-244">Owner</span></span>|@Owner|<span data-ttu-id="df362-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df362-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="df362-246">2</span><span class="sxs-lookup"><span data-stu-id="df362-246">2</span></span>|  
|<span data-ttu-id="df362-247">name</span><span class="sxs-lookup"><span data-stu-id="df362-247">Name</span></span>|@Name|<span data-ttu-id="df362-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="df362-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="df362-249">3</span><span class="sxs-lookup"><span data-stu-id="df362-249">3</span></span>|  
|<span data-ttu-id="df362-250">参数</span><span class="sxs-lookup"><span data-stu-id="df362-250">Parameter</span></span>|@Parameter|<span data-ttu-id="df362-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="df362-251">PARAMETER_NAME</span></span>|<span data-ttu-id="df362-252">4</span><span class="sxs-lookup"><span data-stu-id="df362-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="df362-253">过程</span><span class="sxs-lookup"><span data-stu-id="df362-253">Procedures</span></span>  
  
|<span data-ttu-id="df362-254">限制名称</span><span class="sxs-lookup"><span data-stu-id="df362-254">Restriction Name</span></span>|<span data-ttu-id="df362-255">参数名称</span><span class="sxs-lookup"><span data-stu-id="df362-255">Parameter Name</span></span>|<span data-ttu-id="df362-256">限制默认值</span><span class="sxs-lookup"><span data-stu-id="df362-256">Restriction Default</span></span>|<span data-ttu-id="df362-257">限制数</span><span class="sxs-lookup"><span data-stu-id="df362-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="df362-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="df362-258">Catalog</span></span>|@Catalog|<span data-ttu-id="df362-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df362-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="df362-260">1</span><span class="sxs-lookup"><span data-stu-id="df362-260">1</span></span>|  
|<span data-ttu-id="df362-261">Owner</span><span class="sxs-lookup"><span data-stu-id="df362-261">Owner</span></span>|@Owner|<span data-ttu-id="df362-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df362-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="df362-263">2</span><span class="sxs-lookup"><span data-stu-id="df362-263">2</span></span>|  
|<span data-ttu-id="df362-264">name</span><span class="sxs-lookup"><span data-stu-id="df362-264">Name</span></span>|@Name|<span data-ttu-id="df362-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="df362-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="df362-266">3</span><span class="sxs-lookup"><span data-stu-id="df362-266">3</span></span>|  
|<span data-ttu-id="df362-267">类型</span><span class="sxs-lookup"><span data-stu-id="df362-267">Type</span></span>|@Type|<span data-ttu-id="df362-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="df362-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="df362-269">4</span><span class="sxs-lookup"><span data-stu-id="df362-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="df362-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="df362-270">IndexColumns</span></span>  
  
|<span data-ttu-id="df362-271">限制名称</span><span class="sxs-lookup"><span data-stu-id="df362-271">Restriction Name</span></span>|<span data-ttu-id="df362-272">参数名称</span><span class="sxs-lookup"><span data-stu-id="df362-272">Parameter Name</span></span>|<span data-ttu-id="df362-273">限制默认值</span><span class="sxs-lookup"><span data-stu-id="df362-273">Restriction Default</span></span>|<span data-ttu-id="df362-274">限制数</span><span class="sxs-lookup"><span data-stu-id="df362-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="df362-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="df362-275">Catalog</span></span>|@Catalog|<span data-ttu-id="df362-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="df362-276">db_name()</span></span>|<span data-ttu-id="df362-277">1</span><span class="sxs-lookup"><span data-stu-id="df362-277">1</span></span>|  
|<span data-ttu-id="df362-278">Owner</span><span class="sxs-lookup"><span data-stu-id="df362-278">Owner</span></span>|@Owner|<span data-ttu-id="df362-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="df362-279">user_name()</span></span>|<span data-ttu-id="df362-280">2</span><span class="sxs-lookup"><span data-stu-id="df362-280">2</span></span>|  
|<span data-ttu-id="df362-281">表</span><span class="sxs-lookup"><span data-stu-id="df362-281">Table</span></span>|@Table|<span data-ttu-id="df362-282">o.name</span><span class="sxs-lookup"><span data-stu-id="df362-282">o.name</span></span>|<span data-ttu-id="df362-283">3</span><span class="sxs-lookup"><span data-stu-id="df362-283">3</span></span>|  
|<span data-ttu-id="df362-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="df362-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="df362-285">x.name</span><span class="sxs-lookup"><span data-stu-id="df362-285">x.name</span></span>|<span data-ttu-id="df362-286">4</span><span class="sxs-lookup"><span data-stu-id="df362-286">4</span></span>|  
|<span data-ttu-id="df362-287">列</span><span class="sxs-lookup"><span data-stu-id="df362-287">Column</span></span>|@Column|<span data-ttu-id="df362-288">c.name</span><span class="sxs-lookup"><span data-stu-id="df362-288">c.name</span></span>|<span data-ttu-id="df362-289">5</span><span class="sxs-lookup"><span data-stu-id="df362-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="df362-290">索引</span><span class="sxs-lookup"><span data-stu-id="df362-290">Indexes</span></span>  
  
|<span data-ttu-id="df362-291">限制名称</span><span class="sxs-lookup"><span data-stu-id="df362-291">Restriction Name</span></span>|<span data-ttu-id="df362-292">参数名称</span><span class="sxs-lookup"><span data-stu-id="df362-292">Parameter Name</span></span>|<span data-ttu-id="df362-293">限制默认值</span><span class="sxs-lookup"><span data-stu-id="df362-293">Restriction Default</span></span>|<span data-ttu-id="df362-294">限制数</span><span class="sxs-lookup"><span data-stu-id="df362-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="df362-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="df362-295">Catalog</span></span>|@Catalog|<span data-ttu-id="df362-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="df362-296">db_name()</span></span>|<span data-ttu-id="df362-297">1</span><span class="sxs-lookup"><span data-stu-id="df362-297">1</span></span>|  
|<span data-ttu-id="df362-298">Owner</span><span class="sxs-lookup"><span data-stu-id="df362-298">Owner</span></span>|@Owner|<span data-ttu-id="df362-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="df362-299">user_name()</span></span>|<span data-ttu-id="df362-300">2</span><span class="sxs-lookup"><span data-stu-id="df362-300">2</span></span>|  
|<span data-ttu-id="df362-301">表</span><span class="sxs-lookup"><span data-stu-id="df362-301">Table</span></span>|@Table|<span data-ttu-id="df362-302">o.name</span><span class="sxs-lookup"><span data-stu-id="df362-302">o.name</span></span>|<span data-ttu-id="df362-303">3</span><span class="sxs-lookup"><span data-stu-id="df362-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="df362-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="df362-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="df362-305">限制名称</span><span class="sxs-lookup"><span data-stu-id="df362-305">Restriction Name</span></span>|<span data-ttu-id="df362-306">参数名称</span><span class="sxs-lookup"><span data-stu-id="df362-306">Parameter Name</span></span>|<span data-ttu-id="df362-307">限制默认值</span><span class="sxs-lookup"><span data-stu-id="df362-307">Restriction Default</span></span>|<span data-ttu-id="df362-308">限制数</span><span class="sxs-lookup"><span data-stu-id="df362-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="df362-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="df362-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="df362-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="df362-310">assemblies.name</span></span>|<span data-ttu-id="df362-311">1</span><span class="sxs-lookup"><span data-stu-id="df362-311">1</span></span>|  
|<span data-ttu-id="df362-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="df362-312">udt_name</span></span>|@UDTName|<span data-ttu-id="df362-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="df362-313">types.assembly_class</span></span>|<span data-ttu-id="df362-314">2</span><span class="sxs-lookup"><span data-stu-id="df362-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="df362-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="df362-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="df362-316">限制名称</span><span class="sxs-lookup"><span data-stu-id="df362-316">Restriction Name</span></span>|<span data-ttu-id="df362-317">参数名称</span><span class="sxs-lookup"><span data-stu-id="df362-317">Parameter Name</span></span>|<span data-ttu-id="df362-318">限制默认值</span><span class="sxs-lookup"><span data-stu-id="df362-318">Restriction Default</span></span>|<span data-ttu-id="df362-319">限制数</span><span class="sxs-lookup"><span data-stu-id="df362-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="df362-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="df362-320">Catalog</span></span>|@Catalog|<span data-ttu-id="df362-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df362-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="df362-322">1</span><span class="sxs-lookup"><span data-stu-id="df362-322">1</span></span>|  
|<span data-ttu-id="df362-323">Owner</span><span class="sxs-lookup"><span data-stu-id="df362-323">Owner</span></span>|@Owner|<span data-ttu-id="df362-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df362-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="df362-325">2</span><span class="sxs-lookup"><span data-stu-id="df362-325">2</span></span>|  
|<span data-ttu-id="df362-326">表</span><span class="sxs-lookup"><span data-stu-id="df362-326">Table</span></span>|@Table|<span data-ttu-id="df362-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df362-327">TABLE_NAME</span></span>|<span data-ttu-id="df362-328">3</span><span class="sxs-lookup"><span data-stu-id="df362-328">3</span></span>|  
|<span data-ttu-id="df362-329">name</span><span class="sxs-lookup"><span data-stu-id="df362-329">Name</span></span>|@Name|<span data-ttu-id="df362-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="df362-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="df362-331">4</span><span class="sxs-lookup"><span data-stu-id="df362-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="df362-332">SQL Server 2008     </span><span class="sxs-lookup"><span data-stu-id="df362-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="df362-333">下表列出了 SQL Server 2008 架构集合的限制。</span><span class="sxs-lookup"><span data-stu-id="df362-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="df362-334">这些限制从 .NET Framework 版本 3.5 SP1 和 SQL Server 2008 开始生效。</span><span class="sxs-lookup"><span data-stu-id="df362-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="df362-335">.NET Framework 和 SQL Server 的早期版本不支持这些限制。</span><span class="sxs-lookup"><span data-stu-id="df362-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="df362-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="df362-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="df362-337">限制名称</span><span class="sxs-lookup"><span data-stu-id="df362-337">Restriction Name</span></span>|<span data-ttu-id="df362-338">参数名称</span><span class="sxs-lookup"><span data-stu-id="df362-338">Parameter Name</span></span>|<span data-ttu-id="df362-339">限制默认值</span><span class="sxs-lookup"><span data-stu-id="df362-339">Restriction Default</span></span>|<span data-ttu-id="df362-340">限制数</span><span class="sxs-lookup"><span data-stu-id="df362-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="df362-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="df362-341">Catalog</span></span>|@Catalog|<span data-ttu-id="df362-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df362-342">TABLE_CATALOG</span></span>|<span data-ttu-id="df362-343">1</span><span class="sxs-lookup"><span data-stu-id="df362-343">1</span></span>|  
|<span data-ttu-id="df362-344">Owner</span><span class="sxs-lookup"><span data-stu-id="df362-344">Owner</span></span>|@Owner|<span data-ttu-id="df362-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df362-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="df362-346">2</span><span class="sxs-lookup"><span data-stu-id="df362-346">2</span></span>|  
|<span data-ttu-id="df362-347">表</span><span class="sxs-lookup"><span data-stu-id="df362-347">Table</span></span>|@Table|<span data-ttu-id="df362-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df362-348">TABLE_NAME</span></span>|<span data-ttu-id="df362-349">3</span><span class="sxs-lookup"><span data-stu-id="df362-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="df362-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="df362-350">AllColumns</span></span>  
  
|<span data-ttu-id="df362-351">限制名称</span><span class="sxs-lookup"><span data-stu-id="df362-351">Restriction Name</span></span>|<span data-ttu-id="df362-352">参数名称</span><span class="sxs-lookup"><span data-stu-id="df362-352">Parameter Name</span></span>|<span data-ttu-id="df362-353">限制默认值</span><span class="sxs-lookup"><span data-stu-id="df362-353">Restriction Default</span></span>|<span data-ttu-id="df362-354">限制数</span><span class="sxs-lookup"><span data-stu-id="df362-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="df362-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="df362-355">Catalog</span></span>|@Catalog|<span data-ttu-id="df362-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df362-356">TABLE_CATALOG</span></span>|<span data-ttu-id="df362-357">1</span><span class="sxs-lookup"><span data-stu-id="df362-357">1</span></span>|  
|<span data-ttu-id="df362-358">Owner</span><span class="sxs-lookup"><span data-stu-id="df362-358">Owner</span></span>|@Owner|<span data-ttu-id="df362-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="df362-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="df362-360">2</span><span class="sxs-lookup"><span data-stu-id="df362-360">2</span></span>|  
|<span data-ttu-id="df362-361">表</span><span class="sxs-lookup"><span data-stu-id="df362-361">Table</span></span>|@Table|<span data-ttu-id="df362-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="df362-362">TABLE_NAME</span></span>|<span data-ttu-id="df362-363">3</span><span class="sxs-lookup"><span data-stu-id="df362-363">3</span></span>|  
|<span data-ttu-id="df362-364">列</span><span class="sxs-lookup"><span data-stu-id="df362-364">Column</span></span>|@Column|<span data-ttu-id="df362-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="df362-365">COLUMN_NAME</span></span>|<span data-ttu-id="df362-366">4</span><span class="sxs-lookup"><span data-stu-id="df362-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df362-367">请参阅</span><span class="sxs-lookup"><span data-stu-id="df362-367">See Also</span></span>  
 [<span data-ttu-id="df362-368">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="df362-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
