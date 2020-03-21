---
title: 枚举 SQL 服务器实例
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ddf1c83c-9d40-45e6-b04d-9828c6cbbfdc
ms.openlocfilehash: a707df533216613e34d9f357c7b9e035f73b9561
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148681"
---
# <a name="enumerating-instances-of-sql-server-adonet"></a><span data-ttu-id="b0c53-102">枚举 SQL Server 的实例 (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="b0c53-102">Enumerating Instances of SQL Server (ADO.NET)</span></span>
<span data-ttu-id="b0c53-103">SQL Server 允许应用程序在当前网络中查找 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="b0c53-103">SQL Server permits applications to find SQL Server instances within the current network.</span></span> <span data-ttu-id="b0c53-104"><xref:System.Data.Sql.SqlDataSourceEnumerator> 类向应用程序开发人员公开此信息，提供了包含所有可见服务器的相关信息的 <xref:System.Data.DataTable>。</span><span class="sxs-lookup"><span data-stu-id="b0c53-104">The <xref:System.Data.Sql.SqlDataSourceEnumerator> class exposes this information to the application developer, providing a <xref:System.Data.DataTable> containing information about all the visible servers.</span></span> <span data-ttu-id="b0c53-105">此返回的表包含网络上可用服务器实例的列表（该列表与用户尝试创建新连接时提供的列表匹配），并展开“连接属性”对话框上包含所有可用服务器的下拉列表\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0c53-105">This returned table contains a list of server instances available on the network that matches the list provided when a user attempts to create a new connection, and expands the drop-down list containing all the available servers on the **Connection Properties** dialog box.</span></span> <span data-ttu-id="b0c53-106">显示的结果并不总是完整的。</span><span class="sxs-lookup"><span data-stu-id="b0c53-106">The results displayed are not always complete.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b0c53-107">与大多数 Windows 服务一样，最好以尽可能小的特权运行 SQL Browser 服务。</span><span class="sxs-lookup"><span data-stu-id="b0c53-107">As with most Windows services, it is best to run the SQL Browser service with the least possible privileges.</span></span> <span data-ttu-id="b0c53-108">有关 SQL Browser 服务以及如何管理其行为的更多信息，请参见 SQL Server 联机丛书。</span><span class="sxs-lookup"><span data-stu-id="b0c53-108">See SQL Server Books Online for more information on the SQL Browser service, and how to manage its behavior.</span></span>  
  
## <a name="retrieving-an-enumerator-instance"></a><span data-ttu-id="b0c53-109">检索枚举器实例</span><span class="sxs-lookup"><span data-stu-id="b0c53-109">Retrieving an Enumerator Instance</span></span>  
 <span data-ttu-id="b0c53-110">若要检索包含有关可用 SQL Server 实例的信息的表，必须先使用共享/静态 <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A> 属性来检索枚举器：</span><span class="sxs-lookup"><span data-stu-id="b0c53-110">In order to retrieve the table containing information about the available SQL Server instances, you must first retrieve an enumerator, using the shared/static <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A> property:</span></span>  
  
```vb  
Dim instance As System.Data.Sql.SqlDataSourceEnumerator = _  
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
```csharp  
System.Data.Sql.SqlDataSourceEnumerator instance =
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
 <span data-ttu-id="b0c53-111">检索静态实例后，可以调用 <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A> 方法，此方法返回包含可用服务器的相关信息的 <xref:System.Data.DataTable>：</span><span class="sxs-lookup"><span data-stu-id="b0c53-111">Once you have retrieved the static instance, you can call the <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A> method, which returns a <xref:System.Data.DataTable> containing information about the available servers:</span></span>  
  
```vb  
Dim dataTable As System.Data.DataTable = instance.GetDataSources()  
```  
  
```csharp  
System.Data.DataTable dataTable = instance.GetDataSources();  
```  
  
 <span data-ttu-id="b0c53-112">通过方法调用返回的表包含以下列，其中所有列都包含 `string` 值：</span><span class="sxs-lookup"><span data-stu-id="b0c53-112">The table returned from the method call contains the following columns, all of which contain `string` values:</span></span>  
  
|<span data-ttu-id="b0c53-113">列</span><span class="sxs-lookup"><span data-stu-id="b0c53-113">Column</span></span>|<span data-ttu-id="b0c53-114">说明</span><span class="sxs-lookup"><span data-stu-id="b0c53-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b0c53-115">**服务器名称**</span><span class="sxs-lookup"><span data-stu-id="b0c53-115">**ServerName**</span></span>|<span data-ttu-id="b0c53-116">服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="b0c53-116">Name of the server.</span></span>|  
|<span data-ttu-id="b0c53-117">**实例名称**</span><span class="sxs-lookup"><span data-stu-id="b0c53-117">**InstanceName**</span></span>|<span data-ttu-id="b0c53-118">服务器实例的名称。</span><span class="sxs-lookup"><span data-stu-id="b0c53-118">Name of the server instance.</span></span> <span data-ttu-id="b0c53-119">如果服务器作为默认实例运行，则为空。</span><span class="sxs-lookup"><span data-stu-id="b0c53-119">Blank if the server is running as the default instance.</span></span>|  
|<span data-ttu-id="b0c53-120">**IsClustered**</span><span class="sxs-lookup"><span data-stu-id="b0c53-120">**IsClustered**</span></span>|<span data-ttu-id="b0c53-121">指明服务器是否属于群集。</span><span class="sxs-lookup"><span data-stu-id="b0c53-121">Indicates whether the server is part of a cluster.</span></span>|  
|<span data-ttu-id="b0c53-122">**版本**</span><span class="sxs-lookup"><span data-stu-id="b0c53-122">**Version**</span></span>|<span data-ttu-id="b0c53-123">服务器的版本。</span><span class="sxs-lookup"><span data-stu-id="b0c53-123">Version of the server.</span></span> <span data-ttu-id="b0c53-124">例如：</span><span class="sxs-lookup"><span data-stu-id="b0c53-124">For example:</span></span><br /><br /> <span data-ttu-id="b0c53-125">-   9.00.x (SQL Server 2005)</span><span class="sxs-lookup"><span data-stu-id="b0c53-125">-   9.00.x (SQL Server 2005)</span></span><br /><span data-ttu-id="b0c53-126">-   10.0.xx (SQL Server 2008)</span><span class="sxs-lookup"><span data-stu-id="b0c53-126">-   10.0.xx (SQL Server 2008)</span></span><br /><span data-ttu-id="b0c53-127">-   10.50.x (SQL Server 2008 R2)</span><span class="sxs-lookup"><span data-stu-id="b0c53-127">-   10.50.x (SQL Server 2008 R2)</span></span><br /><span data-ttu-id="b0c53-128">-   11.0.xx (SQL Server 2012)</span><span class="sxs-lookup"><span data-stu-id="b0c53-128">-   11.0.xx (SQL Server 2012)</span></span>|  
  
