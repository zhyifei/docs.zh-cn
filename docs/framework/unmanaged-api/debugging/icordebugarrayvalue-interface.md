---
title: ICorDebugArrayValue Interface1
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
ms.openlocfilehash: 7b8e9e9c9f43b45bf4f5d65bf80394c0fcd71325
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559263"
---
# <a name="icordebugarrayvalue-interface1"></a>ICorDebugArrayValue Interface1
表示一维或多维数组的 ICorDebugHeapValue 子类。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetBaseIndicies 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|获取数组中的每个维的基索引。|  
|[GetCount 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|获取数组中的元素总数。|  
|[GetDimensions 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|获取数组的维数。|  
|[GetElement 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|获取表示给定的数组中元素的值。|  
|[GetElementAtPosition 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|获取位于给定位置，将数组视为从零开始的一维数组的元素。|  
|[GetElementType 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|获取数组中元素的简单类型。|  
|[GetRank 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|获取数组中的维度数。|  
|[HasBaseIndicies 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|确定数组是否具有基索引。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugArrayValue` 支持单维度和多维数组。  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
