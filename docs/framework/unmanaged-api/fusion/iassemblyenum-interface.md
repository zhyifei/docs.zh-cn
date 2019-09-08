---
title: IAssemblyEnum 接口
ms.date: 03/30/2017
api_name:
- IAssemblyEnum
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum
helpviewer_keywords:
- IAssemblyEnum interface [.NET Framework fusion]
ms.assetid: 634ef9f9-e94b-4776-a9e1-866df9a76c8f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0338c1e3e8890f08f87c80ec922071053d591935
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796671"
---
# <a name="iassemblyenum-interface"></a>IAssemblyEnum 接口
表示`IAssemblyName`对象数组的枚举器。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Clone 方法](iassemblyenum-clone-method.md)|创建此`IAssemblyEnum`对象的浅表副本。|  
|[GetNextAssembly 方法](iassemblyenum-getnextassembly-method.md)|获取一个指针，该指针`IAssemblyName`指向此`IAssemblyEnum`对象中包含的下一个。|  
|[Reset 方法](iassemblyenum-reset-method.md)|将此`IAssemblyEnum`对象重置为其起始位置。|  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** 合成。h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [合成接口](fusion-interfaces.md)
- [IAssemblyName 接口](iassemblyname-interface.md)
