---
title: "IEnumReferenceIdentity 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IEnumReferenceIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IEnumReferenceIdentity
helpviewer_keywords: IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 49e1425e8e7e3d09dc36915916b887d2887dccff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ienumreferenceidentity-interface"></a>IEnumReferenceIdentity 接口
用作的集合的枚举数`IReferenceIdentity`对象。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|到新获取的接口指针`IEnumReferenceIdentity`，其中包含与此相同的成员`IEnumReferenceIdentity`。|  
|`IEnumReferenceIdentity::Next`|获取指定的数目的`IReferenceIdentity`对象，从当前位置开始。|  
|`IEnumReferenceIdentity::Reset`|将指令指针移到此开头`IEnumReferenceIdentity`。|  
|`IEnumReferenceIdentity::Skip`|将指令指针向前移动指定数量的元素，从当前位置开始。|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Isolation.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [合成接口](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [IReferenceIdentity 接口](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
