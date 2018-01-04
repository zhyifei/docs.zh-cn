---
title: ServiceAppDomain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5d948d1c77fc3f188694062ca9dcb3058f408c45
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="serviceappdomain"></a>ServiceAppDomain
将服务映射到应用程序域。  
  
## <a name="syntax"></a>语法  
  
```  
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a>方法  
 ServiceAppDomain 类不定义任何方法。  
  
## <a name="properties"></a>属性  
 ServiceAppDomain 类具有以下属性：  
  
### <a name="ref"></a>ref  
 数据类型：Service  
限定符：键  
  
 访问类型：只读  
  
 此应用程序域的服务。  
  
### <a name="ref"></a>ref  
 数据类型：AppDomainInfo  
限定符：键  
  
 访问类型：只读  
  
 包含应用程序域的属性。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|
