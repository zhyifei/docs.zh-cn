---
title: 包含或导入 XML 架构
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: fe1b4a11-37f4-4e1a-93c9-239f4fe736c0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c2f83128f47a687e75a7db9bb36c487fa1f5bb6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573058"
---
# <a name="including-or-importing-xml-schemas"></a><span data-ttu-id="cdfca-102">包含或导入 XML 架构</span><span class="sxs-lookup"><span data-stu-id="cdfca-102">Including or Importing XML Schemas</span></span>
<span data-ttu-id="cdfca-103">XML 架构可以包含 `<xs:import />`、`<xs:include />` 和 `<xs:redefine />` 元素。</span><span class="sxs-lookup"><span data-stu-id="cdfca-103">An XML schema may contain `<xs:import />`, `<xs:include />`, and `<xs:redefine />` elements.</span></span> <span data-ttu-id="cdfca-104">这些架构元素引用其他 XML 架构，可以用于补充包括或导入这些架构的架构的结构。</span><span class="sxs-lookup"><span data-stu-id="cdfca-104">These schema elements refer to other XML schemas that can be used to supplement the structure of the schema that includes or imports them.</span></span> <span data-ttu-id="cdfca-105"><xref:System.Xml.Schema.XmlSchemaImport>、<xref:System.Xml.Schema.XmlSchemaInclude> 和 <xref:System.Xml.Schema.XmlSchemaRedefine> 类映射到架构对象模型 (SOM) API 中的这些元素。</span><span class="sxs-lookup"><span data-stu-id="cdfca-105">The <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> and <xref:System.Xml.Schema.XmlSchemaRedefine> classes, map to these elements in the Schema Object Model (SOM) API.</span></span>  
  
## <a name="including-or-importing-an-xml-schema"></a><span data-ttu-id="cdfca-106">包括或导入 XML 架构</span><span class="sxs-lookup"><span data-stu-id="cdfca-106">Including or Importing an XML Schema</span></span>  
 <span data-ttu-id="cdfca-107">下面的代码示例为[生成 XML 架构](../../../../docs/standard/data/xml/building-xml-schemas.md)主题中创建的客户架构补充了地址架构。</span><span class="sxs-lookup"><span data-stu-id="cdfca-107">The following code example supplements the customer schema created in the [Building XML Schemas](../../../../docs/standard/data/xml/building-xml-schemas.md) topic with the address schema.</span></span> <span data-ttu-id="cdfca-108">为客户架构补充地址架构后，可以在客户架构中使用地址类型。</span><span class="sxs-lookup"><span data-stu-id="cdfca-108">Supplementing the customer schema with the address schema makes address types available in the customer schema.</span></span>  
  
 <span data-ttu-id="cdfca-109">地址架构可以使用 `<xs:include />` 或 `<xs:import />` 元素加入，以原样使用地址架构的组件，也可以使用 `<xs:redefine />` 元素修改其任意组件，以适合客户架构的需要。</span><span class="sxs-lookup"><span data-stu-id="cdfca-109">The address schema can be incorporated using either `<xs:include />` or `<xs:import />` elements to use the components of the address schema as-is, or using an `<xs:redefine />` element to modify any of its components to suit the need of the customer schema.</span></span> <span data-ttu-id="cdfca-110">因为地址架构的 `targetNamespace` 与客户架构的不同，所以，将使用 `<xs:import />` 元素以及导入语义。</span><span class="sxs-lookup"><span data-stu-id="cdfca-110">Because the address schema has a `targetNamespace` that is different from that of the customer schema, the `<xs:import />` element and therefore import semantics is used.</span></span>  
  
 <span data-ttu-id="cdfca-111">代码示例通过下列步骤包括客户架构。</span><span class="sxs-lookup"><span data-stu-id="cdfca-111">The code example includes the address schema in the following steps.</span></span>  
  
