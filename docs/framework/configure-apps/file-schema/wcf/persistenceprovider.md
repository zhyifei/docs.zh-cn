---
title: '&lt;persistenceProvider&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2d93a9ea8614f98c968d499c2f95dcd3962f0020
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltpersistenceprovidergt"></a>&lt;persistenceProvider&gt;
指定要使用的持久性提供程序实现的类型以及用于持久性操作的超时值。  
  
 \<系统。ServiceModel >  
\<行为 >  
\<serviceBehaviors >  
\<行为 >  
\<persistenceProvider >  
  
## <a name="syntax"></a>语法  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"  
   type="String" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|persistenceOperationTimeout|一个 <xref:System.TimeSpan> 值，指定用于持久性操作的超时值。 默认值为"00: 00:30"。|  
|类型|一个字符串，指定要使用的永久性提供程序工厂的类型。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<行为 >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|指定行为元素。|  
  
## <a name="remarks"></a>备注  
 此元素指定要用于序列化 WCF 服务的状态的永久性提供程序。 它应该与 `wsHttpContextBinding` 一起使用，后者在 HTTP 头中传递状态信息。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Configuration.PersistenceProviderElement>  
 <xref:System.ServiceModel.Persistence.PersistenceProvider>
