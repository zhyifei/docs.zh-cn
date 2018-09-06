---
title: 架构限制
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 040ecd8a2ce223f89601de735b77ccc81638c7af
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43884726"
---
# <a name="schema-restrictions"></a><span data-ttu-id="290cc-102">架构限制</span><span class="sxs-lookup"><span data-stu-id="290cc-102">Schema Restrictions</span></span>
<span data-ttu-id="290cc-103">第二个可选参数**GetSchema**方法将返回用于限制架构信息的量的限制，并将它传递到**GetSchema**方法作为一个字符串数组.</span><span class="sxs-lookup"><span data-stu-id="290cc-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="290cc-104">在数组中的位置确定可以传递的值，这等效于限制数。</span><span class="sxs-lookup"><span data-stu-id="290cc-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="290cc-105">例如，下表说明使用适用于 SQL Server 的 .NET Framework 数据提供程序时“Tables”架构集合支持的限制。</span><span class="sxs-lookup"><span data-stu-id="290cc-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="290cc-106">SQL Server 架构集合的其他限制在本主题的结尾处列出。</span><span class="sxs-lookup"><span data-stu-id="290cc-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="290cc-107">限制名称</span><span class="sxs-lookup"><span data-stu-id="290cc-107">Restriction Name</span></span>|<span data-ttu-id="290cc-108">参数名称</span><span class="sxs-lookup"><span data-stu-id="290cc-108">Parameter Name</span></span>|<span data-ttu-id="290cc-109">限制默认值</span><span class="sxs-lookup"><span data-stu-id="290cc-109">Restriction Default</span></span>|<span data-ttu-id="290cc-110">限制数</span><span class="sxs-lookup"><span data-stu-id="290cc-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="290cc-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="290cc-111">Catalog</span></span>|@Catalog|<span data-ttu-id="290cc-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="290cc-112">TABLE_CATALOG</span></span>|<span data-ttu-id="290cc-113">1</span><span class="sxs-lookup"><span data-stu-id="290cc-113">1</span></span>|  
|<span data-ttu-id="290cc-114">Owner</span><span class="sxs-lookup"><span data-stu-id="290cc-114">Owner</span></span>|@Owner|<span data-ttu-id="290cc-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="290cc-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="290cc-116">2</span><span class="sxs-lookup"><span data-stu-id="290cc-116">2</span></span>|  
|<span data-ttu-id="290cc-117">表</span><span class="sxs-lookup"><span data-stu-id="290cc-117">Table</span></span>|@Name|<span data-ttu-id="290cc-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="290cc-118">TABLE_NAME</span></span>|<span data-ttu-id="290cc-119">3</span><span class="sxs-lookup"><span data-stu-id="290cc-119">3</span></span>|  
|<span data-ttu-id="290cc-120">TableType</span><span class="sxs-lookup"><span data-stu-id="290cc-120">TableType</span></span>|@TableType|<span data-ttu-id="290cc-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="290cc-121">TABLE_TYPE</span></span>|<span data-ttu-id="290cc-122">4</span><span class="sxs-lookup"><span data-stu-id="290cc-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="290cc-123">指定限制值</span><span class="sxs-lookup"><span data-stu-id="290cc-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="290cc-124">要使用“Tables”架构集合的一个限制，只需创建一个包含四个元素的字符串数组，然后在与限制数匹配的元素中填充值。</span><span class="sxs-lookup"><span data-stu-id="290cc-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="290cc-125">例如，若要限制的表返回的**GetSchema**仅在"Sales"架构中，这些表的方法将其传递给之前设置为"Sales"数组的第二个元素**GetSchema**方法。</span><span class="sxs-lookup"><span data-stu-id="290cc-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="290cc-126">`SqlClient` 和 `OracleClient` 的限制集合还有附加的 `ParameterName` 列。</span><span class="sxs-lookup"><span data-stu-id="290cc-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="290cc-127">为了向后兼容，仍提供限制默认列，但是目前忽略该列。</span><span class="sxs-lookup"><span data-stu-id="290cc-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="290cc-128">在指定限制值时，应使用参数化查询（而不是字符串替换）来最大程度地降低受到 SQL 注入式攻击的风险。</span><span class="sxs-lookup"><span data-stu-id="290cc-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="290cc-129">数组中的元素数必须小于或等于指定架构集合支持的限制数，否则，将引发 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="290cc-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="290cc-130">可以小于最大限制数。</span><span class="sxs-lookup"><span data-stu-id="290cc-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="290cc-131">缺少的限制假定为空（无限制）。</span><span class="sxs-lookup"><span data-stu-id="290cc-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="290cc-132">您可以查询的.NET Framework 托管提供程序来确定受支持的限制列表中，通过调用**GetSchema**方法替换为"限制"限制架构集合的名称。</span><span class="sxs-lookup"><span data-stu-id="290cc-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="290cc-133">此时将返回 <xref:System.Data.DataTable>，包含集合名称、限制名称、默认限制值和限制数的列表。</span><span class="sxs-lookup"><span data-stu-id="290cc-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="290cc-134">示例</span><span class="sxs-lookup"><span data-stu-id="290cc-134">Example</span></span>  
 <span data-ttu-id="290cc-135">下面的示例演示如何使用<xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>的 SQL Server 的.NET Framework 数据提供程序方法<xref:System.Data.SqlClient.SqlConnection>类来检索有关的所有表中包含的架构信息**AdventureWorks**示例数据库，并且能够限制的信息返回到"Sales"的架构中的这些表：</span><span class="sxs-lookup"><span data-stu-id="290cc-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="290cc-136">SQL Server 架构限制</span><span class="sxs-lookup"><span data-stu-id="290cc-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="290cc-137">下表列出了 SQL Server 架构集合的限制。</span><span class="sxs-lookup"><span data-stu-id="290cc-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="290cc-138">Users</span><span class="sxs-lookup"><span data-stu-id="290cc-138">Users</span></span>  
  
