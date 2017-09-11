---
title: "在 Visual Basic 中的 XML IntelliSense |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, XML
- XML IntelliSense [Visual Basic]
- XML [Visual Basic], IntelliSense
- IntelliSense [Visual Basic], XML
ms.assetid: 59506ce9-d64e-417e-90fc-e9fe19f0a8fa
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: 9a3c6f923bc9458997c388d4cf74ca113265a8cc
ms.contentlocale: zh-cn
ms.lasthandoff: 06/01/2017

---
# <a name="xml-intellisense-in-visual-basic"></a><span data-ttu-id="59995-102">Visual Basic 中的 XML IntelliSense</span><span class="sxs-lookup"><span data-stu-id="59995-102">XML IntelliSense in Visual Basic</span></span>
<span data-ttu-id="59995-103">Visual Basic 代码编辑器包括提供 XML 架构中定义的元素的单词自动完成的 XML IntelliSense 功能。</span><span class="sxs-lookup"><span data-stu-id="59995-103">The Visual Basic Code Editor includes IntelliSense features for XML that provide word completion for elements defined in an XML schema.</span></span> <span data-ttu-id="59995-104">如果您在项目中包含的 XML 架构定义 (XSD) 文件，并使用导入架构的目标命名空间`Imports`语句中，代码编辑器中将包括的 XSD 架构中的元素，在 IntelliSense 列表中的有效成员变量<xref:System.Xml.Linq.XElement>和<xref:System.Xml.Linq.XDocument>对象。</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="59995-104">If you include an XML Schema Definition (XSD) file in your project and import the target namespace of the schema by using the `Imports` statement, the Code Editor will include elements from the XSD schema in the IntelliSense list of valid member variables for <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="59995-105">下图显示了 IntelliSense 成员列表的<xref:System.Xml.Linq.XElement>对象。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="59995-105">The following illustration shows the IntelliSense members list for an <xref:System.Xml.Linq.XElement> object.</span></span>  
  
 <span data-ttu-id="59995-106">![在 Visual Basic 中的 XML IntelliSense](../../../../visual-basic/programming-guide/language-features/xml/media/xml_intellisense.png "XML_Intellisense")</span><span class="sxs-lookup"><span data-stu-id="59995-106">![XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/media/xml_intellisense.png "XML_Intellisense")</span></span>  
<span data-ttu-id="59995-107">XML IntelliSense</span><span class="sxs-lookup"><span data-stu-id="59995-107">XML IntelliSense</span></span>  
  