1.  <span data-ttu-id="cdfca-112">将客户架构和地址架构添加到新的 <xref:System.Xml.Schema.XmlSchemaSet> 对象并进行编译。</span><span class="sxs-lookup"><span data-stu-id="cdfca-112">Adds the customer schema and the address schema to a new <xref:System.Xml.Schema.XmlSchemaSet> object and then compiles them.</span></span> <span data-ttu-id="cdfca-113">_在读取或编译架构时遇到的任何架构验证警告和错误由 <xref:System.Xml.Schema.ValidationEventHandler> 委托进行处理。</span><span class="sxs-lookup"><span data-stu-id="cdfca-113">Any schema validation warnings and errors encountered reading or compiling the schemas are handled by the <xref:System.Xml.Schema.ValidationEventHandler> delegate.</span></span>  
  
2.  <span data-ttu-id="cdfca-114">通过循环访问 <xref:System.Xml.Schema.XmlSchema> 属性，从 <xref:System.Xml.Schema.XmlSchemaSet> 中为客户架构和地址架构检索已编译的 <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> 对象。</span><span class="sxs-lookup"><span data-stu-id="cdfca-114">Retrieves the compiled <xref:System.Xml.Schema.XmlSchema> objects for both the customer and address schemas from the <xref:System.Xml.Schema.XmlSchemaSet> by iterating over the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property.</span></span> <span data-ttu-id="cdfca-115">因为架构已编译，所以，可以访问后架构编译信息集 (PSCI) 属性。</span><span class="sxs-lookup"><span data-stu-id="cdfca-115">Because the schemas are compiled, Post-Schema-Compilation-Infoset (PSCI) properties are accessible.</span></span>  
  
3.  <span data-ttu-id="cdfca-116">创建一个 <xref:System.Xml.Schema.XmlSchemaImport> 对象，将导入的 <xref:System.Xml.Schema.XmlSchemaImport.Namespace%2A> 属性设置为地址架构的命名空间，将导入的 <xref:System.Xml.Schema.XmlSchemaExternal.Schema%2A> 属性设置为地址架构的 <xref:System.Xml.Schema.XmlSchema> 对象，并将导入添加到客户架构的 <xref:System.Xml.Schema.XmlSchema.Includes%2A> 属性中。</span><span class="sxs-lookup"><span data-stu-id="cdfca-116">Creates an <xref:System.Xml.Schema.XmlSchemaImport> object, sets the <xref:System.Xml.Schema.XmlSchemaImport.Namespace%2A> property of the import to the namespace of the address schema, sets the <xref:System.Xml.Schema.XmlSchemaExternal.Schema%2A> property of the import to the <xref:System.Xml.Schema.XmlSchema> object of the address schema, and adds the import to the <xref:System.Xml.Schema.XmlSchema.Includes%2A> property of the customer schema.</span></span>  
  
4.  <span data-ttu-id="cdfca-117">使用 <xref:System.Xml.Schema.XmlSchema> 类的 <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> 和 <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> 方法重新处理并编译已修改的客户架构的 <xref:System.Xml.Schema.XmlSchemaSet> 对象并将其写入控制台。</span><span class="sxs-lookup"><span data-stu-id="cdfca-117">Reprocesses and compiles the modified <xref:System.Xml.Schema.XmlSchema> object of the customer schema using the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> and <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> methods of the <xref:System.Xml.Schema.XmlSchemaSet> class and writes it to the console.</span></span>  
  
