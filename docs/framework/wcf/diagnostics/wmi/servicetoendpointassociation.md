---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 3d23a3ee10c47e04ea7bdba202ea5063c0d84fac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62048226"
---
# <a name="servicetoendpointassociation"></a>ServiceToEndpointAssociation
将服务映射到终结点。  
  
## <a name="syntax"></a>语法  
  
```csharp
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
 数据类型：服务  
  
 访问类型：只读  
限定符：键  
  
 与终结点关联的服务。  
  
### <a name="ref"></a>ref  
 数据类型：终结点  
  
 访问类型：只读  
限定符：键  
  
 与服务关联的终结点。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|
