---
title: XmlDictionaryReaderQuotas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 980a7eacd095dc1b601d63f5a807f2e287c09885
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xmldictionaryreaderquotas"></a>XmlDictionaryReaderQuotas
XmlDictionaryReaderQuotas  
  
## <a name="syntax"></a>语法  
  
```  
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a>方法  
 XmlDictionaryReaderQuotas 类不定义任何方法。  
  
## <a name="properties"></a>属性  
 XmlDictionaryReaderQuotas 类具有以下属性：  
  
### <a name="maxarraylength"></a>MaxArrayLength  
 数据类型：sint32  
  
 访问类型：只读  
  
 允许的最大数组长度。  
  
### <a name="maxbytesperread"></a>MaxBytesPerRead  
 数据类型：sint32  
  
 访问类型：只读  
  
 允许为每次读取返回的最大字节数。  
  
### <a name="maxdepth"></a>MaxDepth  
 数据类型：sint32  
  
 访问类型：只读  
  
 每次读取的最大嵌套节点深度。  
  
### <a name="maxnametablecharcount"></a>MaxNameTableCharCount  
 数据类型：sint32  
  
 访问类型：只读  
  
 表名称中允许的最大字符数。  
  
### <a name="maxstringcontentlength"></a>MaxStringContentLength  
 数据类型：sint32  
  
 访问类型：只读  
  
 XML 元素内容中允许包含的最大字符数。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
