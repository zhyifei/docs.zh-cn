---
title: "生成强类型化数据集"
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
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 61836196d9e11d3c87c43d4faaaeff54125bf706
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="generating-strongly-typed-datasets"></a><span data-ttu-id="6cb6c-102">生成强类型化数据集</span><span class="sxs-lookup"><span data-stu-id="6cb6c-102">Generating Strongly Typed DataSets</span></span>
<span data-ttu-id="6cb6c-103">如果给定符合 XML 架构定义语言 (XSD) 标准的 XML 架构，您就可以使用随 <xref:System.Data.DataSet> 提供的 XSD.exe 工具生成强类型 [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6cb6c-103">Given an XML Schema that complies with the XML Schema definition language (XSD) standard, you can generate a strongly typed <xref:System.Data.DataSet> using the XSD.exe tool provided with the [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)].</span></span>  
  
 <span data-ttu-id="6cb6c-104">(若要从数据库表创建 xsd，请参阅<xref:System.Data.DataSet.WriteXmlSchema%2A>或[使用 Visual Studio 中的数据集](http://msdn.microsoft.com/library/8bw9ksd6.aspx))。</span><span class="sxs-lookup"><span data-stu-id="6cb6c-104">(To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)).</span></span>  
  
 <span data-ttu-id="6cb6c-105">下面的代码演示生成的语法**数据集**使用此工具。</span><span class="sxs-lookup"><span data-stu-id="6cb6c-105">The following code shows the syntax for generating a **DataSet** using this tool.</span></span>  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 <span data-ttu-id="6cb6c-106">在此语法中，`/d`指令指示该工具生成**数据集**，和`/l:`指示该工具 （例如，C# 或 Visual Basic.NET） 使用哪种语言。</span><span class="sxs-lookup"><span data-stu-id="6cb6c-106">In this syntax, the `/d` directive tells the tool to generate a **DataSet**, and the `/l:` tells the tool what language to use (for example, C# or Visual Basic .NET).</span></span> <span data-ttu-id="6cb6c-107">可选`/eld`指令指定，你可以使用[!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)]对生成查询**数据集。**</span><span class="sxs-lookup"><span data-stu-id="6cb6c-107">The optional `/eld` directive specifies that you can use [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] to query against the generated **DataSet.**</span></span> <span data-ttu-id="6cb6c-108">当同时指定 `/d` 选项时可使用此选项。</span><span class="sxs-lookup"><span data-stu-id="6cb6c-108">This option is used when the `/d` option is also specified.</span></span> <span data-ttu-id="6cb6c-109">有关详细信息，请参阅[查询类型化数据集](../../../../../docs/framework/data/adonet/querying-typed-datasets.md)。</span><span class="sxs-lookup"><span data-stu-id="6cb6c-109">For more information, see [Querying Typed DataSets](../../../../../docs/framework/data/adonet/querying-typed-datasets.md).</span></span> <span data-ttu-id="6cb6c-110">可选`/n:`指令指示该工具还生成的命名空间**数据集**调用**XSDSchema.Namespace**。</span><span class="sxs-lookup"><span data-stu-id="6cb6c-110">The optional `/n:` directive tells the tool to also generate a namespace for the **DataSet** called **XSDSchema.Namespace**.</span></span> <span data-ttu-id="6cb6c-111">命令的输出为 XSDSchemaFileName.cs，该输出可以在 ADO.NET 应用程序中编译和使用。</span><span class="sxs-lookup"><span data-stu-id="6cb6c-111">The output of the command is XSDSchemaFileName.cs, which can be compiled and used in an ADO.NET application.</span></span> <span data-ttu-id="6cb6c-112">所生成的代码可以编译成库或模块。</span><span class="sxs-lookup"><span data-stu-id="6cb6c-112">The generated code can be compiled as a library or a module.</span></span>  
  
 <span data-ttu-id="6cb6c-113">以下代码显示使用 C# 编译器 (csc.exe) 将生成的代码编译成库的语法。</span><span class="sxs-lookup"><span data-stu-id="6cb6c-113">The following code shows the syntax for compiling the generated code as a library using the C# compiler (csc.exe).</span></span>  
  
```  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 <span data-ttu-id="6cb6c-114">`/t:` 指令指示该工具编译成库，`/r:` 指令指定进行编译所需的依赖库。</span><span class="sxs-lookup"><span data-stu-id="6cb6c-114">The `/t:` directive tells the tool to compile to a library, and the `/r:` directives specify dependent libraries required to compile.</span></span> <span data-ttu-id="6cb6c-115">该命令的输出为 XSDSchemaFileName.dll，它可以在使用 `/r:` 指令编译 ADO.NET 应用程序时传递给编译器。</span><span class="sxs-lookup"><span data-stu-id="6cb6c-115">The output of the command is XSDSchemaFileName.dll, which can be passed to the compiler when compiling an ADO.NET application with the `/r:` directive.</span></span>  
  
 <span data-ttu-id="6cb6c-116">以下代码显示访问向 ADO.NET 应用程序中的 XSD.exe 传递的命名空间的语法。</span><span class="sxs-lookup"><span data-stu-id="6cb6c-116">The following code shows the syntax for accessing the namespace passed to XSD.exe in an ADO.NET application.</span></span>  
  
```vb  
Imports XSDSchema.Namespace  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 <span data-ttu-id="6cb6c-117">下面的代码示例使用类型化**数据集**名为**CustomerDataSet**加载来自的客户列表**Northwind**数据库。</span><span class="sxs-lookup"><span data-stu-id="6cb6c-117">The following code example uses a typed **DataSet** named **CustomerDataSet** to load a list of customers from the **Northwind** database.</span></span> <span data-ttu-id="6cb6c-118">一旦加载数据使用**填充**方法，该示例循环访问每个客户**客户**表使用类型化**CustomersRow** (**DataRow**) 对象。</span><span class="sxs-lookup"><span data-stu-id="6cb6c-118">Once the data is loaded using the **Fill** method, the example loops through each customer in the **Customers** table using the typed **CustomersRow** (**DataRow**) object.</span></span> <span data-ttu-id="6cb6c-119">这提供直接访问权限**CustomerID**列，而不是通过**DataColumnCollection**。</span><span class="sxs-lookup"><span data-stu-id="6cb6c-119">This provides direct access to the **CustomerID** column, as opposed to through the **DataColumnCollection**.</span></span>  
  
```vb  
Dim customers As CustomerDataSet= New CustomerDataSet()  
Dim adapter As SqlDataAdapter New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers;", _  
  "Data Source=(local);Integrated " & _  
  "Security=SSPI;Initial Catalog=Northwind")  
  
adapter.Fill(customers, "Customers")  
  
Dim customerRow As CustomerDataSet.CustomersRow  
For Each customerRow In customers.Customers  
  Console.WriteLine(customerRow.CustomerID)  
Next  
```  
  
```csharp  
CustomerDataSet customers = new CustomerDataSet();  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers;",  
  "Data Source=(local);Integrated " +  
  "Security=SSPI;Initial Catalog=Northwind");  
  
adapter.Fill(customers, "Customers");  
  
foreach(CustomerDataSet.CustomersRow customerRow in customers.Customers)  
  Console.WriteLine(customerRow.CustomerID);  
```  
  
 <span data-ttu-id="6cb6c-120">下面是用于该示例的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="6cb6c-120">Following is the XML Schema used for the example.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6cb6c-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6cb6c-121">See Also</span></span>  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataSet>  
 [<span data-ttu-id="6cb6c-122">类型化数据集</span><span class="sxs-lookup"><span data-stu-id="6cb6c-122">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [<span data-ttu-id="6cb6c-123">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="6cb6c-123">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="6cb6c-124">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="6cb6c-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