|<span data-ttu-id="290cc-139">限制名称</span><span class="sxs-lookup"><span data-stu-id="290cc-139">Restriction Name</span></span>|<span data-ttu-id="290cc-140">参数名称</span><span class="sxs-lookup"><span data-stu-id="290cc-140">Parameter Name</span></span>|<span data-ttu-id="290cc-141">限制默认值</span><span class="sxs-lookup"><span data-stu-id="290cc-141">Restriction Default</span></span>|<span data-ttu-id="290cc-142">限制数</span><span class="sxs-lookup"><span data-stu-id="290cc-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="290cc-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="290cc-143">User_Name</span></span>|@Name|<span data-ttu-id="290cc-144">name</span><span class="sxs-lookup"><span data-stu-id="290cc-144">name</span></span>|<span data-ttu-id="290cc-145">1</span><span class="sxs-lookup"><span data-stu-id="290cc-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="290cc-146">数据库</span><span class="sxs-lookup"><span data-stu-id="290cc-146">Databases</span></span>  
  
|<span data-ttu-id="290cc-147">限制名称</span><span class="sxs-lookup"><span data-stu-id="290cc-147">Restriction Name</span></span>|<span data-ttu-id="290cc-148">参数名称</span><span class="sxs-lookup"><span data-stu-id="290cc-148">Parameter Name</span></span>|<span data-ttu-id="290cc-149">限制默认值</span><span class="sxs-lookup"><span data-stu-id="290cc-149">Restriction Default</span></span>|<span data-ttu-id="290cc-150">限制数</span><span class="sxs-lookup"><span data-stu-id="290cc-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="290cc-151">name</span><span class="sxs-lookup"><span data-stu-id="290cc-151">Name</span></span>|@Name|<span data-ttu-id="290cc-152">name</span><span class="sxs-lookup"><span data-stu-id="290cc-152">Name</span></span>|<span data-ttu-id="290cc-153">1</span><span class="sxs-lookup"><span data-stu-id="290cc-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="290cc-154">表</span><span class="sxs-lookup"><span data-stu-id="290cc-154">Tables</span></span>  
  