## <a name="enabling-xml-intellisense-in-visual-basic"></a><span data-ttu-id="59995-108">在 Visual Basic 中启用 XML IntelliSense</span><span class="sxs-lookup"><span data-stu-id="59995-108">Enabling XML IntelliSense in Visual Basic</span></span>  
 <span data-ttu-id="59995-109">若要启用 XML IntelliSense 在 Visual Basic 中，必须在 Visual Basic 项目中包括 XSD 架构文件。</span><span class="sxs-lookup"><span data-stu-id="59995-109">To enable XML IntelliSense in Visual Basic, you must include an XSD schema file in your Visual Basic project.</span></span> <span data-ttu-id="59995-110">您还必须导入的 XSD 架构的目标命名空间到代码文件使用`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="59995-110">You must also import the target namespace for the XSD schema into your code file by using the `Imports` statement.</span></span> <span data-ttu-id="59995-111">或者，您可以通过将添加的目标命名空间到项目级别命名空间列表**引用**Visual Basic 项目设计器的页面。</span><span class="sxs-lookup"><span data-stu-id="59995-111">Alternatively, you can add the target namespace to the project-level namespace list by using the **References** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="59995-112">有关示例，请参阅[如何︰ 在 Visual Basic 中启用 XML IntelliSense](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md)。</span><span class="sxs-lookup"><span data-stu-id="59995-112">For examples, see [How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).</span></span> <span data-ttu-id="59995-113">有关详细信息，请参阅[Imports 语句 (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)和[，项目设计器 (Visual Basic 中) 引用页](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="59995-113">For more information, see [Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) and [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="59995-114">请注意，默认您无法看到在 Visual Basic 项目的 XSD 架构文件。</span><span class="sxs-lookup"><span data-stu-id="59995-114">Note that by default you cannot see XSD schema files in Visual Basic projects.</span></span> <span data-ttu-id="59995-115">您可能需要单击**显示所有文件**按钮以选择要包括在项目中的 XSD 文件。</span><span class="sxs-lookup"><span data-stu-id="59995-115">You may have to click the **Show All Files** button to select an XSD file to include in your project.</span></span>  
  
### <a name="generating-a-schema-file-schema-inference"></a><span data-ttu-id="59995-116">生成架构文件 （架构推断）</span><span class="sxs-lookup"><span data-stu-id="59995-116">Generating a Schema File (Schema Inference)</span></span>  
 <span data-ttu-id="59995-117">可以通过使用 Visual Studio XML 工具推断 XSD 架构来创建针对现有的 XML 文件的 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="59995-117">You can create an XSD schema for an existing XML file by inferring the XSD schema by using Visual Studio XML tools.</span></span>  
  
-   <span data-ttu-id="59995-118">从 SP1 开始，您可以使用 XML 到架构向导创建的 XML 架构集，则会推断从一个或多个 XML 文档并将其包含您的项目。</span><span class="sxs-lookup"><span data-stu-id="59995-118">Starting in SP1, you can use the XML to Schema Wizard to create an XML Schema set that is inferred from one or more XML documents and include it your project.</span></span> <span data-ttu-id="59995-119">可以使用文本文件、 XML 从 HTTP Internet 地址或键入或粘贴到 XML 到架构向导的 XML 形式的 XML 文档的任意组合。</span><span class="sxs-lookup"><span data-stu-id="59995-119">You can use any combination of XML documents in the form of text files, XML from HTTP Internet addresses, or XML that is typed or pasted into the XML to Schema Wizard.</span></span> <span data-ttu-id="59995-120">若要访问 XML 到架构向导，请单击**添加新项**上**项目**菜单上，并添加**XML 到架构**模板**数据**或**常用项**模板组。</span><span class="sxs-lookup"><span data-stu-id="59995-120">To access the XML to Schema Wizard, click **Add New Item** on the **Project** menu and add an **XML to Schema** template from either the **Data** or **Common Items** template group.</span></span> <span data-ttu-id="59995-121">包括了要推断从 XML 架构集的所有 XML 文档源之后，单击**确定**创建推断出的架构集。</span><span class="sxs-lookup"><span data-stu-id="59995-121">After you have included all the XML document sources to infer the XML Schema set from, click **OK** to create the inferred schema set.</span></span> <span data-ttu-id="59995-122">有关详细信息，请参阅[XML 到架构向导](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md)。</span><span class="sxs-lookup"><span data-stu-id="59995-122">For more information, see [XML to Schema Wizard](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md).</span></span>  
  
-   <span data-ttu-id="59995-123">Visual Studio XML 编辑器还可用于推断 XSD 架构将设置从 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="59995-123">You can also use the Visual Studio XML Editor to infer an XSD schema set from an XML file.</span></span> <span data-ttu-id="59995-124">要创建 XML 架构使用 XML 编辑器设置，请在 Visual Studio XML 设计器中打开 XML 文件，然后单击**Create Schema**上**XML**菜单。</span><span class="sxs-lookup"><span data-stu-id="59995-124">To create an XML schema set by using the XML Editor, open an XML file in the Visual Studio XML Designer and then click **Create Schema** on the **XML** menu.</span></span> <span data-ttu-id="59995-125">在创建 XSD 架构集后，可以将所创建的架构集保存到一个或多个 XSD 文件并将它们包括在你的项目。</span><span class="sxs-lookup"><span data-stu-id="59995-125">After you create the XSD schema set, you can save the created schema set to one or more XSD files and include them in your project.</span></span> <span data-ttu-id="59995-126">有关详细信息，请参阅[如何︰ 在 Visual Basic 中启用 XML IntelliSense](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md)。</span><span class="sxs-lookup"><span data-stu-id="59995-126">For more information, see[How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).</span></span>  
  
 <span data-ttu-id="59995-127">请注意，可能从多个用于具有相同的架构的 XML 文档推断不同的 XSD 架构集。</span><span class="sxs-lookup"><span data-stu-id="59995-127">Note that different XSD schema sets might be inferred from multiple XML documents that are intended to have the same schema.</span></span> <span data-ttu-id="59995-128">这可发生在一个 XML 文件中而不是在另一台，找到特定的元素和属性时也顺序不同，例如包含元素。</span><span class="sxs-lookup"><span data-stu-id="59995-128">This can occur when particular elements and attributes are found in one XML file and not in another, or when elements are included in different order, for example.</span></span> <span data-ttu-id="59995-129">使用 XSD 架构推断时，应检查推断的 XSD 架构集的完整性和精确性。</span><span class="sxs-lookup"><span data-stu-id="59995-129">You should review inferred XSD schema sets for completeness and accuracy when you use XSD schema inference.</span></span>  
  
## <a name="member-list"></a><span data-ttu-id="59995-130">成员列表</span><span class="sxs-lookup"><span data-stu-id="59995-130">Member List</span></span>  
 <span data-ttu-id="59995-131">键入句点 （.） 来分隔的一个实例后<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XDocument>对象 (或实例`IEnumerable(Of XElement)`或`IEnumerable(Of XDocument)`)，Visual Basic IntelliSense 将显示可能的对象成员的列表。</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="59995-131">After you type a period (.) to delimit an instance of an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object (or an instance of `IEnumerable(Of XElement)` or `IEnumerable(Of XDocument)`), Visual Basic IntelliSense displays a list of possible object members.</span></span> <span data-ttu-id="59995-132">初始列表中包括三个选项，表示 XML 轴属性，如下面的列表中所述。</span><span class="sxs-lookup"><span data-stu-id="59995-132">The initial list includes three options that represent XML axis properties, as described in the following list.</span></span>  
  
|<span data-ttu-id="59995-133">选项</span><span class="sxs-lookup"><span data-stu-id="59995-133">Option</span></span>|<span data-ttu-id="59995-134">说明</span><span class="sxs-lookup"><span data-stu-id="59995-134">Description</span></span>|  
|---|---|  
|**\< >**|<span data-ttu-id="59995-135">选择此选项以显示可能的子列表元素。</span><span class="sxs-lookup"><span data-stu-id="59995-135">Select this option to show a list of possible child elements.</span></span> <span data-ttu-id="59995-136">有关详细信息，请参阅[XML 元素文本](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)和<xref:System.Xml.Linq.XContainer.Elements%2A>方法。</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="59995-136">For more information, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) and the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>|  
|**@**|<span data-ttu-id="59995-137">选择此选项以显示可能的属性的列表。</span><span class="sxs-lookup"><span data-stu-id="59995-137">Select this option to show a list of possible attributes.</span></span> <span data-ttu-id="59995-138">有关详细信息，请参阅[XML 轴属性](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)。此选项才可用仅适用于对象类型<xref:System.Xml.Linq.XElement>。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="59995-138">For more information, see [XML Axis Properties](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).This option is available only for objects of type <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="59995-139">**…\< >**</span><span class="sxs-lookup"><span data-stu-id="59995-139">**…\< >**</span></span>|<span data-ttu-id="59995-140">选择此选项以显示可能的子代元素的列表。</span><span class="sxs-lookup"><span data-stu-id="59995-140">Select this option to show a list of possible descendant elements.</span></span> <span data-ttu-id="59995-141">有关详细信息，请参阅[如何︰ 访问 XML 后代元素](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)和<xref:System.Xml.Linq.XContainer.Elements%2A>方法。</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="59995-141">For more information, see [How to: Access XML Descendant Elements](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md) and the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>|  
  
 <span data-ttu-id="59995-142">选择或开始键入任何从列表中的 XML 选项。</span><span class="sxs-lookup"><span data-stu-id="59995-142">Select or begin typing any of the XML options from the list.</span></span> <span data-ttu-id="59995-143">成员列表中将显示从 XML 架构中特定于所选的选项的潜在成员。</span><span class="sxs-lookup"><span data-stu-id="59995-143">The member list will then display potential members from the XML schema that are specific to the selected option.</span></span> <span data-ttu-id="59995-144">如果您有 XML 命名空间导入与特定的 XML 命名空间前缀相关联，在成员列表中包含的潜在的 XML 命名空间前缀列表。</span><span class="sxs-lookup"><span data-stu-id="59995-144">If you have XML namespaces imported that are associated with a specific XML namespace prefix, a list of potential XML namespace prefixes is included in the member list.</span></span>  
  
 <span data-ttu-id="59995-145">例如，考虑下面的 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="59995-145">For example, consider the following XSD schema.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema attributeFormDefault="unqualified"   
           elementFormDefault="qualified"   
           targetNamespace="http://SamplePurchaseOrder"   
           xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="PurchaseOrders">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="PurchaseOrder">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="Address" />  
              <xs:element name="Items" />  
              <xs:element name="Comment" />  
            </xs:sequence>  
            <xs:attribute name="PurchaseOrderNumber" type="xs:unsignedShort" use="required" />  
            <xs:attribute name="OrderDate" type="xs:string" use="required" />  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="59995-146">有效的 XSD 架构的 XML 将如下所示。</span><span class="sxs-lookup"><span data-stu-id="59995-146">Valid XML for the XSD schema would resemble the following.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<PurchaseOrders xmlns="http://SamplePurchaseOrder">  
  <PurchaseOrder PurchaseOrderNumber="12345" OrderDate="2000-1-1">  
    <Address />  
    <Items />  
    <Comment />  
  </PurchaseOrder>  
</PurchaseOrders>  
```  
  
 <span data-ttu-id="59995-147">如果您在项目中包括此 XSD 架构文件并将从 XSD 架构的目标命名空间导入您的代码文件或项目，Visual Basic IntelliSense 将显示架构中的成员，键入您的 Visual Basic 代码。</span><span class="sxs-lookup"><span data-stu-id="59995-147">If you include this XSD schema file in a project and import the target namespace from the XSD schema into your code file or project, Visual Basic IntelliSense displays members from the schema as you type your Visual Basic code.</span></span> <span data-ttu-id="59995-148">如果您键入以下 XSD 架构的目标命名空间将作为默认命名空间导入，IntelliSense 将显示可能的子元素的列表`PurchaseOrder`XML 元素。</span><span class="sxs-lookup"><span data-stu-id="59995-148">If the target namespace for the XSD schema is imported as the default namespace and you type the following, IntelliSense displays a list of possible child elements for the `PurchaseOrder` XML element.</span></span>  
  
