---
title: 枚举 SQL Server 的实例 (ADO.NET)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ddf1c83c-9d40-45e6-b04d-9828c6cbbfdc
ms.openlocfilehash: d9456926b228fadca940f6c4698829494382e237
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355517"
---
# <a name="enumerating-instances-of-sql-server-adonet"></a><span data-ttu-id="13049-102">枚举 SQL Server 的实例 (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="13049-102">Enumerating Instances of SQL Server (ADO.NET)</span></span>
<span data-ttu-id="13049-103">SQL Server 允许应用程序查找当前的网络中的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="13049-103">SQL Server permits applications to find SQL Server instances within the current network.</span></span> <span data-ttu-id="13049-104"><xref:System.Data.Sql.SqlDataSourceEnumerator> 类向应用程序开发人员公开此信息，提供包含所有可见服务器的信息的 <xref:System.Data.DataTable>。</span><span class="sxs-lookup"><span data-stu-id="13049-104">The <xref:System.Data.Sql.SqlDataSourceEnumerator> class exposes this information to the application developer, providing a <xref:System.Data.DataTable> containing information about all the visible servers.</span></span> <span data-ttu-id="13049-105">此返回的表包含与用户尝试创建一个新的连接时提供的列表匹配和扩展包含在所有可用的服务器上的下拉列表的网络上可用的服务器实例的列表**连接属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="13049-105">This returned table contains a list of server instances available on the network that matches the list provided when a user attempts to create a new connection, and expands the drop-down list containing all the available servers on the **Connection Properties** dialog box.</span></span> <span data-ttu-id="13049-106">显示的结果并非总是完整的。</span><span class="sxs-lookup"><span data-stu-id="13049-106">The results displayed are not always complete.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13049-107">与大多数 Windows 服务一样，最好使用尽可能少的权限运行 SQL 浏览器服务。</span><span class="sxs-lookup"><span data-stu-id="13049-107">As with most Windows services, it is best to run the SQL Browser service with the least possible privileges.</span></span> <span data-ttu-id="13049-108">有关 SQL 浏览器服务以及如何管理其行为的更多信息，请参见“SQL Server 联机图书”。</span><span class="sxs-lookup"><span data-stu-id="13049-108">See SQL Server Books Online for more information on the SQL Browser service, and how to manage its behavior.</span></span>  
  
## <a name="retrieving-an-enumerator-instance"></a><span data-ttu-id="13049-109">检索枚举器实例</span><span class="sxs-lookup"><span data-stu-id="13049-109">Retrieving an Enumerator Instance</span></span>  
 <span data-ttu-id="13049-110">要检索包含可用 SQL Server 实例信息的表，必须先使用共享/静态 <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A> 属性检索枚举器：</span><span class="sxs-lookup"><span data-stu-id="13049-110">In order to retrieve the table containing information about the available SQL Server instances, you must first retrieve an enumerator, using the shared/static <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A> property:</span></span>  
  
```vb  
Dim instance As System.Data.Sql.SqlDataSourceEnumerator = _  
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
```csharp  
System.Data.Sql.SqlDataSourceEnumerator instance =   
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
 <span data-ttu-id="13049-111">检索到静态实例之后，可以调用 <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A> 方法，该方法返回包含可用服务器信息的 <xref:System.Data.DataTable>：</span><span class="sxs-lookup"><span data-stu-id="13049-111">Once you have retrieved the static instance, you can call the <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A> method, which returns a <xref:System.Data.DataTable> containing information about the available servers:</span></span>  
  
```vb  
Dim dataTable As System.Data.DataTable = instance.GetDataSources()  
```  
  
```csharp  
System.Data.DataTable dataTable = instance.GetDataSources();  
```  
  
 <span data-ttu-id="13049-112">通过方法调用返回的表包含以下列，所有列均包含 `string` 值：</span><span class="sxs-lookup"><span data-stu-id="13049-112">The table returned from the method call contains the following columns, all of which contain `string` values:</span></span>  
  
