---
title: 通过 XML Web 服务使用数据集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
ms.openlocfilehash: ab96e8f3395a78c88184872a2c78b71fb2bf7b9e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43403456"
---
# <a name="consuming-a-dataset-from-an-xml-web-service"></a><span data-ttu-id="201df-102">通过 XML Web 服务使用数据集</span><span class="sxs-lookup"><span data-stu-id="201df-102">Consuming a DataSet from an XML Web Service</span></span>
<span data-ttu-id="201df-103"><xref:System.Data.DataSet> 是用断开式设计来构建的，其部分目的是为了便于通过 Internet 来传输数据。</span><span class="sxs-lookup"><span data-stu-id="201df-103">The <xref:System.Data.DataSet> was architected with a disconnected design, in part to facilitate the convenient transport of data over the Internet.</span></span> <span data-ttu-id="201df-104">**数据集**是"可序列化"，它可以被指定为输入还是输出而无需任何其他编码的 XML Web services 所需流式传输的内容**数据集**从 XML Web 服务到客户端并返回。</span><span class="sxs-lookup"><span data-stu-id="201df-104">The **DataSet** is "serializable" in that it can be specified as an input to or output from XML Web services without any additional coding required to stream the contents of the **DataSet** from an XML Web service to a client and back.</span></span> <span data-ttu-id="201df-105">**数据集**隐式转换为使用 DiffGram 格式的 XML 流、 通过网络发送和从 XML 流作为然后重新构造**数据集**在接收端。</span><span class="sxs-lookup"><span data-stu-id="201df-105">The **DataSet** is implicitly converted to an XML stream using the DiffGram format, sent over the network, and then reconstructed from the XML stream as a **DataSet** on the receiving end.</span></span> <span data-ttu-id="201df-106">它为你使用 XML Web services 传输和返回关系数据提供了非常简单而灵活的方法。</span><span class="sxs-lookup"><span data-stu-id="201df-106">This gives you a very simple and flexible method for transmitting and returning relational data using XML Web services.</span></span> <span data-ttu-id="201df-107">有关 DiffGram 格式的详细信息，请参阅[Diffgram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)。</span><span class="sxs-lookup"><span data-stu-id="201df-107">For more information about the DiffGram format, see [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span></span>  
  
 <span data-ttu-id="201df-108">下面的示例演示如何创建 XML Web 服务和使用客户端**数据集**传输关系数据 （包括修改后的数据） 并解决任何更新回原始数据源。</span><span class="sxs-lookup"><span data-stu-id="201df-108">The following example shows how to create an XML Web service and client that use the **DataSet** to transport relational data (including modified data) and resolve any updates back to the original data source.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="201df-109">我们建议你在创建 XML Web services 时，应始终考虑到安全问题。</span><span class="sxs-lookup"><span data-stu-id="201df-109">We recommend that you always consider security implications when creating an XML Web service.</span></span> <span data-ttu-id="201df-110">有关保护的 XML Web 服务的信息，请参阅[保护 ASP.NET XML Web Services 创建使用](https://msdn.microsoft.com/library/354b2ab1-2782-4542-b32a-dc560178b90c)。</span><span class="sxs-lookup"><span data-stu-id="201df-110">For information on securing an XML Web service, see [Securing XML Web Services Created Using ASP.NET](https://msdn.microsoft.com/library/354b2ab1-2782-4542-b32a-dc560178b90c).</span></span>  
  
### <a name="to-create-an-xml-web-service-that-returns-and-consumes-a-dataset"></a><span data-ttu-id="201df-111">创建返回和使用 DataSet 的 XML Web services</span><span class="sxs-lookup"><span data-stu-id="201df-111">To create an XML Web service that returns and consumes a DataSet</span></span>  
  
1.  <span data-ttu-id="201df-112">创建 XML Web services。</span><span class="sxs-lookup"><span data-stu-id="201df-112">Create the XML Web service.</span></span>  
  
     <span data-ttu-id="201df-113">在示例中，XML Web 服务创建返回数据，在此情况下从客户列表**Northwind**数据库，并接收**数据集**与更新数据，该 XML Web 服务解析回原始数据源。</span><span class="sxs-lookup"><span data-stu-id="201df-113">In the example, an XML Web service is created that returns data, in this case a list of customers from the **Northwind** database, and receives a **DataSet** with updates to the data, which the XML Web service resolves back to the original data source.</span></span>  
  
     <span data-ttu-id="201df-114">XML Web 服务公开两个方法： **GetCustomers**，以返回客户列表，并**UpdateCustomers**，以将更新解析回数据源。</span><span class="sxs-lookup"><span data-stu-id="201df-114">The XML Web service exposes two methods: **GetCustomers**, to return the list of customers, and **UpdateCustomers**, to resolve updates back to the data source.</span></span> <span data-ttu-id="201df-115">XML Web services 存储在 Web 服务器上名为 DataSetSample.asmx 的文件中。</span><span class="sxs-lookup"><span data-stu-id="201df-115">The XML Web service is stored in a file on the Web server called DataSetSample.asmx.</span></span> <span data-ttu-id="201df-116">下面的代码概括了 DataSetSample.asmx 的内容。</span><span class="sxs-lookup"><span data-stu-id="201df-116">The following code outlines the contents of DataSetSample.asmx.</span></span>  
  
    ```vb  
    <% @ WebService Language = "vb" Class = "Sample" %>  
    Imports System  
    Imports System.Data  
    Imports System.Data.SqlClient  
    Imports System.Web.Services  
  
    <WebService(Namespace:="http://microsoft.com/webservices/")> _  
    Public Class Sample  
  
    Public connection As SqlConnection = New SqlConnection("Data Source=(local);Integrated Security=SSPI;Initial Catalog=Northwind")  
  
      <WebMethod( Description := "Returns Northwind Customers", EnableSession := False )> _  
      Public Function GetCustomers() As DataSet  
        Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
          "SELECT CustomerID, CompanyName FROM Customers", connection)  
  
        Dim custDS As DataSet = New DataSet()  
        adapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
        adapter.Fill(custDS, "Customers")  
  
        Return custDS  
      End Function  
  
      <WebMethod( Description := "Updates Northwind Customers", EnableSession := False )> _  
      Public Function UpdateCustomers(custDS As DataSet) As DataSet  
        Dim adapter As SqlDataAdapter = New SqlDataAdapter()  
  
        adapter.InsertCommand = New SqlCommand( _  
          "INSERT INTO Customers (CustomerID, CompanyName) " & _  
          "Values(@CustomerID, @CompanyName)", connection)  
        adapter.InsertCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        adapter.InsertCommand.Parameters.Add( _  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
  
        adapter.UpdateCommand = New SqlCommand( _  
          "UPDATE Customers Set CustomerID = @CustomerID, " & _  
          "CompanyName = @CompanyName WHERE CustomerID = " & _  
          @OldCustomerID", connection)  
        adapter.UpdateCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        adapter.UpdateCommand.Parameters.Add( _  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
  
        Dim parameter As SqlParameter = _  
          adapter.UpdateCommand.Parameters.Add( _  
          "@OldCustomerID", SqlDbType.NChar, 5, "CustomerID")  
        parameter.SourceVersion = DataRowVersion.Original  
  
        adapter.DeleteCommand = New SqlCommand( _  
          "DELETE FROM Customers WHERE CustomerID = @CustomerID", _  
          connection)  
        parameter = adapter.DeleteCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        parameter.SourceVersion = DataRowVersion.Original  
  
        adapter.Update(custDS, "Customers")  
  
        Return custDS  
      End Function  
    End Class  
    ```  
  
    ```csharp  
    <% @ WebService Language = "C#" Class = "Sample" %>  
    using System;  
    using System.Data;  
    using System.Data.SqlClient;  
    using System.Web.Services;  
  
    [WebService(Namespace="http://microsoft.com/webservices/")]  
    public class Sample  
    {  
      public SqlConnection connection = new SqlConnection("Data Source=(local);Integrated Security=SSPI;Initial Catalog=Northwind");  
  
      [WebMethod( Description = "Returns Northwind Customers", EnableSession = false )]  
      public DataSet GetCustomers()  
      {  
        SqlDataAdapter adapter = new SqlDataAdapter(  
          "SELECT CustomerID, CompanyName FROM Customers", connection);  
  
        DataSet custDS = new DataSet();  
        adapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
        adapter.Fill(custDS, "Customers");  
  
        return custDS;  
      }  
  
      [WebMethod( Description = "Updates Northwind Customers",  
        EnableSession = false )]  
      public DataSet UpdateCustomers(DataSet custDS)  
      {  
        SqlDataAdapter adapter = new SqlDataAdapter();  
  
        adapter.InsertCommand = new SqlCommand(  
          "INSERT INTO Customers (CustomerID, CompanyName) " +  
          "Values(@CustomerID, @CompanyName)", connection);  
        adapter.InsertCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        adapter.InsertCommand.Parameters.Add(  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName");  
  
        adapter.UpdateCommand = new SqlCommand(  
          "UPDATE Customers Set CustomerID = @CustomerID, " +  
          "CompanyName = @CompanyName WHERE CustomerID = " +  
          "@OldCustomerID", connection);  
        adapter.UpdateCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        adapter.UpdateCommand.Parameters.Add(  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName");  
        SqlParameter parameter = adapter.UpdateCommand.Parameters.Add(  
          "@OldCustomerID", SqlDbType.NChar, 5, "CustomerID");  
        parameter.SourceVersion = DataRowVersion.Original;  
  
        adapter.DeleteCommand = new SqlCommand(  
        "DELETE FROM Customers WHERE CustomerID = @CustomerID",  
         connection);  
        parameter = adapter.DeleteCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        parameter.SourceVersion = DataRowVersion.Original;  
  
        adapter.Update(custDS, "Customers");  
  
        return custDS;  
      }  
    }  
    ```  
  
     <span data-ttu-id="201df-117">在典型方案中， **UpdateCustomers**会编写方法来捕获开放式并发冲突。</span><span class="sxs-lookup"><span data-stu-id="201df-117">In a typical scenario, the **UpdateCustomers** method would be written to catch optimistic concurrency violations.</span></span> <span data-ttu-id="201df-118">为了简单起见，以上示例没有包含此方法。</span><span class="sxs-lookup"><span data-stu-id="201df-118">For simplicity, the example does not include this.</span></span> <span data-ttu-id="201df-119">有关开放式并发的详细信息，请参阅[乐观并发](../../../../../docs/framework/data/adonet/optimistic-concurrency.md)。</span><span class="sxs-lookup"><span data-stu-id="201df-119">For more information about optimistic concurrency, see [Optimistic Concurrency](../../../../../docs/framework/data/adonet/optimistic-concurrency.md).</span></span>  
  
2.  <span data-ttu-id="201df-120">创建 XML Web services 代理。</span><span class="sxs-lookup"><span data-stu-id="201df-120">Create an XML Web service proxy.</span></span>  
  
     <span data-ttu-id="201df-121">XML Web services 的客户端将需要通过 SOAP 代理来使用公开的方法。</span><span class="sxs-lookup"><span data-stu-id="201df-121">Clients of the XML Web service require a SOAP proxy in order to consume the exposed methods.</span></span> <span data-ttu-id="201df-122">可以使用 Visual Studio 生成此代理。</span><span class="sxs-lookup"><span data-stu-id="201df-122">You can have Visual Studio generate this proxy for you.</span></span> <span data-ttu-id="201df-123">通过从 Visual Studio 中设置对现有 Web 服务的 Web 引用，此步骤中所述的所有行为均将透明地发生。</span><span class="sxs-lookup"><span data-stu-id="201df-123">By setting a Web reference to an existing Web service from within Visual Studio, all the behavior described in this step occurs transparently.</span></span> <span data-ttu-id="201df-124">如果要自己创建代理类，请继续阅读本讨论。</span><span class="sxs-lookup"><span data-stu-id="201df-124">If you want to create the proxy class yourself, continue with this discussion.</span></span> <span data-ttu-id="201df-125">但是，在大多数情况下，使用 Visual Studio 足以为客户端应用程序创建代理类。</span><span class="sxs-lookup"><span data-stu-id="201df-125">In most circumstances, however, using Visual Studio to create the proxy class for the client application is sufficient.</span></span>  
  
     <span data-ttu-id="201df-126">代理可以使用 Web 服务描述语言工具来创建。</span><span class="sxs-lookup"><span data-stu-id="201df-126">A proxy can be created using the Web Services Description Language Tool.</span></span> <span data-ttu-id="201df-127">例如，如果 XML Web 服务的 URL 公开 http://myserver/data/DataSetSample.asmx，发出的命令如下所示，若要使用的命名空间中创建的 Visual Basic.NET 代理**WebData.DSSample**并将其存储在文件 sample.vb 中。</span><span class="sxs-lookup"><span data-stu-id="201df-127">For example, if the XML Web service is exposed at the URL http://myserver/data/DataSetSample.asmx, issue a command such as the following to create a Visual Basic .NET proxy with a namespace of **WebData.DSSample** and store it in the file sample.vb.</span></span>  
  
    ```console
    wsdl /l:VB -out:sample.vb http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     <span data-ttu-id="201df-128">若要在文件 sample.cs 中创建一个 C# 代理，请发出以下命令。</span><span class="sxs-lookup"><span data-stu-id="201df-128">To create a C# proxy in the file sample.cs, issue the following command.</span></span>  
  
    ```console
    wsdl -l:CS -out:sample.cs http://myserver/data/DataSetSample.asmx -n:WebData.DSSample  
    ```  
  
     <span data-ttu-id="201df-129">然后，可以将该代理编译为库并导入 XML Web services 客户端。</span><span class="sxs-lookup"><span data-stu-id="201df-129">The proxy can then be compiled as a library and imported into the XML Web service client.</span></span> <span data-ttu-id="201df-130">若要将 sample.vb 中存储的 Visual Basic .NET 代理代码编译为 sample.dll，请发出以下命令。</span><span class="sxs-lookup"><span data-stu-id="201df-130">To compile the Visual Basic .NET proxy code stored in sample.vb as sample.dll, issue the following command.</span></span>  
  
    ```console  
    vbc -t:library -out:sample.dll sample.vb -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
     <span data-ttu-id="201df-131">若要将 sample.cs 中存储的 C# 代理代码编译为 sample.dll，请发出以下命令。</span><span class="sxs-lookup"><span data-stu-id="201df-131">To compile the C# proxy code stored in sample.cs as sample.dll, issue the following command.</span></span>  
  
    ```console
    csc -t:library -out:sample.dll sample.cs -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
3.  <span data-ttu-id="201df-132">创建 XML Web services 客户端。</span><span class="sxs-lookup"><span data-stu-id="201df-132">Create an XML Web service client.</span></span>  
  
     <span data-ttu-id="201df-133">如果你想要使用 Visual Studio 为你生成 Web 服务代理类，只需创建客户端项目中，并且，在解决方案资源管理器窗口中，右键单击项目，单击**添加 Web 引用**，并选择从 Web 服务（这可能需要提供的 Web 服务终结点地址，如果 Web 服务不可用当前解决方案中或在当前计算机上。） 的可用 Web 服务的列表如果自己创建 XML Web services 代理（按照前面的步骤所述），可以将其导入客户端代码并使用 XML Web services 方法。</span><span class="sxs-lookup"><span data-stu-id="201df-133">If you want to have Visual Studio generate the Web service proxy class for you, simply create the client project, and, in the Solution Explorer window, right-click the project, click **Add Web Reference**, and select the Web service from the list of available Web services (this may require supplying the address of the Web service endpoint, if the Web service isn't available within the current solution, or on the current computer.) If you create the XML Web service proxy yourself (as described in the previous step), you can import it into your client code and consume the XML Web service methods.</span></span> <span data-ttu-id="201df-134">下面的示例代码导入代理库，调用**GetCustomers**若要获取的客户，列表中添加新客户，然后返回**数据集**的更新的**UpdateCustomers**.</span><span class="sxs-lookup"><span data-stu-id="201df-134">The following sample code imports the proxy library, calls **GetCustomers** to get a list of customers, adds a new customer, and then returns a **DataSet** with the updates to **UpdateCustomers**.</span></span>  
  
     <span data-ttu-id="201df-135">请注意，该示例将**数据集**返回的**DataSet.GetChanges**到**UpdateCustomers**因为修改的行需要传递给**UpdateCustomers**。</span><span class="sxs-lookup"><span data-stu-id="201df-135">Notice that the example passes the **DataSet** returned by **DataSet.GetChanges** to **UpdateCustomers** because only modified rows need to be passed to **UpdateCustomers**.</span></span> <span data-ttu-id="201df-136">**UpdateCustomers**返回已解析**数据集**，然后，您可以**合并**到现有**数据集**合并的已解析的更改和任何从更新的行错误信息。</span><span class="sxs-lookup"><span data-stu-id="201df-136">**UpdateCustomers** returns the resolved **DataSet**, which you can then **Merge** into the existing **DataSet** to incorporate the resolved changes and any row error information from the update.</span></span> <span data-ttu-id="201df-137">以下代码假定您已经使用 Visual Studio 创建的 Web 引用，并且你已重命名为 DsSample 中的 Web 引用**添加 Web 引用**对话框。</span><span class="sxs-lookup"><span data-stu-id="201df-137">The following code assumes that you have used Visual Studio to create the Web reference, and that you have renamed the Web reference to DsSample in the **Add Web Reference** dialog box.</span></span>  
  
    ```vb  
    Imports System  
    Imports System.Data  
  
    Public Class Client  
  
      Public Shared Sub Main()  
        Dim proxySample As New DsSample.Sample ()  ' Proxy object.  
        Dim customersDataSet As DataSet = proxySample.GetCustomers()  
        Dim customersTable As DataTable = _  
          customersDataSet.Tables("Customers")  
  
        Dim rowAs DataRow = customersTable.NewRow()  
        row("CustomerID") = "ABCDE"  
        row("CompanyName") = "New Company Name"  
        customersTable.Rows.Add(row)  
  
        Dim updateDataSet As DataSet = _  
          proxySample.UpdateCustomers(customersDataSet.GetChanges())  
  
        customersDataSet.Merge(updateDataSet)  
        customersDataSet.AcceptChanges()  
      End Sub  
    End Class  
    ```  
  
    ```csharp  
    using System;  
    using System.Data;  
  
    public class Client  
    {  
      public static void Main()  
      {  
        Sample proxySample = new DsSample.Sample();  // Proxy object.  
        DataSet customersDataSet = proxySample.GetCustomers();  
        DataTable customersTable = customersDataSet.Tables["Customers"];  
  
        DataRow row = customersTable.NewRow();  
        row["CustomerID"] = "ABCDE";  
        row["CompanyName"] = "New Company Name";  
        customersTable.Rows.Add(row);  
  
        DataSet updateDataSet = new DataSet();  
  
        updateDataSet =   
          proxySample.UpdateCustomers(customersDataSet.GetChanges());  
  
        customersDataSet.Merge(updateDataSet);  
        customersDataSet.AcceptChanges();  
      }  
    }  
    ```  
  
     <span data-ttu-id="201df-138">如果决定自己创建代理类，必须执行下列额外的步骤。</span><span class="sxs-lookup"><span data-stu-id="201df-138">If you decide to create the proxy class yourself, you must take the following extra steps.</span></span> <span data-ttu-id="201df-139">若要编译该示例，将需要提供已创建的代理库 (sample.dll) 和相关的 .NET 库。</span><span class="sxs-lookup"><span data-stu-id="201df-139">To compile the sample, supply the proxy library that was created (sample.dll) and the related .NET libraries.</span></span> <span data-ttu-id="201df-140">若要编译该示例的 Visual Basic .NET 版本（存储在文件 client.vb 中），请发出以下命令。</span><span class="sxs-lookup"><span data-stu-id="201df-140">To compile the Visual Basic .NET version of the sample, stored in the file client.vb, issue the following command.</span></span>  
  
    ```console
    vbc client.vb -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
     <span data-ttu-id="201df-141">若要编译该示例的 C# 版本（存储在文件 client.cs 中），请发出以下命令。</span><span class="sxs-lookup"><span data-stu-id="201df-141">To compile the C# version of the sample, stored in the file client.cs, issue the following command.</span></span>  
  
    ```console
    csc client.cs -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="201df-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="201df-142">See Also</span></span>  
 [<span data-ttu-id="201df-143">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="201df-143">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)  
 [<span data-ttu-id="201df-144">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="201df-144">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="201df-145">数据表</span><span class="sxs-lookup"><span data-stu-id="201df-145">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="201df-146">从 DataAdapter 填充数据集</span><span class="sxs-lookup"><span data-stu-id="201df-146">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 [<span data-ttu-id="201df-147">使用 DataAdapter 更新数据源</span><span class="sxs-lookup"><span data-stu-id="201df-147">Updating Data Sources with DataAdapters</span></span>](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 [<span data-ttu-id="201df-148">DataAdapter 参数</span><span class="sxs-lookup"><span data-stu-id="201df-148">DataAdapter Parameters</span></span>](../../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 [<span data-ttu-id="201df-149">Web 服务描述语言工具 (Wsdl.exe)</span><span class="sxs-lookup"><span data-stu-id="201df-149">Web Services Description Language Tool (Wsdl.exe)</span></span>](https://msdn.microsoft.com/library/b9210348-8bc2-4367-8c91-d1a04b403e88)  
 [<span data-ttu-id="201df-150">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="201df-150">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
