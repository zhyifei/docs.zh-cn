---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 05be495dbfe87e7dd14b0cfbb38b30c6f8278e6d
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192234"
---
# <a name="serviceappdomain"></a>ServiceAppDomain
将服务映射到应用程序域。  
  
## <a name="syntax"></a>语法  
  
```csharp
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