|<span data-ttu-id="290cc-155">限制名称</span><span class="sxs-lookup"><span data-stu-id="290cc-155">Restriction Name</span></span>|<span data-ttu-id="290cc-156">参数名称</span><span class="sxs-lookup"><span data-stu-id="290cc-156">Parameter Name</span></span>|<span data-ttu-id="290cc-157">限制默认值</span><span class="sxs-lookup"><span data-stu-id="290cc-157">Restriction Default</span></span>|<span data-ttu-id="290cc-158">限制数</span><span class="sxs-lookup"><span data-stu-id="290cc-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="290cc-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="290cc-159">Catalog</span></span>|@Catalog|<span data-ttu-id="290cc-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="290cc-160">TABLE_CATALOG</span></span>|<span data-ttu-id="290cc-161">1</span><span class="sxs-lookup"><span data-stu-id="290cc-161">1</span></span>|  
|<span data-ttu-id="290cc-162">Owner</span><span class="sxs-lookup"><span data-stu-id="290cc-162">Owner</span></span>|@Owner|<span data-ttu-id="290cc-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="290cc-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="290cc-164">2</span><span class="sxs-lookup"><span data-stu-id="290cc-164">2</span></span>|  
|<span data-ttu-id="290cc-165">表</span><span class="sxs-lookup"><span data-stu-id="290cc-165">Table</span></span>|@Name|<span data-ttu-id="290cc-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="290cc-166">TABLE_NAME</span></span>|<span data-ttu-id="290cc-167">3</span><span class="sxs-lookup"><span data-stu-id="290cc-167">3</span></span>|  
|<span data-ttu-id="290cc-168">TableType</span><span class="sxs-lookup"><span data-stu-id="290cc-168">TableType</span></span>|@TableType|<span data-ttu-id="290cc-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="290cc-169">TABLE_TYPE</span></span>|<span data-ttu-id="290cc-170">4</span><span class="sxs-lookup"><span data-stu-id="290cc-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="290cc-171">Columns</span><span class="sxs-lookup"><span data-stu-id="290cc-171">Columns</span></span>  
  
|<span data-ttu-id="290cc-172">限制名称</span><span class="sxs-lookup"><span data-stu-id="290cc-172">Restriction Name</span></span>|<span data-ttu-id="290cc-173">参数名称</span><span class="sxs-lookup"><span data-stu-id="290cc-173">Parameter Name</span></span>|<span data-ttu-id="290cc-174">限制默认值</span><span class="sxs-lookup"><span data-stu-id="290cc-174">Restriction Default</span></span>|<span data-ttu-id="290cc-175">限制数</span><span class="sxs-lookup"><span data-stu-id="290cc-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="290cc-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="290cc-176">Catalog</span></span>|@Catalog|<span data-ttu-id="290cc-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="290cc-177">TABLE_CATALOG</span></span>|<span data-ttu-id="290cc-178">1</span><span class="sxs-lookup"><span data-stu-id="290cc-178">1</span></span>|  
|<span data-ttu-id="290cc-179">Owner</span><span class="sxs-lookup"><span data-stu-id="290cc-179">Owner</span></span>|@Owner|<span data-ttu-id="290cc-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="290cc-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="290cc-181">2</span><span class="sxs-lookup"><span data-stu-id="290cc-181">2</span></span>|  
|<span data-ttu-id="290cc-182">表</span><span class="sxs-lookup"><span data-stu-id="290cc-182">Table</span></span>|@Table|<span data-ttu-id="290cc-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="290cc-183">TABLE_NAME</span></span>|<span data-ttu-id="290cc-184">3</span><span class="sxs-lookup"><span data-stu-id="290cc-184">3</span></span>|  
|<span data-ttu-id="290cc-185">列</span><span class="sxs-lookup"><span data-stu-id="290cc-185">Column</span></span>|@Column|<span data-ttu-id="290cc-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="290cc-186">COLUMN_NAME</span></span>|<span data-ttu-id="290cc-187">4</span><span class="sxs-lookup"><span data-stu-id="290cc-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="290cc-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="290cc-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="290cc-189">限制名称</span><span class="sxs-lookup"><span data-stu-id="290cc-189">Restriction Name</span></span>|<span data-ttu-id="290cc-190">参数名称</span><span class="sxs-lookup"><span data-stu-id="290cc-190">Parameter Name</span></span>|<span data-ttu-id="290cc-191">限制默认值</span><span class="sxs-lookup"><span data-stu-id="290cc-191">Restriction Default</span></span>|<span data-ttu-id="290cc-192">限制数</span><span class="sxs-lookup"><span data-stu-id="290cc-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="290cc-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="290cc-193">Catalog</span></span>|@Catalog|<span data-ttu-id="290cc-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="290cc-194">TABLE_CATALOG</span></span>|<span data-ttu-id="290cc-195">1</span><span class="sxs-lookup"><span data-stu-id="290cc-195">1</span></span>|  
|<span data-ttu-id="290cc-196">Owner</span><span class="sxs-lookup"><span data-stu-id="290cc-196">Owner</span></span>|@Owner|<span data-ttu-id="290cc-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="290cc-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="290cc-198">2</span><span class="sxs-lookup"><span data-stu-id="290cc-198">2</span></span>|  
|<span data-ttu-id="290cc-199">表</span><span class="sxs-lookup"><span data-stu-id="290cc-199">Table</span></span>|@Table|<span data-ttu-id="290cc-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="290cc-200">TABLE_NAME</span></span>|<span data-ttu-id="290cc-201">3</span><span class="sxs-lookup"><span data-stu-id="290cc-201">3</span></span>|  
|<span data-ttu-id="290cc-202">列</span><span class="sxs-lookup"><span data-stu-id="290cc-202">Column</span></span>|@Column|<span data-ttu-id="290cc-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="290cc-203">COLUMN_NAME</span></span>|<span data-ttu-id="290cc-204">4</span><span class="sxs-lookup"><span data-stu-id="290cc-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="290cc-205">视图</span><span class="sxs-lookup"><span data-stu-id="290cc-205">Views</span></span>  
  
