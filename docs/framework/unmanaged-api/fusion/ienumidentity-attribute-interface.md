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
ms.openlocfilehash: dbb3ac150ebfe9fe3698427d8bb2bfb3e3347c07
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796468"
---
# <a name="ienumidentity_attribute-interface"></a>IEnumIDENTITY_ATTRIBUTE 接口
用作当前范围中代码对象的特性的枚举数。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|获取一个接口指针，该指针`IEnumIDENTITY_ATTRIBUTE`指向包含与此`IEnumIDENTITY_ATTRIBUTE`相同的成员的新。|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|将此`IEnumIDENTITY_ATTRIBUTE`中包含的数据写入指定的数据缓冲区。|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|从当前位置开始，获取指定数目的属性。|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|将指令指针移到此`IEnumIDENTITY_ATTRIBUTE`的开头。|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|从当前位置开始，将指令指针向前移动指定数量的元素。|  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** 隔离。h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [合成接口](fusion-interfaces.md)
