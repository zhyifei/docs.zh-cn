---
title: "IReferenceAppId 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IReferenceAppId
api_location: fusion.dll
api_type: COM
f1_keywords: IReferenceAppId
helpviewer_keywords: IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 22ac2d75632b3c670d7c185cbbf5081732dcaffc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ireferenceappid-interface"></a>IReferenceAppId 接口
表示当前范围中的应用程序的唯一标识符的引用。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|获取一个指向的字符串表示形式的代码标识符的应用程序引用此`IReferenceAppId`。|  
|`IReferenceAppId::put_CodeBase`|设置此引用的应用程序的代码标识符`IReferenceAppId`。|  
|`IReferenceAppId::EnumAppPath`|获取到的接口指针`IEnumReferenceIdentity`实例包含`IReferenceIdentity`表示此成员的实例`IReferenceAppId`。|  
|`IReferenceAppId::get_SubscriptionId`|获取一个指针指向的字符串表示形式的令牌标识符对此订阅`IReferenceAppId`。|  
|`IReferenceAppId::put_SubscriptionId`|设置与此订阅的令牌标识符`IReferenceAppId`到指定的字符串值。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Isolation.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [合成接口](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [IEnumReferenceIdentity 接口](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 [IReferenceIdentity 接口](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