|<span data-ttu-id="290cc-206">限制名称</span><span class="sxs-lookup"><span data-stu-id="290cc-206">Restriction Name</span></span>|<span data-ttu-id="290cc-207">参数名称</span><span class="sxs-lookup"><span data-stu-id="290cc-207">Parameter Name</span></span>|<span data-ttu-id="290cc-208">限制默认值</span><span class="sxs-lookup"><span data-stu-id="290cc-208">Restriction Default</span></span>|<span data-ttu-id="290cc-209">限制数</span><span class="sxs-lookup"><span data-stu-id="290cc-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="290cc-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="290cc-210">Catalog</span></span>|@Catalog|<span data-ttu-id="290cc-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="290cc-211">TABLE_CATALOG</span></span>|<span data-ttu-id="290cc-212">1</span><span class="sxs-lookup"><span data-stu-id="290cc-212">1</span></span>|  
|<span data-ttu-id="290cc-213">Owner</span><span class="sxs-lookup"><span data-stu-id="290cc-213">Owner</span></span>|@Owner|<span data-ttu-id="290cc-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="290cc-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="290cc-215">2</span><span class="sxs-lookup"><span data-stu-id="290cc-215">2</span></span>|  
|<span data-ttu-id="290cc-216">表</span><span class="sxs-lookup"><span data-stu-id="290cc-216">Table</span></span>|@Table|<span data-ttu-id="290cc-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="290cc-217">TABLE_NAME</span></span>|<span data-ttu-id="290cc-218">3</span><span class="sxs-lookup"><span data-stu-id="290cc-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="290cc-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="290cc-219">ViewColumns</span></span>  
  
