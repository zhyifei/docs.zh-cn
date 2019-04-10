---
title: IEnumIDENTITY_ATTRIBUTE 接口
ms.date: 03/30/2017
api_name:
- IEnumIDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords:
- IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d725228f2a7359d415673fdcb90d0cabae1a40be
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175521"
---
# <a name="ienumidentityattribute-interface"></a>IEnumIDENTITY_ATTRIBUTE 接口
用作当前作用域中的代码对象的属性的枚举器。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|为新获取的接口指针`IEnumIDENTITY_ATTRIBUTE`，其中包含与此相同的成员`IEnumIDENTITY_ATTRIBUTE`。|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|此元素中包含的数据写入`IEnumIDENTITY_ATTRIBUTE`到指定的数据缓冲区。|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|获取指定的数目的属性，从当前位置开始。|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|将指令指针移到开头`IEnumIDENTITY_ATTRIBUTE`。|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|按指定数量的元素，从当前位置开始移动指令指针前进。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Isolation.h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [合成接口](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
