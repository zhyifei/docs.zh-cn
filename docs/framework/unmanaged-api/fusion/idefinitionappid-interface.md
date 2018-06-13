---
title: IDefinitionAppId 接口
ms.date: 03/30/2017
api_name:
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2735355097a1f3f581b3a4bc74f08d8f2ebf3bd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430375"
---
# <a name="idefinitionappid-interface"></a>IDefinitionAppId 接口
表示在当前范围内定义应用程序的代码的唯一标识符。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|获取表示在此代码的格式化的字符串`IDefinitionAppId`对象。|  
|`IDefinitionAppId::put_Codebase`|设置此代码`IDefinitionAppId`到指定的对象设置格式的字符串值。|  
|`IDefinitionAppId::EnumAppPath`|获取到的接口指针[IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md)对象，其中包含当前的应用程序路径中的程序集。|  
|`IDefinitionAppId::SetAppPath`|为程序集的应用程序路径设置到由指定引用的值的当前作用域中[IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)对象。|  
|`IDefinitionAppId::get_SubscriptionId`|获取一个指针指向的字符串表示形式的令牌标识符对此订阅`IDefinitionAppId`对象。|  
|`IDefinitionAppId::put_SubscriptionId`|设置与此订阅的令牌标识符`IDefinitionAppId`到指定的字符串值的对象。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Isolation.h  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [合成接口](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
