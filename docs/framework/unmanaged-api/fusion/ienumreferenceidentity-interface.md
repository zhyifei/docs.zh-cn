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
ms.openlocfilehash: 1305b9ebe3cd87ba002ee87610ff309d015a44e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131751"
---
# <a name="ienumreferenceidentity-interface"></a>IEnumReferenceIdentity 接口
用作 `IReferenceIdentity` 对象的集合的枚举器。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|获取一个接口指针，该指针指向与此 `IEnumReferenceIdentity`包含相同成员的新 `IEnumReferenceIdentity`。|  
|`IEnumReferenceIdentity::Next`|从当前位置开始，获取指定数目的 `IReferenceIdentity` 对象。|  
|`IEnumReferenceIdentity::Reset`|将指令指针移动到此 `IEnumReferenceIdentity`的开头。|  
|`IEnumReferenceIdentity::Skip`|从当前位置开始，将指令指针向前移动指定数量的元素。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** 隔离。h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [合成接口](fusion-interfaces.md)
- [IReferenceIdentity 接口](ireferenceidentity-interface.md)