|<span data-ttu-id="290cc-220">限制名称</span><span class="sxs-lookup"><span data-stu-id="290cc-220">Restriction Name</span></span>|<span data-ttu-id="290cc-221">参数名称</span><span class="sxs-lookup"><span data-stu-id="290cc-221">Parameter Name</span></span>|<span data-ttu-id="290cc-222">限制默认值</span><span class="sxs-lookup"><span data-stu-id="290cc-222">Restriction Default</span></span>|<span data-ttu-id="290cc-223">限制数</span><span class="sxs-lookup"><span data-stu-id="290cc-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="290cc-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="290cc-224">Catalog</span></span>|@Catalog|<span data-ttu-id="290cc-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="290cc-225">VIEW_CATALOG</span></span>|<span data-ttu-id="290cc-226">1</span><span class="sxs-lookup"><span data-stu-id="290cc-226">1</span></span>|  
|<span data-ttu-id="290cc-227">Owner</span><span class="sxs-lookup"><span data-stu-id="290cc-227">Owner</span></span>|@Owner|<span data-ttu-id="290cc-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="290cc-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="290cc-229">2</span><span class="sxs-lookup"><span data-stu-id="290cc-229">2</span></span>|  
|<span data-ttu-id="290cc-230">表</span><span class="sxs-lookup"><span data-stu-id="290cc-230">Table</span></span>|@Table|<span data-ttu-id="290cc-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="290cc-231">VIEW_NAME</span></span>|<span data-ttu-id="290cc-232">3</span><span class="sxs-lookup"><span data-stu-id="290cc-232">3</span></span>|  
|<span data-ttu-id="290cc-233">列</span><span class="sxs-lookup"><span data-stu-id="290cc-233">Column</span></span>|@Column|<span data-ttu-id="290cc-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="290cc-234">COLUMN_NAME</span></span>|<span data-ttu-id="290cc-235">4</span><span class="sxs-lookup"><span data-stu-id="290cc-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="290cc-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="290cc-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="290cc-237">限制名称</span><span class="sxs-lookup"><span data-stu-id="290cc-237">Restriction Name</span></span>|<span data-ttu-id="290cc-238">参数名称</span><span class="sxs-lookup"><span data-stu-id="290cc-238">Parameter Name</span></span>|<span data-ttu-id="290cc-239">限制默认值</span><span class="sxs-lookup"><span data-stu-id="290cc-239">Restriction Default</span></span>|<span data-ttu-id="290cc-240">限制数</span><span class="sxs-lookup"><span data-stu-id="290cc-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="290cc-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="290cc-241">Catalog</span></span>|@Catalog|<span data-ttu-id="290cc-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="290cc-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="290cc-243">1</span><span class="sxs-lookup"><span data-stu-id="290cc-243">1</span></span>|  
|<span data-ttu-id="290cc-244">Owner</span><span class="sxs-lookup"><span data-stu-id="290cc-244">Owner</span></span>|@Owner|<span data-ttu-id="290cc-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="290cc-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="290cc-246">2</span><span class="sxs-lookup"><span data-stu-id="290cc-246">2</span></span>|  
|<span data-ttu-id="290cc-247">name</span><span class="sxs-lookup"><span data-stu-id="290cc-247">Name</span></span>|@Name|<span data-ttu-id="290cc-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="290cc-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="290cc-249">3</span><span class="sxs-lookup"><span data-stu-id="290cc-249">3</span></span>|  
|<span data-ttu-id="290cc-250">参数</span><span class="sxs-lookup"><span data-stu-id="290cc-250">Parameter</span></span>|@Parameter|<span data-ttu-id="290cc-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="290cc-251">PARAMETER_NAME</span></span>|<span data-ttu-id="290cc-252">4</span><span class="sxs-lookup"><span data-stu-id="290cc-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="290cc-253">过程</span><span class="sxs-lookup"><span data-stu-id="290cc-253">Procedures</span></span>  
  
|<span data-ttu-id="290cc-254">限制名称</span><span class="sxs-lookup"><span data-stu-id="290cc-254">Restriction Name</span></span>|<span data-ttu-id="290cc-255">参数名称</span><span class="sxs-lookup"><span data-stu-id="290cc-255">Parameter Name</span></span>|<span data-ttu-id="290cc-256">限制默认值</span><span class="sxs-lookup"><span data-stu-id="290cc-256">Restriction Default</span></span>|<span data-ttu-id="290cc-257">限制数</span><span class="sxs-lookup"><span data-stu-id="290cc-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="290cc-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="290cc-258">Catalog</span></span>|@Catalog|<span data-ttu-id="290cc-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="290cc-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="290cc-260">1</span><span class="sxs-lookup"><span data-stu-id="290cc-260">1</span></span>|  
|<span data-ttu-id="290cc-261">Owner</span><span class="sxs-lookup"><span data-stu-id="290cc-261">Owner</span></span>|@Owner|<span data-ttu-id="290cc-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="290cc-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="290cc-263">2</span><span class="sxs-lookup"><span data-stu-id="290cc-263">2</span></span>|  
|<span data-ttu-id="290cc-264">name</span><span class="sxs-lookup"><span data-stu-id="290cc-264">Name</span></span>|@Name|<span data-ttu-id="290cc-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="290cc-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="290cc-266">3</span><span class="sxs-lookup"><span data-stu-id="290cc-266">3</span></span>|  
|<span data-ttu-id="290cc-267">类型</span><span class="sxs-lookup"><span data-stu-id="290cc-267">Type</span></span>|@Type|<span data-ttu-id="290cc-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="290cc-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="290cc-269">4</span><span class="sxs-lookup"><span data-stu-id="290cc-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="290cc-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="290cc-270">IndexColumns</span></span>  
  