5.  <span data-ttu-id="cdfca-118">最后，使用客户架构的 <xref:System.Xml.Schema.XmlSchema.Includes%2A> 方法递归式将导入到客户架构的所有架构写入控制台。</span><span class="sxs-lookup"><span data-stu-id="cdfca-118">Finally, recursively writes all of the schemas imported into the customer schema to the console using the <xref:System.Xml.Schema.XmlSchema.Includes%2A> property of the customer schema.</span></span> <span data-ttu-id="cdfca-119"><xref:System.Xml.Schema.XmlSchema.Includes%2A> 属性提供对所有添加到架构中的包括、导入或重新定义的访问。</span><span class="sxs-lookup"><span data-stu-id="cdfca-119">The <xref:System.Xml.Schema.XmlSchema.Includes%2A> property provides access to all the includes, imports, or redefines added to a schema.</span></span>  
  
 <span data-ttu-id="cdfca-120">以下是完整的代码示例以及写入控制台的客户架构和地址架构。</span><span class="sxs-lookup"><span data-stu-id="cdfca-120">The following is the complete code example and the customer and address schemas written to the console.</span></span>  
  
 [!code-cpp[XmlSchemaImportExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaImportExample/CPP/XmlSchemaImportExample.cpp#1)]
 [!code-csharp[XmlSchemaImportExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaImportExample/CS/XmlSchemaImportExample.cs#1)]
 [!code-vb[XmlSchemaImportExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaImportExample/VB/XmlSchemaImportExample.vb#1)]  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:import namespace="http://www.example.com/IPO" />  
  <xs:element name="Customer">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="FirstName" type="xs:string" />  
        <xs:element name="LastName" type="tns:LastNameType" />  
      </xs:sequence>  
      <xs:attribute name="CustomerId" type="xs:positiveInteger" use="required" /  
>  
    </xs:complexType>  
  </xs:element>  
  <xs:simpleType name="LastNameType">  
    <xs:restriction base="xs:string">  
      <xs:maxLength value="20" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
<schema targetNamespace="http://www.example.com/IPO" xmlns="http://www.w3.org/2001/XMLSchema" xmlns:ipo="http://www.example.com/IPO">  
  <annotation>  
    <documentation xml:lang="en">  
      Addresses for International Purchase order schema  
      Copyright 2000 Example.com. All rights reserved.  
    </documentation>  
  </annotation>  
  <complexType name="Address">  
    <sequence>  
      <element name="name"   type="string"/>  
      <element name="street" type="string"/>  
      <element name="city"   type="string"/>  
    </sequence>  
  </complexType>  
  <complexType name="USAddress">  
    <complexContent>  
      <extension base="ipo:Address">  
        <sequence>  
          <element name="state" type="ipo:USState"/>  
          <element name="zip"   type="positiveInteger"/>  
        </sequence>  
      </extension>  
    </complexContent>  
  </complexType>  
  <!-- other Address derivations for more countries or regions -->  
  <simpleType name="USState">  
    <restriction base="string">  
      <enumeration value="AK"/>  
      <enumeration value="AL"/>  
      <enumeration value="AR"/>  
      <!-- and so on ... -->  
    </restriction>  
  </simpleType>  
</schema>  
```  
  
 <span data-ttu-id="cdfca-121">若要详细了解 `<xs:import />`、`<xs:include />` 和 `<xs:redefine />` 元素以及 <xref:System.Xml.Schema.XmlSchemaImport>、<xref:System.Xml.Schema.XmlSchemaInclude> 和 <xref:System.Xml.Schema.XmlSchemaRedefine> 类，请参阅 [W3C XML 架构](https://www.w3.org/XML/Schema)和 <xref:System.Xml.Schema?displayProperty=nameWithType> 命名空间类参考文档。</span><span class="sxs-lookup"><span data-stu-id="cdfca-121">For more information about the `<xs:import />`, `<xs:include />`, and `<xs:redefine />` elements and the <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> and <xref:System.Xml.Schema.XmlSchemaRedefine> classes, see the [W3C XML Schema](https://www.w3.org/XML/Schema) and the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace class reference documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdfca-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="cdfca-122">See Also</span></span>  
 [<span data-ttu-id="cdfca-123">XML 架构对象模型概述</span><span class="sxs-lookup"><span data-stu-id="cdfca-123">XML Schema Object Model Overview</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)  
 [<span data-ttu-id="cdfca-124">读取和编写 XML 架构</span><span class="sxs-lookup"><span data-stu-id="cdfca-124">Reading and Writing XML Schemas</span></span>](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)  
 [<span data-ttu-id="cdfca-125">生成 XML 架构</span><span class="sxs-lookup"><span data-stu-id="cdfca-125">Building XML Schemas</span></span>](../../../../docs/standard/data/xml/building-xml-schemas.md)  
 [<span data-ttu-id="cdfca-126">遍历 XML 架构</span><span class="sxs-lookup"><span data-stu-id="cdfca-126">Traversing XML Schemas</span></span>](../../../../docs/standard/data/xml/traversing-xml-schemas.md)  
 [<span data-ttu-id="cdfca-127">编辑 XML 架构</span><span class="sxs-lookup"><span data-stu-id="cdfca-127">Editing XML Schemas</span></span>](../../../../docs/standard/data/xml/editing-xml-schemas.md)  
 [<span data-ttu-id="cdfca-128">用于编译架构的 XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="cdfca-128">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
