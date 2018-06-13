---
title: 数据集和 XmlDataDocument 同步
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
ms.openlocfilehash: cb16d4fae5dc153361fe2cb31cfd6af9b4b83c68
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759161"
---
# <a name="dataset-and-xmldatadocument-synchronization"></a><span data-ttu-id="0d833-102">数据集和 XmlDataDocument 同步</span><span class="sxs-lookup"><span data-stu-id="0d833-102">DataSet and XmlDataDocument Synchronization</span></span>
<span data-ttu-id="0d833-103">ADO.NET <xref:System.Data.DataSet> 为您提供了数据的关系表示形式。</span><span class="sxs-lookup"><span data-stu-id="0d833-103">The ADO.NET <xref:System.Data.DataSet> provides you with a relational representation of data.</span></span> <span data-ttu-id="0d833-104">若要实现分层数据访问，可以使用 .NET Framework 中的可用 XML 类。</span><span class="sxs-lookup"><span data-stu-id="0d833-104">For hierarchical data access, you can use the XML classes available in the .NET Framework.</span></span> <span data-ttu-id="0d833-105">以前，数据的这两种表示形式是单独使用的。</span><span class="sxs-lookup"><span data-stu-id="0d833-105">Historically, these two representations of data have been used separately.</span></span> <span data-ttu-id="0d833-106">不过，.NET Framework 允许对通过数据的关系和分层表示的实时同步访问**数据集**对象和<xref:System.Xml.XmlDataDocument>对象，分别。</span><span class="sxs-lookup"><span data-stu-id="0d833-106">However, the .NET Framework enables real-time, synchronous access to both the relational and hierarchical representations of data through the **DataSet** object and the <xref:System.Xml.XmlDataDocument> object, respectively.</span></span>  
  
 <span data-ttu-id="0d833-107">当**数据集**与同步**XmlDataDocument**，这两个对象都使用一组数据。</span><span class="sxs-lookup"><span data-stu-id="0d833-107">When a **DataSet** is synchronized with an **XmlDataDocument**, both objects are working with a single set of data.</span></span> <span data-ttu-id="0d833-108">这意味着，如果更改到**数据集**，此更改将反映在**XmlDataDocument**，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="0d833-108">This means that if a change is made to the **DataSet**, the change will be reflected in the **XmlDataDocument**, and vice versa.</span></span> <span data-ttu-id="0d833-109">之间的关系**数据集**和**XmlDataDocument**通过允许单个应用程序，使用一组数据，访问生成的服务的整个套件创建极大的灵活性围绕**数据集**（如 Web 窗体和 Windows 窗体控件和 Visual Studio.NET 设计器），以及包括可扩展样式表语言 (XSL)、 XSL 转换 (XSLT) 和 XML 路径的所有 XML 服务套件语言 (XPath)。</span><span class="sxs-lookup"><span data-stu-id="0d833-109">The relationship between the **DataSet** and the **XmlDataDocument** creates great flexibility by allowing a single application, using a single set of data, to access the entire suite of services built around the **DataSet** (such as Web Forms and Windows Forms controls, and Visual Studio .NET designers), as well as the suite of XML services including Extensible Stylesheet Language (XSL), XSL Transformations (XSLT), and XML Path Language (XPath).</span></span> <span data-ttu-id="0d833-110">您不必选择使应用程序以哪一组服务为目标，这两组服务都可用。</span><span class="sxs-lookup"><span data-stu-id="0d833-110">You do not have to choose which set of services to target with the application; both are available.</span></span>  
  
 <span data-ttu-id="0d833-111">有多种方法可以同步**数据集**与**XmlDataDocument**。</span><span class="sxs-lookup"><span data-stu-id="0d833-111">There are several ways that you can synchronize a **DataSet** with an **XmlDataDocument**.</span></span> <span data-ttu-id="0d833-112">你可以：</span><span class="sxs-lookup"><span data-stu-id="0d833-112">You can:</span></span>  
  