|<span data-ttu-id="290cc-271">限制名称</span><span class="sxs-lookup"><span data-stu-id="290cc-271">Restriction Name</span></span>|<span data-ttu-id="290cc-272">参数名称</span><span class="sxs-lookup"><span data-stu-id="290cc-272">Parameter Name</span></span>|<span data-ttu-id="290cc-273">限制默认值</span><span class="sxs-lookup"><span data-stu-id="290cc-273">Restriction Default</span></span>|<span data-ttu-id="290cc-274">限制数</span><span class="sxs-lookup"><span data-stu-id="290cc-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="290cc-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="290cc-275">Catalog</span></span>|@Catalog|<span data-ttu-id="290cc-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="290cc-276">db_name()</span></span>|<span data-ttu-id="290cc-277">1</span><span class="sxs-lookup"><span data-stu-id="290cc-277">1</span></span>|  
|<span data-ttu-id="290cc-278">Owner</span><span class="sxs-lookup"><span data-stu-id="290cc-278">Owner</span></span>|@Owner|<span data-ttu-id="290cc-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="290cc-279">user_name()</span></span>|<span data-ttu-id="290cc-280">2</span><span class="sxs-lookup"><span data-stu-id="290cc-280">2</span></span>|  
|<span data-ttu-id="290cc-281">表</span><span class="sxs-lookup"><span data-stu-id="290cc-281">Table</span></span>|@Table|<span data-ttu-id="290cc-282">o.name</span><span class="sxs-lookup"><span data-stu-id="290cc-282">o.name</span></span>|<span data-ttu-id="290cc-283">3</span><span class="sxs-lookup"><span data-stu-id="290cc-283">3</span></span>|  
|<span data-ttu-id="290cc-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="290cc-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="290cc-285">x.name</span><span class="sxs-lookup"><span data-stu-id="290cc-285">x.name</span></span>|<span data-ttu-id="290cc-286">4</span><span class="sxs-lookup"><span data-stu-id="290cc-286">4</span></span>|  
|<span data-ttu-id="290cc-287">列</span><span class="sxs-lookup"><span data-stu-id="290cc-287">Column</span></span>|@Column|<span data-ttu-id="290cc-288">c.name</span><span class="sxs-lookup"><span data-stu-id="290cc-288">c.name</span></span>|<span data-ttu-id="290cc-289">5</span><span class="sxs-lookup"><span data-stu-id="290cc-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="290cc-290">索引</span><span class="sxs-lookup"><span data-stu-id="290cc-290">Indexes</span></span>  
  
