---
title: IReferenceAppId 接口
ms.date: 03/30/2017
api_name:
- IReferenceAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceAppId
helpviewer_keywords:
- IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 522ed80f161f114af25e1fa7ad041c8238073d6f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796366"
---
# <a name="ireferenceappid-interface"></a>IReferenceAppId 接口
表示对当前范围内的应用程序的唯一标识符的引用。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|获取一个指针，该指针指向由此`IReferenceAppId`引用的应用程序的代码标识符的字符串表示形式。|  
|`IReferenceAppId::put_CodeBase`|设置由此`IReferenceAppId`引用的应用程序的代码标识符。|  
|`IReferenceAppId::EnumAppPath`|获取一个接口指针，该`IEnumReferenceIdentity`指针指向一个`IReferenceIdentity`实例，该实例包含表示`IReferenceAppId`此的成员的实例。|  
|`IReferenceAppId::get_SubscriptionId`|获取一个指针，该指针指向此`IReferenceAppId`的订阅的标记标识符的字符串表示形式。|  
|`IReferenceAppId::put_SubscriptionId`|将此`IReferenceAppId`订阅的标记标识符设置为指定的字符串值。|  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** 隔离。h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [合成接口](fusion-interfaces.md)
- [IEnumReferenceIdentity 接口](ienumreferenceidentity-interface.md)
- [IReferenceIdentity 接口](ireferenceidentity-interface.md)
