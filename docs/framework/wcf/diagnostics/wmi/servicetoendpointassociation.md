---
title: ServiceToEndpointAssociation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f576c2f82590f683aa51d5cc70c67a4a2b15a1e0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="servicetoendpointassociation"></a>ServiceToEndpointAssociation
将服务映射到终结点。  
  
## <a name="syntax"></a>语法  
  
```  
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a>方法  
 ServiceToEndpointAssociation 类不定义任何方法。  
  
## <a name="properties"></a>属性  
 ServiceToEndpointAssociation 类有以下属性：  
  
### <a name="ref"></a>ref  
 数据类型：Service  
  
 访问类型：只读  
限定符：键  
  
 与终结点关联的服务。  
  
### <a name="ref"></a>ref  
 数据类型：Endpoint  
  
 访问类型：只读  
限定符：键  
  
 与服务关联的终结点。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|