|<span data-ttu-id="13049-113">列</span><span class="sxs-lookup"><span data-stu-id="13049-113">Column</span></span>|<span data-ttu-id="13049-114">描述</span><span class="sxs-lookup"><span data-stu-id="13049-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="13049-115">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="13049-115">**ServerName**</span></span>|<span data-ttu-id="13049-116">服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="13049-116">Name of the server.</span></span>|  
|<span data-ttu-id="13049-117">**InstanceName**</span><span class="sxs-lookup"><span data-stu-id="13049-117">**InstanceName**</span></span>|<span data-ttu-id="13049-118">服务器实例的名称。</span><span class="sxs-lookup"><span data-stu-id="13049-118">Name of the server instance.</span></span> <span data-ttu-id="13049-119">如果服务器作为默认实例运行，则为空白。</span><span class="sxs-lookup"><span data-stu-id="13049-119">Blank if the server is running as the default instance.</span></span>|  
|<span data-ttu-id="13049-120">**IsClustered**</span><span class="sxs-lookup"><span data-stu-id="13049-120">**IsClustered**</span></span>|<span data-ttu-id="13049-121">指示服务器是否属于群集。</span><span class="sxs-lookup"><span data-stu-id="13049-121">Indicates whether the server is part of a cluster.</span></span>|  
|<span data-ttu-id="13049-122">**Version**</span><span class="sxs-lookup"><span data-stu-id="13049-122">**Version**</span></span>|<span data-ttu-id="13049-123">服务器的版本。</span><span class="sxs-lookup"><span data-stu-id="13049-123">Version of the server.</span></span> <span data-ttu-id="13049-124">例如：</span><span class="sxs-lookup"><span data-stu-id="13049-124">For example:</span></span><br /><br /> <span data-ttu-id="13049-125">-   9.00.x ([!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)])</span><span class="sxs-lookup"><span data-stu-id="13049-125">-   9.00.x ([!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)])</span></span><br /><span data-ttu-id="13049-126">-   10.0.xx ([!INCLUDE[ssKatmai](../../../../../includes/sskatmai-md.md)])</span><span class="sxs-lookup"><span data-stu-id="13049-126">-   10.0.xx ([!INCLUDE[ssKatmai](../../../../../includes/sskatmai-md.md)])</span></span><br /><span data-ttu-id="13049-127">-   10.50.x ([!INCLUDE[ssKilimanjaro](../../../../../includes/sskilimanjaro-md.md)])</span><span class="sxs-lookup"><span data-stu-id="13049-127">-   10.50.x ([!INCLUDE[ssKilimanjaro](../../../../../includes/sskilimanjaro-md.md)])</span></span><br /><span data-ttu-id="13049-128">-11.0.xx (SQL Server 2012)</span><span class="sxs-lookup"><span data-stu-id="13049-128">-   11.0.xx (SQL Server 2012)</span></span>|  
  
