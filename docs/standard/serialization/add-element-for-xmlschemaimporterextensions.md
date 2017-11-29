---
title: "&lt;xmlSchemaImporterExtensions&gt; 的 &lt;add&gt; 元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <xmlSchemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 766d04dd792534f0da33116ed959d81ff376e026
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-element-for-ltxmlschemaimporterextensionsgt"></a><span data-ttu-id="29702-102">&lt;xmlSchemaImporterExtensions&gt; 的 &lt;add&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="29702-102">&lt;add&gt; Element for &lt;xmlSchemaImporterExtensions&gt;</span></span>
<span data-ttu-id="29702-103">添加将 XSD 类型映射到 .NET Framework 类型时 <xref:System.Xml.Serialization.XmlSchemaImporter> 所用的类型。</span><span class="sxs-lookup"><span data-stu-id="29702-103">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET Framework types.</span></span> <span data-ttu-id="29702-104">有关配置文件的详细信息，请参阅[配置文件架构](../../../docs/framework/configure-apps/file-schema/index.md)。</span><span class="sxs-lookup"><span data-stu-id="29702-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="29702-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="29702-105">\<configuration></span></span>  
<span data-ttu-id="29702-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="29702-106">\<system.xml.serialization></span></span>  
<span data-ttu-id="29702-107">\<XmlSchemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="29702-107">\<XmlSchemaImporterExtensions></span></span>  
<span data-ttu-id="29702-108">\<add></span><span class="sxs-lookup"><span data-stu-id="29702-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29702-109">语法</span><span class="sxs-lookup"><span data-stu-id="29702-109">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29702-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="29702-110">Attributes and Elements</span></span>  
 <span data-ttu-id="29702-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="29702-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29702-112">特性</span><span class="sxs-lookup"><span data-stu-id="29702-112">Attributes</span></span>  
  
|<span data-ttu-id="29702-113">特性</span><span class="sxs-lookup"><span data-stu-id="29702-113">Attribute</span></span>|<span data-ttu-id="29702-114">描述</span><span class="sxs-lookup"><span data-stu-id="29702-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="29702-115">**name**</span><span class="sxs-lookup"><span data-stu-id="29702-115">**name**</span></span>|<span data-ttu-id="29702-116">用于查找实例的简单名称。</span><span class="sxs-lookup"><span data-stu-id="29702-116">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="29702-117">**type**</span><span class="sxs-lookup"><span data-stu-id="29702-117">**type**</span></span>|<span data-ttu-id="29702-118">必需。</span><span class="sxs-lookup"><span data-stu-id="29702-118">Required.</span></span> <span data-ttu-id="29702-119">指定要添加的架构扩展类。</span><span class="sxs-lookup"><span data-stu-id="29702-119">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="29702-120">type 特性值必须位于一行上，并且包含完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="29702-120">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="29702-121">当程序集放置在全局程序集缓存 (GAC) 中时，该特性值还必须包括已签名程序集的版本、区域性和公钥标记。</span><span class="sxs-lookup"><span data-stu-id="29702-121">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29702-122">子元素</span><span class="sxs-lookup"><span data-stu-id="29702-122">Child Elements</span></span>  
 <span data-ttu-id="29702-123">无。</span><span class="sxs-lookup"><span data-stu-id="29702-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="29702-124">父元素</span><span class="sxs-lookup"><span data-stu-id="29702-124">Parent Elements</span></span>  
  
|<span data-ttu-id="29702-125">元素</span><span class="sxs-lookup"><span data-stu-id="29702-125">Element</span></span>|<span data-ttu-id="29702-126">描述</span><span class="sxs-lookup"><span data-stu-id="29702-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="29702-127">\<xmlSchemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="29702-127">\<xmlSchemaImporterExtensions></span></span>|<span data-ttu-id="29702-128">包含 <xref:System.Xml.Serialization.XmlSchemaImporter> 所使用的类型。</span><span class="sxs-lookup"><span data-stu-id="29702-128">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="29702-129">示例</span><span class="sxs-lookup"><span data-stu-id="29702-129">Example</span></span>  
 <span data-ttu-id="29702-130">下面的代码示例添加 XmlSchemaImporter 可以在映射类型时使用的扩展类型。</span><span class="sxs-lookup"><span data-stu-id="29702-130">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSchemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,   
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,   
       PublicKeyToken=b03f5f7f11d50a3a" />   
    </xmlSchemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="29702-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29702-131">See Also</span></span>  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 [<span data-ttu-id="29702-132">\<system.xml.serialization> 元素</span><span class="sxs-lookup"><span data-stu-id="29702-132">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)  
 [<span data-ttu-id="29702-133">\<schemaImporterExtensions> 元素</span><span class="sxs-lookup"><span data-stu-id="29702-133">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
