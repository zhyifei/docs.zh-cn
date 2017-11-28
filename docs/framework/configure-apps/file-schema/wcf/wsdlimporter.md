---
title: '&lt;wsdlImporter&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c3b3eaa4e4a229000bb0e2412adee541f4d59484
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltwsdlimportergt"></a>&lt;wsdlImporter&gt;
指定可导入带有 WS-Policy 附件的 Web 服务描述语言 (WSDL) 1.1 元数据的所有 WSDL 导入程序。  
  
\<系统。ServiceModel >  
\<客户端 >  
\<元数据 >  
\<wsdlImporters >  
\<wsdlImporter >  
  
## <a name="syntax"></a>语法  
  
```xml  
<metadata>  
  <wsdlImporters>  
    <wsdlImporter type="string" />  
  </wsdlImporters>  
</metadata>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`type`|此元素的类型。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<wsdlImporters >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|指定可导入带有 WS-Policy 附件的 Web 服务描述语言 (WSDL) 1.1 元数据的所有 WSDL 导入程序。|  
  
## <a name="remarks"></a>备注  
 WSDL 导入程序可用于导入元数据并将这些信息转换为各种表示协定和终结点信息的类。 它可以有选择地导入协定和终结点信息以及公开任何导入错误的属性，并接受与导入和转换过程相关的类型信息。 它还支持导入某些绑定信息和属性，这些信息和属性提供了对任何策略文档、WSDL 文档、WSDL 扩展和 XML 架构文档的访问。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Configuration.WsdlImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 <xref:System.ServiceModel.Description.WsdlImporter>  
 [WCF 客户端配置](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [客户端](../../../../../docs/framework/wcf/feature-details/clients.md)