## <a name="enumeration-limitations"></a><span data-ttu-id="b0c53-129">枚举限制</span><span class="sxs-lookup"><span data-stu-id="b0c53-129">Enumeration Limitations</span></span>  
 <span data-ttu-id="b0c53-130">不一定会列出所有可用服务器。</span><span class="sxs-lookup"><span data-stu-id="b0c53-130">All of the available servers may or may not be listed.</span></span> <span data-ttu-id="b0c53-131">此列表因超时和网络流量等因素而异。</span><span class="sxs-lookup"><span data-stu-id="b0c53-131">The list can vary depending on factors such as timeouts and network traffic.</span></span> <span data-ttu-id="b0c53-132">这可能会导致两次连续调用生成不同的列表。</span><span class="sxs-lookup"><span data-stu-id="b0c53-132">This can cause the list to be different on two consecutive calls.</span></span> <span data-ttu-id="b0c53-133">只有同一网络中的服务器才列出。</span><span class="sxs-lookup"><span data-stu-id="b0c53-133">Only servers on the same network will be listed.</span></span> <span data-ttu-id="b0c53-134">广播数据包通常不会遍历路由器，正因为此，可能看不到列出的服务器，但它跨调用是稳定的。</span><span class="sxs-lookup"><span data-stu-id="b0c53-134">Broadcast packets typically won't traverse routers, which is why you may not see a server listed, but it will be stable across calls.</span></span>  
  
 <span data-ttu-id="b0c53-135">列出的服务器不一定包含 `IsClustered` 和版本等其他信息。</span><span class="sxs-lookup"><span data-stu-id="b0c53-135">Listed servers may or may not have additional information such as `IsClustered` and version.</span></span> <span data-ttu-id="b0c53-136">这取决于列表的获取方式。</span><span class="sxs-lookup"><span data-stu-id="b0c53-136">This is dependent on how the list was obtained.</span></span> <span data-ttu-id="b0c53-137">通过 SQL Server 浏览器服务列出的服务器比通过 Windows 基础结构发现的服务器具有更详细的信息，后者仅列出名称。</span><span class="sxs-lookup"><span data-stu-id="b0c53-137">Servers listed through the SQL Server browser service will have more details than those found through the Windows infrastructure, which will list only the name.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b0c53-138">仅当在完全信任的环境中运行时，服务器枚举才可用。</span><span class="sxs-lookup"><span data-stu-id="b0c53-138">Server enumeration is only available when running in full-trust.</span></span> <span data-ttu-id="b0c53-139">在部分信任的环境中运行的程序集无法使用它，即使拥有 <xref:System.Data.SqlClient.SqlClientPermission> 代码访问安全性 (CAS) 权限，也不例外。</span><span class="sxs-lookup"><span data-stu-id="b0c53-139">Assemblies running in a partially-trusted environment will not be able to use it, even if they have the <xref:System.Data.SqlClient.SqlClientPermission> Code Access Security (CAS) permission.</span></span>  
  
 <span data-ttu-id="b0c53-140">SQL Server 通过使用名为 SQL Browser 的外部 Windows 服务来提供 <xref:System.Data.Sql.SqlDataSourceEnumerator> 的信息。</span><span class="sxs-lookup"><span data-stu-id="b0c53-140">SQL Server provides information for the <xref:System.Data.Sql.SqlDataSourceEnumerator> through the use of an external Windows service named SQL Browser.</span></span> <span data-ttu-id="b0c53-141">此服务默认处于启用状态，但管理员可以禁用它，让服务器实例对此类不可见。</span><span class="sxs-lookup"><span data-stu-id="b0c53-141">This service is enabled by default, but administrators may turn it off or disable it, making the server instance invisible to this class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0c53-142">示例</span><span class="sxs-lookup"><span data-stu-id="b0c53-142">Example</span></span>  
 <span data-ttu-id="b0c53-143">以下控制台应用程序检索所有可见 SQL Server 实例的信息，并在控制台窗口中显示该信息。</span><span class="sxs-lookup"><span data-stu-id="b0c53-143">The following console application retrieves information about all of the visible SQL Server instances and displays the information in the console window.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b0c53-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0c53-144">See also</span></span>

- [<span data-ttu-id="b0c53-145">SQL Server 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b0c53-145">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="b0c53-146">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="b0c53-146">ADO.NET Overview</span></span>](../ado-net-overview.md)
