---
title: '&lt;添加&gt;元素&lt;schemaImporterExtensions&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 48deb8684e53f583e3ff4a5407fadd112d45f749
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44196824"
---
# <a name="ltaddgt-element-for-ltschemaimporterextensionsgt"></a><span data-ttu-id="9d8dc-102">&lt;添加&gt;元素&lt;schemaImporterExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="9d8dc-102">&lt;add&gt; Element for &lt;schemaImporterExtensions&gt;</span></span>
<span data-ttu-id="9d8dc-103">添加将 XSD 类型映射到 .NET Framework 类型时 <xref:System.Xml.Serialization.XmlSchemaImporter> 所用的类型。</span><span class="sxs-lookup"><span data-stu-id="9d8dc-103">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET Framework types.</span></span> <span data-ttu-id="9d8dc-104">有关配置文件的详细信息，请参阅[配置文件架构](../../../docs/framework/configure-apps/file-schema/index.md)。</span><span class="sxs-lookup"><span data-stu-id="9d8dc-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="9d8dc-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9d8dc-105">\<configuration></span></span>  
<span data-ttu-id="9d8dc-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="9d8dc-106">\<system.xml.serialization></span></span>  
<span data-ttu-id="9d8dc-107">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="9d8dc-107">\<schemaImporterExtensions></span></span>  
<span data-ttu-id="9d8dc-108">\<add></span><span class="sxs-lookup"><span data-stu-id="9d8dc-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d8dc-109">语法</span><span class="sxs-lookup"><span data-stu-id="9d8dc-109">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d8dc-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9d8dc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9d8dc-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9d8dc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d8dc-112">特性</span><span class="sxs-lookup"><span data-stu-id="9d8dc-112">Attributes</span></span>  
  
|<span data-ttu-id="9d8dc-113">特性</span><span class="sxs-lookup"><span data-stu-id="9d8dc-113">Attribute</span></span>|<span data-ttu-id="9d8dc-114">描述</span><span class="sxs-lookup"><span data-stu-id="9d8dc-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d8dc-115">**name**</span><span class="sxs-lookup"><span data-stu-id="9d8dc-115">**name**</span></span>|<span data-ttu-id="9d8dc-116">用于查找实例的简单名称。</span><span class="sxs-lookup"><span data-stu-id="9d8dc-116">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="9d8dc-117">**type**</span><span class="sxs-lookup"><span data-stu-id="9d8dc-117">**type**</span></span>|<span data-ttu-id="9d8dc-118">必须的。</span><span class="sxs-lookup"><span data-stu-id="9d8dc-118">Required.</span></span> <span data-ttu-id="9d8dc-119">指定要添加的架构扩展类。</span><span class="sxs-lookup"><span data-stu-id="9d8dc-119">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="9d8dc-120">type 特性值必须位于一行上，并且包含完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="9d8dc-120">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="9d8dc-121">当程序集放置在全局程序集缓存 (GAC) 中时，该特性值还必须包括已签名程序集的版本、区域性和公钥标记。</span><span class="sxs-lookup"><span data-stu-id="9d8dc-121">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d8dc-122">子元素</span><span class="sxs-lookup"><span data-stu-id="9d8dc-122">Child Elements</span></span>  
 <span data-ttu-id="9d8dc-123">无。</span><span class="sxs-lookup"><span data-stu-id="9d8dc-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9d8dc-124">父元素</span><span class="sxs-lookup"><span data-stu-id="9d8dc-124">Parent Elements</span></span>  
  
|<span data-ttu-id="9d8dc-125">元素</span><span class="sxs-lookup"><span data-stu-id="9d8dc-125">Element</span></span>|<span data-ttu-id="9d8dc-126">描述</span><span class="sxs-lookup"><span data-stu-id="9d8dc-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9d8dc-127">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="9d8dc-127">\<schemaImporterExtensions></span></span>|<span data-ttu-id="9d8dc-128">包含 <xref:System.Xml.Serialization.XmlSchemaImporter> 所使用的类型。</span><span class="sxs-lookup"><span data-stu-id="9d8dc-128">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9d8dc-129">示例</span><span class="sxs-lookup"><span data-stu-id="9d8dc-129">Example</span></span>  
 <span data-ttu-id="9d8dc-130">下面的代码示例添加 XmlSchemaImporter 可以在映射类型时使用的扩展类型。</span><span class="sxs-lookup"><span data-stu-id="9d8dc-130">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <schemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,   
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,   
       PublicKeyToken=b03f5f7f11d50a3a" />   
    </schemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d8dc-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d8dc-131">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>  
- [<span data-ttu-id="9d8dc-132">\<system.xml.serialization> 元素</span><span class="sxs-lookup"><span data-stu-id="9d8dc-132">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)  
- [<span data-ttu-id="9d8dc-133">\<schemaImporterExtensions> 元素</span><span class="sxs-lookup"><span data-stu-id="9d8dc-133">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