## <a name="enumeration-limitations"></a><span data-ttu-id="13049-129">枚举限制</span><span class="sxs-lookup"><span data-stu-id="13049-129">Enumeration Limitations</span></span>  
 <span data-ttu-id="13049-130">所有可用服务器可能会列出，也可能不会列出。</span><span class="sxs-lookup"><span data-stu-id="13049-130">All of the available servers may or may not be listed.</span></span> <span data-ttu-id="13049-131">根据超时和网络通信量等因素，列表可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="13049-131">The list can vary depending on factors such as timeouts and network traffic.</span></span> <span data-ttu-id="13049-132">这可能会使两个连续调用生成不同的列表。</span><span class="sxs-lookup"><span data-stu-id="13049-132">This can cause the list to be different on two consecutive calls.</span></span> <span data-ttu-id="13049-133">只会列出相同网络上的服务器。</span><span class="sxs-lookup"><span data-stu-id="13049-133">Only servers on the same network will be listed.</span></span> <span data-ttu-id="13049-134">广播包通常不会遍历路由器，这也就是可能会看不到某个服务器列出的原因，但是在各个调用之间是稳定的。</span><span class="sxs-lookup"><span data-stu-id="13049-134">Broadcast packets typically won't traverse routers, which is why you may not see a server listed, but it will be stable across calls.</span></span>  
  
 <span data-ttu-id="13049-135">列出的服务器可能包含其他信息，也可能不包含其他信息，例如 `IsClustered` 和版本。</span><span class="sxs-lookup"><span data-stu-id="13049-135">Listed servers may or may not have additional information such as `IsClustered` and version.</span></span> <span data-ttu-id="13049-136">这取决于获取列表的方式。</span><span class="sxs-lookup"><span data-stu-id="13049-136">This is dependent on how the list was obtained.</span></span> <span data-ttu-id="13049-137">通过 SQL Server 浏览器服务列出的服务器将比通过 Windows 基础结构发现的服务器更加详细，后者只会列出名称。</span><span class="sxs-lookup"><span data-stu-id="13049-137">Servers listed through the SQL Server browser service will have more details than those found through the Windows infrastructure, which will list only the name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13049-138">只有以完全信任模式运行时，才可以使用服务器枚举。</span><span class="sxs-lookup"><span data-stu-id="13049-138">Server enumeration is only available when running in full-trust.</span></span> <span data-ttu-id="13049-139">在部分信任的环境中运行的程序集将无法使用服务器枚举，即使这些程序集具有 <xref:System.Data.SqlClient.SqlClientPermission> 代码访问安全性 (CAS) 权限。</span><span class="sxs-lookup"><span data-stu-id="13049-139">Assemblies running in a partially-trusted environment will not be able to use it, even if they have the <xref:System.Data.SqlClient.SqlClientPermission> Code Access Security (CAS) permission.</span></span>  
  
 <span data-ttu-id="13049-140">SQL Server 提供的信息<xref:System.Data.Sql.SqlDataSourceEnumerator>通过名为 SQL Browser 的外部 Windows 服务使用。</span><span class="sxs-lookup"><span data-stu-id="13049-140">SQL Server provides information for the <xref:System.Data.Sql.SqlDataSourceEnumerator> through the use of an external Windows service named SQL Browser.</span></span> <span data-ttu-id="13049-141">默认情况下启用此服务，但是管理员可以关闭或禁用此服务，使服务器实例对此类是不可见的。</span><span class="sxs-lookup"><span data-stu-id="13049-141">This service is enabled by default, but administrators may turn it off or disable it, making the server instance invisible to this class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13049-142">示例</span><span class="sxs-lookup"><span data-stu-id="13049-142">Example</span></span>  
 <span data-ttu-id="13049-143">以下控制台应用程序检索所有可见 SQL Server 实例的信息并在控制台窗口中显示该信息。</span><span class="sxs-lookup"><span data-stu-id="13049-143">The following console application retrieves information about all of the visible SQL Server instances and displays the information in the console window.</span></span>  
  
```vb  
Imports System.Data.Sql  
  
Module Module1  
  Sub Main()  
    ' Retrieve the enumerator instance and then the data.  
    Dim instance As SqlDataSourceEnumerator = _  
     SqlDataSourceEnumerator.Instance  
    Dim table As System.Data.DataTable = instance.GetDataSources()  
  
    ' Display the contents of the table.  
    DisplayData(table)  
  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Sub  
  
  Private Sub DisplayData(ByVal table As DataTable)  
    For Each row As DataRow In table.Rows  
      For Each col As DataColumn In table.Columns  
        Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
      Next  
      Console.WriteLine("============================")  
    Next  
  End Sub  
End Module  
```  
  
```csharp  
using System.Data.Sql;  
  
class Program  
{  
  static void Main()  
  {  
    // Retrieve the enumerator instance and then the data.  
    SqlDataSourceEnumerator instance =  
      SqlDataSourceEnumerator.Instance;  
    System.Data.DataTable table = instance.GetDataSources();  
  
    // Display the contents of the table.  
    DisplayData(table);  
  
    Console.WriteLine("Press any key to continue.");  
    Console.ReadKey();  
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
  
## <a name="see-also"></a><span data-ttu-id="13049-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="13049-144">See Also</span></span>  
 [<span data-ttu-id="13049-145">SQL Server 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="13049-145">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="13049-146">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="13049-146">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
