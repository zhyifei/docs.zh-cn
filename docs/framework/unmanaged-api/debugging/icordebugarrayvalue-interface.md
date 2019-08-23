---
title: ICorDebugArrayValue 接口
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue interface
helpviewer_keywords:
- ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99bd3e9ae1faec1b71933681fadf4816b4789c98
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952208"
---
# <a name="icordebugarrayvalue-interface"></a>ICorDebugArrayValue 接口

表示一维或多维数组的 ICorDebugHeapValue 的子类。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetBaseIndicies 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|获取数组中每个维的基索引。|  
|[GetCount 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|获取数组中的元素总数。|  
|[GetDimensions 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|获取数组的尺寸。|  
|[GetElement 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|获取一个值, 该值表示数组中的给定元素。|  
|[GetElementAtPosition 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|获取位于给定位置的元素, 并将该数组视为从零开始的一维数组。|  
|[GetElementType 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|获取数组中元素的简单类型。|  
|[GetRank 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|获取数组中的维度数。|  
|[HasBaseIndicies 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|确定数组是否具有基索引。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugArrayValue`支持一维数组和多维数组。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl, Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