```  
Dim po = <PurchaseOrder />  
po.<  
```  
  
 <span data-ttu-id="59995-149">列表由地址、 注释和项元素组成。</span><span class="sxs-lookup"><span data-stu-id="59995-149">The list consists of the Address, Comment, and Items elements.</span></span>  
  
### <a name="certainty-levels-for-intellisense-list-items"></a><span data-ttu-id="59995-150">智能感知列表项的确定性级别</span><span class="sxs-lookup"><span data-stu-id="59995-150">Certainty Levels for IntelliSense List Items</span></span>  
 <span data-ttu-id="59995-151">确定要用于智能感知的 XSD 类型并不精确。</span><span class="sxs-lookup"><span data-stu-id="59995-151">Determining the XSD type to use for IntelliSense is not exact.</span></span> <span data-ttu-id="59995-152">因此，XML IntelliSense 通常将显示可能成员的扩展的列表。</span><span class="sxs-lookup"><span data-stu-id="59995-152">As a result, XML IntelliSense will often show an expanded list of possible members.</span></span> <span data-ttu-id="59995-153">若要帮助您从 IntelliSense 成员列表中选择一项，项将显示相对值的指示的 XML IntelliSense 的特定成员具有的确定性级别。</span><span class="sxs-lookup"><span data-stu-id="59995-153">To aid you in selecting an item from the IntelliSense member list, items are displayed with an indication of the level of certainty that XML IntelliSense has for a particular member.</span></span>  
  
 <span data-ttu-id="59995-154">有时 XML IntelliSense 可以识别的 XSD 架构中特定类型。</span><span class="sxs-lookup"><span data-stu-id="59995-154">Sometimes XML IntelliSense can identify a specific type from the XSD schema.</span></span> <span data-ttu-id="59995-155">在这些情况下，它将具有高确定性级别中显示可能的子元素、 属性或该 XSD 类型的子代元素。</span><span class="sxs-lookup"><span data-stu-id="59995-155">In these cases, it will display possible child elements, attributes, or descendant elements for that XSD type with a high degree of certainty.</span></span> <span data-ttu-id="59995-156">带有复选标记，这些项进行标识。</span><span class="sxs-lookup"><span data-stu-id="59995-156">These items are identified with a check mark.</span></span>  
  
 <span data-ttu-id="59995-157">但是，有时 XML IntelliSense 不能用于标识特定类型的 XSD 架构中。</span><span class="sxs-lookup"><span data-stu-id="59995-157">However, sometimes XML IntelliSense is not able to identify a specific type from the XSD schema.</span></span> <span data-ttu-id="59995-158">在这些情况下，它将与低确定性级别显示可能的子元素、 属性或项目的 XSD 架构中的子代元素的扩展的的列表。</span><span class="sxs-lookup"><span data-stu-id="59995-158">In these cases, it will display an expanded list of possible child elements, attributes, or descendant elements from the XSD schema for the project with a low degree of certainty.</span></span> <span data-ttu-id="59995-159">使用问号来标识这些项。</span><span class="sxs-lookup"><span data-stu-id="59995-159">These items are identified with a question mark.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59995-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59995-160">See Also</span></span>  
 <span data-ttu-id="59995-161">[如何︰ 启用在 Visual Basic 中的 XML IntelliSense](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md) </span><span class="sxs-lookup"><span data-stu-id="59995-161">[How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md) </span></span>  
<span data-ttu-id="59995-162"> [XML 到架构向导](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="59995-162"> [XML to Schema Wizard](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md) </span></span>  
<span data-ttu-id="59995-163"> [Imports 语句 (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="59995-163"> [Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span></span>  
<span data-ttu-id="59995-164"> [XML 元素文本](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="59995-164"> [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="59995-165"> [XML 特性轴属性](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md) </span><span class="sxs-lookup"><span data-stu-id="59995-165"> [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md) </span></span>  
<span data-ttu-id="59995-166"> [XML 子代轴属性](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md) </span><span class="sxs-lookup"><span data-stu-id="59995-166"> [XML Descendant Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md) </span></span>  
<span data-ttu-id="59995-167"> [项目设计器 ->“引用”页 (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="59995-167"> [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span></span>