|<span data-ttu-id="290cc-291">限制名称</span><span class="sxs-lookup"><span data-stu-id="290cc-291">Restriction Name</span></span>|<span data-ttu-id="290cc-292">参数名称</span><span class="sxs-lookup"><span data-stu-id="290cc-292">Parameter Name</span></span>|<span data-ttu-id="290cc-293">限制默认值</span><span class="sxs-lookup"><span data-stu-id="290cc-293">Restriction Default</span></span>|<span data-ttu-id="290cc-294">限制数</span><span class="sxs-lookup"><span data-stu-id="290cc-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="290cc-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="290cc-295">Catalog</span></span>|@Catalog|<span data-ttu-id="290cc-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="290cc-296">db_name()</span></span>|<span data-ttu-id="290cc-297">1</span><span class="sxs-lookup"><span data-stu-id="290cc-297">1</span></span>|  
|<span data-ttu-id="290cc-298">Owner</span><span class="sxs-lookup"><span data-stu-id="290cc-298">Owner</span></span>|@Owner|<span data-ttu-id="290cc-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="290cc-299">user_name()</span></span>|<span data-ttu-id="290cc-300">2</span><span class="sxs-lookup"><span data-stu-id="290cc-300">2</span></span>|  
|<span data-ttu-id="290cc-301">表</span><span class="sxs-lookup"><span data-stu-id="290cc-301">Table</span></span>|@Table|<span data-ttu-id="290cc-302">o.name</span><span class="sxs-lookup"><span data-stu-id="290cc-302">o.name</span></span>|<span data-ttu-id="290cc-303">3</span><span class="sxs-lookup"><span data-stu-id="290cc-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="290cc-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="290cc-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="290cc-305">限制名称</span><span class="sxs-lookup"><span data-stu-id="290cc-305">Restriction Name</span></span>|<span data-ttu-id="290cc-306">参数名称</span><span class="sxs-lookup"><span data-stu-id="290cc-306">Parameter Name</span></span>|<span data-ttu-id="290cc-307">限制默认值</span><span class="sxs-lookup"><span data-stu-id="290cc-307">Restriction Default</span></span>|<span data-ttu-id="290cc-308">限制数</span><span class="sxs-lookup"><span data-stu-id="290cc-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="290cc-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="290cc-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="290cc-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="290cc-310">assemblies.name</span></span>|<span data-ttu-id="290cc-311">1</span><span class="sxs-lookup"><span data-stu-id="290cc-311">1</span></span>|  
|<span data-ttu-id="290cc-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="290cc-312">udt_name</span></span>|@UDTName|<span data-ttu-id="290cc-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="290cc-313">types.assembly_class</span></span>|<span data-ttu-id="290cc-314">2</span><span class="sxs-lookup"><span data-stu-id="290cc-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="290cc-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="290cc-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="290cc-316">限制名称</span><span class="sxs-lookup"><span data-stu-id="290cc-316">Restriction Name</span></span>|<span data-ttu-id="290cc-317">参数名称</span><span class="sxs-lookup"><span data-stu-id="290cc-317">Parameter Name</span></span>|<span data-ttu-id="290cc-318">限制默认值</span><span class="sxs-lookup"><span data-stu-id="290cc-318">Restriction Default</span></span>|<span data-ttu-id="290cc-319">限制数</span><span class="sxs-lookup"><span data-stu-id="290cc-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="290cc-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="290cc-320">Catalog</span></span>|@Catalog|<span data-ttu-id="290cc-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="290cc-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="290cc-322">1</span><span class="sxs-lookup"><span data-stu-id="290cc-322">1</span></span>|  
|<span data-ttu-id="290cc-323">Owner</span><span class="sxs-lookup"><span data-stu-id="290cc-323">Owner</span></span>|@Owner|<span data-ttu-id="290cc-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="290cc-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="290cc-325">2</span><span class="sxs-lookup"><span data-stu-id="290cc-325">2</span></span>|  
|<span data-ttu-id="290cc-326">表</span><span class="sxs-lookup"><span data-stu-id="290cc-326">Table</span></span>|@Table|<span data-ttu-id="290cc-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="290cc-327">TABLE_NAME</span></span>|<span data-ttu-id="290cc-328">3</span><span class="sxs-lookup"><span data-stu-id="290cc-328">3</span></span>|  
|<span data-ttu-id="290cc-329">name</span><span class="sxs-lookup"><span data-stu-id="290cc-329">Name</span></span>|@Name|<span data-ttu-id="290cc-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="290cc-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="290cc-331">4</span><span class="sxs-lookup"><span data-stu-id="290cc-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="290cc-332">SQL Server 2008     </span><span class="sxs-lookup"><span data-stu-id="290cc-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="290cc-333">下表列出了 SQL Server 2008 架构集合的限制。</span><span class="sxs-lookup"><span data-stu-id="290cc-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="290cc-334">这些限制从 .NET Framework 版本 3.5 SP1 和 SQL Server 2008 开始生效。</span><span class="sxs-lookup"><span data-stu-id="290cc-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="290cc-335">.NET Framework 和 SQL Server 的早期版本不支持这些限制。</span><span class="sxs-lookup"><span data-stu-id="290cc-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="290cc-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="290cc-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="290cc-337">限制名称</span><span class="sxs-lookup"><span data-stu-id="290cc-337">Restriction Name</span></span>|<span data-ttu-id="290cc-338">参数名称</span><span class="sxs-lookup"><span data-stu-id="290cc-338">Parameter Name</span></span>|<span data-ttu-id="290cc-339">限制默认值</span><span class="sxs-lookup"><span data-stu-id="290cc-339">Restriction Default</span></span>|<span data-ttu-id="290cc-340">限制数</span><span class="sxs-lookup"><span data-stu-id="290cc-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="290cc-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="290cc-341">Catalog</span></span>|@Catalog|<span data-ttu-id="290cc-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="290cc-342">TABLE_CATALOG</span></span>|<span data-ttu-id="290cc-343">1</span><span class="sxs-lookup"><span data-stu-id="290cc-343">1</span></span>|  
|<span data-ttu-id="290cc-344">Owner</span><span class="sxs-lookup"><span data-stu-id="290cc-344">Owner</span></span>|@Owner|<span data-ttu-id="290cc-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="290cc-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="290cc-346">2</span><span class="sxs-lookup"><span data-stu-id="290cc-346">2</span></span>|  
|<span data-ttu-id="290cc-347">表</span><span class="sxs-lookup"><span data-stu-id="290cc-347">Table</span></span>|@Table|<span data-ttu-id="290cc-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="290cc-348">TABLE_NAME</span></span>|<span data-ttu-id="290cc-349">3</span><span class="sxs-lookup"><span data-stu-id="290cc-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="290cc-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="290cc-350">AllColumns</span></span>  
  
