---
title: 将 XML 数据类型映射到 CLR 类型
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: cabdfcad-f359-479b-b71c-8b2fad42ca49
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9cff30147da82896fb3a757ba2fed16d794ec3c9
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46004044"
---
# <a name="mapping-xml-data-types-to-clr-types"></a><span data-ttu-id="c2009-102">将 XML 数据类型映射到 CLR 类型</span><span class="sxs-lookup"><span data-stu-id="c2009-102">Mapping XML Data Types to CLR Types</span></span>
<span data-ttu-id="c2009-103">下表介绍 XML 数据类型与公共语言运行库 (CLR) 类型之间的默认映射。</span><span class="sxs-lookup"><span data-stu-id="c2009-103">The following table describes the default mapping between the XML data types and the common language runtime (CLR) types.</span></span>  
  
## <a name="the-following-table-describes-the-default-mappings-of-an-xml-data-type-to-a-clr-type"></a><span data-ttu-id="c2009-104">下表介绍 XML 数据类型与 CLR 类型的默认映射。</span><span class="sxs-lookup"><span data-stu-id="c2009-104">The following table describes the default mappings of an XML data type to a CLR type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2009-105">`xs` 和 `xdt` 前缀分别映射到 http://www.w3.org/2001/XMLSchema 和 http://www.w3.org/2003/05/xpath-datatypes 命名空间 URI。</span><span class="sxs-lookup"><span data-stu-id="c2009-105">The `xs` and the `xdt` prefixes are mapped to the http://www.w3.org/2001/XMLSchema and the http://www.w3.org/2003/05/xpath-datatypes namespace URIs respectively.</span></span>  
  
|<span data-ttu-id="c2009-106">XML 类型</span><span class="sxs-lookup"><span data-stu-id="c2009-106">XML Type</span></span>|<span data-ttu-id="c2009-107">CLR 类型</span><span class="sxs-lookup"><span data-stu-id="c2009-107">CLR Type</span></span>|  
|--------------|--------------|  
|`xs:anyURI`|<xref:System.Uri>|  
|`xs:base64Binary`|`Byte[]`|  
|`xs:boolean`|<xref:System.Boolean>|  
|`xs:byte`|<xref:System.SByte>|  
|`xs:date`|<xref:System.DateTime>|  
|`xs:dateTime`|<xref:System.DateTime>|  
|`xs:decimal`|<xref:System.Decimal>|  
|`xs:double`|<xref:System.Double>|  
|`xs:duration`|<xref:System.TimeSpan>|  
|`xs:ENTITIES`|`String[]`|  
|`xs:ENTITY`|<xref:System.String>|  
|`xs:float`|<xref:System.Single>|  
|`xs:gDay`|<xref:System.DateTime>|  
|`xs:gMonthDay`|<xref:System.DateTime>|  
|`xs:gYear`|<xref:System.DateTime>|  
|`xs:gYearMonth`|<xref:System.DateTime>|  
|`xs:hexBinary`|`Byte[]`|  
|`xs:ID`|<xref:System.String>|  
|`xs:IDREF`|<xref:System.String>|  
|`xs:IDREFS`|`String[]`|  
|`xs:int`|<xref:System.Int32>|  
|`xs:integer`|<xref:System.Decimal>|  
|`xs:language`|<xref:System.String>|  
|`xs:long`|<xref:System.Int64>|  
|`xs:gMmonth`|<xref:System.DateTime>|  
|`xs:Name`|<xref:System.String>|  
|`xs:NCName`|<xref:System.String>|  
|`xs:negativeInteger`|<xref:System.Decimal>|  
|`xs:NMTOKEN`|<xref:System.String>|  
|`xs:NMTOKENS`|`String[]`|  
|`xs:nonNegativeInteger`|<xref:System.Decimal>|  
|`xs:nonPositiveInteger`|<xref:System.Decimal>|  
|`xs:normalizedString`|<xref:System.String>|  
|`xs:NOTATION`|<xref:System.Xml.XmlQualifiedName>|  
|`xs:positiveInteger`|<xref:System.Decimal>|  
|`xs:QName`|<xref:System.Xml.XmlQualifiedName>|  
|`xs:short`|<xref:System.Int16>|  
|`xs:string`|<xref:System.String>|  
|`xs:time`|<xref:System.DateTime>|  
|`xs:token`|<xref:System.String>|  
|`xs:unsignedByte`|<xref:System.Byte>|  
|`xs:unsignedInt`|<xref:System.UInt32>|  
|`xs:unsignedLong`|<xref:System.UInt64>|  
|`xs:unsignedShort`|<xref:System.UInt16>|  
|`xdt:dayTimeDuration`|<xref:System.TimeSpan>|  
|`xdt:yearMonthDuration`|<xref:System.TimeSpan>|  
|`xdt:untypedAtomic`|<xref:System.String>|  
|`xdt:anyAtomicType`|<xref:System.Object>|  
|`xs:anySimpleType`|<xref:System.String>|  
|<span data-ttu-id="c2009-108">文档节点</span><span class="sxs-lookup"><span data-stu-id="c2009-108">Document node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="c2009-109">Element 节点</span><span class="sxs-lookup"><span data-stu-id="c2009-109">Element node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="c2009-110">Attribute 节点</span><span class="sxs-lookup"><span data-stu-id="c2009-110">Attribute node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="c2009-111">Namespace 节点</span><span class="sxs-lookup"><span data-stu-id="c2009-111">Namespace node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="c2009-112">Text 节点</span><span class="sxs-lookup"><span data-stu-id="c2009-112">Text node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="c2009-113">Comment 节点</span><span class="sxs-lookup"><span data-stu-id="c2009-113">Comment node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="c2009-114">Processing Instruction 节点</span><span class="sxs-lookup"><span data-stu-id="c2009-114">Processing instruction node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
  
## <a name="see-also"></a><span data-ttu-id="c2009-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2009-115">See also</span></span>

- [<span data-ttu-id="c2009-116">System.Xml 类中的类型支持</span><span class="sxs-lookup"><span data-stu-id="c2009-116">Type Support in the System.Xml Classes</span></span>](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)