-   <span data-ttu-id="0d833-113">填充**数据集**使用架构 （即关系结构） 和数据，然后使其与新同步**XmlDataDocument**。</span><span class="sxs-lookup"><span data-stu-id="0d833-113">Populate a **DataSet** with schema (that is, a relational structure) and data and then synchronize it with a new **XmlDataDocument**.</span></span> <span data-ttu-id="0d833-114">这将提供现有关系数据的分层视图。</span><span class="sxs-lookup"><span data-stu-id="0d833-114">This provides a hierarchical view of existing relational data.</span></span> <span data-ttu-id="0d833-115">例如：</span><span class="sxs-lookup"><span data-stu-id="0d833-115">For example:</span></span>  
  
    ```vb  
    Dim dataSet As DataSet = New DataSet  
  
    ' Add code here to populate the DataSet with schema and data.  
  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)  
    ```  
  
    ```csharp  
    DataSet dataSet = new DataSet();  
  
    // Add code here to populate the DataSet with schema and data.  
  
    XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);  
    ```  
  
-   <span data-ttu-id="0d833-116">填充**数据集**仅使用架构 (如强类型化**数据集**)，使其与同步**XmlDataDocument**，，然后加载**XmlDataDocument**从 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="0d833-116">Populate a **DataSet** with schema only (such as a strongly typed **DataSet**), synchronize it with an **XmlDataDocument**, and then load the **XmlDataDocument** from an XML document.</span></span> <span data-ttu-id="0d833-117">这将提供现有分层数据的关系视图。</span><span class="sxs-lookup"><span data-stu-id="0d833-117">This provides a relational view of existing hierarchical data.</span></span> <span data-ttu-id="0d833-118">表名称和中的列名称你**数据集**架构必须匹配要与其同步的 XML 元素名称。</span><span class="sxs-lookup"><span data-stu-id="0d833-118">The table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="0d833-119">该匹配区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0d833-119">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="0d833-120">请注意的架构**数据集**只需匹配要在关系视图中公开的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="0d833-120">Note that the schema of the **DataSet** only needs to match the XML elements that you want to expose in your relational view.</span></span> <span data-ttu-id="0d833-121">这样，就可以具有非常大的 XML 文档，而该文档上可以有非常小的关系“窗口”。</span><span class="sxs-lookup"><span data-stu-id="0d833-121">This way, you can have a very large XML document and a very small relational "window" on that document.</span></span> <span data-ttu-id="0d833-122">**XmlDataDocument**即使保留整个 XML 文档**数据集**仅公开它的一小部分。</span><span class="sxs-lookup"><span data-stu-id="0d833-122">The **XmlDataDocument** preserves the entire XML document even though the **DataSet** only exposes a small portion of it.</span></span> <span data-ttu-id="0d833-123">(这的详细示例，请参阅[使 DataSet 与 XmlDataDocument 同步](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)。)</span><span class="sxs-lookup"><span data-stu-id="0d833-123">(For a detailed example of this, see [Synchronizing a DataSet with an XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)</span></span>  
  
     <span data-ttu-id="0d833-124">下面的代码示例演示的步骤创建**数据集**和填充其架构，然后将其与同步**XmlDataDocument**。</span><span class="sxs-lookup"><span data-stu-id="0d833-124">The following code example shows the steps for creating a **DataSet** and populating its schema, then synchronizing it with an **XmlDataDocument**.</span></span> <span data-ttu-id="0d833-125">请注意，**数据集**架构只需要匹配中的元素**XmlDataDocument**你想要公开使用**数据集**。</span><span class="sxs-lookup"><span data-stu-id="0d833-125">Note that the **DataSet** schema only needs to match the elements from the **XmlDataDocument** that you want to expose using the **DataSet**.</span></span>  
  
    ```vb  
    Dim dataSet As DataSet = New DataSet  
  
    ' Add code here to populate the DataSet with schema, but not data.  
  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)  
    xmlDoc.Load("XMLDocument.xml")  
    ```  
  
    ```csharp  
    DataSet dataSet = new DataSet();  
  
    // Add code here to populate the DataSet with schema, but not data.  
  
    XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);  
    xmlDoc.Load("XMLDocument.xml");  
    ```  
  
     <span data-ttu-id="0d833-126">无法加载**XmlDataDocument**如果与同步**数据集**包含数据。</span><span class="sxs-lookup"><span data-stu-id="0d833-126">You cannot load an **XmlDataDocument** if it is synchronized with a **DataSet** that contains data.</span></span> <span data-ttu-id="0d833-127">否则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="0d833-127">An exception will be thrown.</span></span>  
  