|<span data-ttu-id="290cc-351">限制名称</span><span class="sxs-lookup"><span data-stu-id="290cc-351">Restriction Name</span></span>|<span data-ttu-id="290cc-352">参数名称</span><span class="sxs-lookup"><span data-stu-id="290cc-352">Parameter Name</span></span>|<span data-ttu-id="290cc-353">限制默认值</span><span class="sxs-lookup"><span data-stu-id="290cc-353">Restriction Default</span></span>|<span data-ttu-id="290cc-354">限制数</span><span class="sxs-lookup"><span data-stu-id="290cc-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="290cc-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="290cc-355">Catalog</span></span>|@Catalog|<span data-ttu-id="290cc-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="290cc-356">TABLE_CATALOG</span></span>|<span data-ttu-id="290cc-357">1</span><span class="sxs-lookup"><span data-stu-id="290cc-357">1</span></span>|  
|<span data-ttu-id="290cc-358">Owner</span><span class="sxs-lookup"><span data-stu-id="290cc-358">Owner</span></span>|@Owner|<span data-ttu-id="290cc-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="290cc-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="290cc-360">2</span><span class="sxs-lookup"><span data-stu-id="290cc-360">2</span></span>|  
|<span data-ttu-id="290cc-361">表</span><span class="sxs-lookup"><span data-stu-id="290cc-361">Table</span></span>|@Table|<span data-ttu-id="290cc-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="290cc-362">TABLE_NAME</span></span>|<span data-ttu-id="290cc-363">3</span><span class="sxs-lookup"><span data-stu-id="290cc-363">3</span></span>|  
|<span data-ttu-id="290cc-364">列</span><span class="sxs-lookup"><span data-stu-id="290cc-364">Column</span></span>|@Column|<span data-ttu-id="290cc-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="290cc-365">COLUMN_NAME</span></span>|<span data-ttu-id="290cc-366">4</span><span class="sxs-lookup"><span data-stu-id="290cc-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="290cc-367">请参阅</span><span class="sxs-lookup"><span data-stu-id="290cc-367">See Also</span></span>  
 [<span data-ttu-id="290cc-368">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="290cc-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
