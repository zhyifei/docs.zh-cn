---
title: '&lt;wsdlImporters&gt;'
ms.date: 03/30/2017
ms.assetid: 270c7f93-eab7-47b6-8b94-ac3f5b7f17e4
ms.openlocfilehash: 338d6fb9364847b13a8f1abe5671c508df99c255
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32767435"
---
# <a name="ltwsdlimportersgt"></a><span data-ttu-id="1b44f-102">&lt;wsdlImporters&gt;</span><span class="sxs-lookup"><span data-stu-id="1b44f-102">&lt;wsdlImporters&gt;</span></span>
<span data-ttu-id="1b44f-103">此配置元素指定可导入带有 WS-Policy 附件的 Web 服务描述语言 (WSDL) 1.1 元数据的所有 WSDL 导入程序。</span><span class="sxs-lookup"><span data-stu-id="1b44f-103">This configuration element specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="1b44f-104">每个子元素就是一个 <`wsdlImporter`>，可指定导入元数据以及将该信息转换为各种表示协定和终结点信息的类的方法。</span><span class="sxs-lookup"><span data-stu-id="1b44f-104">Each child element is a <`wsdlImporter`> that specifies the way to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="1b44f-105">它可以有选择地导入协定和终结点信息以及公开任何导入错误的属性，并接受与导入和转换过程相关的类型信息。</span><span class="sxs-lookup"><span data-stu-id="1b44f-105">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="1b44f-106">它还支持导入某些绑定信息和属性，这些信息和属性提供了对任何策略文档、WSDL 文档、WSDL 扩展和 XML 架构文档的访问。</span><span class="sxs-lookup"><span data-stu-id="1b44f-106">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b44f-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b44f-107">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 <xref:System.ServiceModel.Description.WsdlImporter>  
 [<span data-ttu-id="1b44f-108">WCF 客户端配置</span><span class="sxs-lookup"><span data-stu-id="1b44f-108">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="1b44f-109">客户端</span><span class="sxs-lookup"><span data-stu-id="1b44f-109">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
