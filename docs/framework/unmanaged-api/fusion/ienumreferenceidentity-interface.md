---
title: IEnumReferenceIdentity 接口
ms.date: 03/30/2017
api_name:
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c5d4bc1fa82f7623168050f4ee36f0ea3cd171e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796442"
---
# <a name="ienumreferenceidentity-interface"></a>IEnumReferenceIdentity 接口
用作对象集合的`IReferenceIdentity`枚举器。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|获取一个接口指针，该指针`IEnumReferenceIdentity`指向包含与此`IEnumReferenceIdentity`相同的成员的新。|  
|`IEnumReferenceIdentity::Next`|从当前位置开始，获取`IReferenceIdentity`指定数目的对象。|  
|`IEnumReferenceIdentity::Reset`|将指令指针移到此`IEnumReferenceIdentity`的开头。|  
|`IEnumReferenceIdentity::Skip`|从当前位置开始，将指令指针向前移动指定数量的元素。|  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** 隔离。h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [合成接口](fusion-interfaces.md)
- [IReferenceIdentity 接口](ireferenceidentity-interface.md)