-   <span data-ttu-id="0d833-128">创建一个新**XmlDataDocument**和从 XML 文档，加载它，然后访问的数据使用的关系视图**数据集**属性**XmlDataDocument**。</span><span class="sxs-lookup"><span data-stu-id="0d833-128">Create a new **XmlDataDocument** and load it from an XML document, and then access the relational view of the data using the **DataSet** property of the **XmlDataDocument**.</span></span> <span data-ttu-id="0d833-129">你需要设置的架构**数据集**你可以查看任何中的数据之前**XmlDataDocument**使用**数据集**。</span><span class="sxs-lookup"><span data-stu-id="0d833-129">You need to set the schema of the **DataSet** before you can view any of the data in the **XmlDataDocument** using the **DataSet**.</span></span> <span data-ttu-id="0d833-130">中的表名称和列的名称同样，你**数据集**架构必须匹配要与其同步的 XML 元素名称。</span><span class="sxs-lookup"><span data-stu-id="0d833-130">Again, the table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="0d833-131">该匹配区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0d833-131">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="0d833-132">下面的代码示例演示如何访问中的数据的关系视图**XmlDataDocument**。</span><span class="sxs-lookup"><span data-stu-id="0d833-132">The following code example shows how to access the relational view of the data in an **XmlDataDocument**.</span></span>  
  
    ```vb  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument  
    Dim dataSet As DataSet = xmlDoc.DataSet  
  
    ' Add code here to create the schema of the DataSet to view the data.  
  
    xmlDoc.Load("XMLDocument.xml")  
    ```  
  
    ```csharp  
    XmlDataDocument xmlDoc = new XmlDataDocument();  
    DataSet dataSet = xmlDoc.DataSet;  
  
    // Add code here to create the schema of the DataSet to view the data.  
  
    xmlDoc.Load("XMLDocument.xml");  
    ```  
  
 <span data-ttu-id="0d833-133">同步的另一个优点**XmlDataDocument**与**数据集**是避免了 XML 文档的失真。</span><span class="sxs-lookup"><span data-stu-id="0d833-133">Another advantage of synchronizing an **XmlDataDocument** with a **DataSet** is that the fidelity of an XML document is preserved.</span></span> <span data-ttu-id="0d833-134">如果**数据集**填充从 XML 文档使用**ReadXml**，当将数据写回作为 XML 文档使用**WriteXml**可能大大不同于原始 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="0d833-134">If the **DataSet** is populated from an XML document using **ReadXml**, when the data is written back as an XML document using **WriteXml** it may differ dramatically from the original XML document.</span></span> <span data-ttu-id="0d833-135">这是因为**数据集**不维护格式设置，如空格或分层信息，如元素顺序，从 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="0d833-135">This is because the **DataSet** does not maintain formatting, such as white space, or hierarchical information, such as element order, from the XML document.</span></span> <span data-ttu-id="0d833-136">**数据集**也不包含 XML 文档中已忽略，因为它们与的架构不匹配的元素**数据集**。</span><span class="sxs-lookup"><span data-stu-id="0d833-136">The **DataSet** also does not contain elements from the XML document that were ignored because they did not match the schema of the **Dataset**.</span></span> <span data-ttu-id="0d833-137">同步**XmlDataDocument**与**数据集**允许在中维护初始 XML 文档的格式设置和分层元素结构**XmlDataDocument**，虽然**数据集**包含唯一的数据和架构信息适用于**数据集**。</span><span class="sxs-lookup"><span data-stu-id="0d833-137">Synchronizing an **XmlDataDocument** with a **DataSet** allows the formatting and hierarchical element structure of the original XML document to be maintained in the **XmlDataDocument**, while the **DataSet** contains only data and schema information appropriate to the **DataSet**.</span></span>  
  
 <span data-ttu-id="0d833-138">同步时**数据集**与**XmlDataDocument**，结果可能会有所不同，具体取决于是否你<xref:System.Data.DataRelation>对象是否嵌套。</span><span class="sxs-lookup"><span data-stu-id="0d833-138">When synchronizing a **DataSet** with an **XmlDataDocument**, results may differ depending on whether or not your <xref:System.Data.DataRelation> objects are nested.</span></span> <span data-ttu-id="0d833-139">有关详细信息，请参阅[嵌套 Datarelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)。</span><span class="sxs-lookup"><span data-stu-id="0d833-139">For more information, see [Nesting DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0d833-140">本节内容</span><span class="sxs-lookup"><span data-stu-id="0d833-140">In This Section</span></span>  
 [<span data-ttu-id="0d833-141">将数据集与 XmlDataDocument 同步</span><span class="sxs-lookup"><span data-stu-id="0d833-141">Synchronizing a DataSet with an XmlDataDocument</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 <span data-ttu-id="0d833-142">演示同步强类型化**数据集**，使用最小的架构与**XmlDataDocument**。</span><span class="sxs-lookup"><span data-stu-id="0d833-142">Demonstrates synchronizing a strongly typed **DataSet**, with minimal schema, with an **XmlDataDocument**.</span></span>  
  
 [<span data-ttu-id="0d833-143">对数据集执行 XPath 查询</span><span class="sxs-lookup"><span data-stu-id="0d833-143">Performing an XPath Query on a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 <span data-ttu-id="0d833-144">演示的内容执行 XPath 查询**数据集**。</span><span class="sxs-lookup"><span data-stu-id="0d833-144">Demonstrates performing an XPath query on the contents of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="0d833-145">将 XSLT 转换应用于 DataSet</span><span class="sxs-lookup"><span data-stu-id="0d833-145">Applying an XSLT Transform to a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 <span data-ttu-id="0d833-146">演示将 XSLT 转换应用于的内容**数据集**。</span><span class="sxs-lookup"><span data-stu-id="0d833-146">Demonstrates applying an XSLT transform to the contents of a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0d833-147">相关章节</span><span class="sxs-lookup"><span data-stu-id="0d833-147">Related Sections</span></span>  
 [<span data-ttu-id="0d833-148">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="0d833-148">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="0d833-149">描述如何**数据集**作为数据源，包括加载和保持的内容与 XML 进行交互**数据集**以 XML 数据形式。</span><span class="sxs-lookup"><span data-stu-id="0d833-149">Describes how the **DataSet** interacts with XML as a data source, including loading and persisting the contents of a **DataSet** as XML data.</span></span>  
  
 [<span data-ttu-id="0d833-150">嵌套 DataRelation</span><span class="sxs-lookup"><span data-stu-id="0d833-150">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 <span data-ttu-id="0d833-151">讨论的重要性嵌套**DataRelation**对象表示的内容时**数据集**作为 XML 数据，并描述如何创建这些关系。</span><span class="sxs-lookup"><span data-stu-id="0d833-151">Discusses the importance of nested **DataRelation** objects when representing the contents of a **DataSet** as XML data, and describes how to create these relations.</span></span>  
  
 [<span data-ttu-id="0d833-152">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="0d833-152">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="0d833-153">描述**数据集**以及如何使用它来管理应用程序数据和与数据源包括关系数据库和 XML 进行交互。</span><span class="sxs-lookup"><span data-stu-id="0d833-153">Describes the **DataSet** and how to use it to manage application data and to interact with data sources including relational databases and XML.</span></span>  
  
 <xref:System.Xml.XmlDataDocument>  
 <span data-ttu-id="0d833-154">包含有关引用信息**XmlDataDocument**类。</span><span class="sxs-lookup"><span data-stu-id="0d833-154">Contains reference information about the **XmlDataDocument** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d833-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="0d833-155">See Also</span></span>  
 [<span data-ttu-id="0d833-156">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="0d833-156">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
