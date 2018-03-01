---
title: "ICorProfilerInfo5::GetEventMask2 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- cpp
api_name:
- ICorProfilerInfo5.GetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: f854b68f-009c-4ffb-89cd-ca874d1c0fb7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 72adbbdc3495f4171f555d119cb61d5dbc5ef0e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo5geteventmask2-method"></a>ICorProfilerInfo5::GetEventMask2 方法
[仅在 .NET Framework 4.5.2 及更高版本中受支持]  
  
 获取探查器要从公共语言运行时 (CLR) 中接收通知的当前事件类别。  它提供了功能不是由[icorprofilerinfo:: Geteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pdwEventsLow`  
 [out] 一个指向指定事件类别的 4 字节值的指针。 每个位都可控制不同的功能、行为或事件类型。 中描述了这些位[COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)枚举。  
  
 `pdwEventsHigh`  
 [out] 一个指向指定事件类别的 4 字节值的指针。  每个位都可控制不同的功能、行为或事件类型。 中描述了这些位[COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)枚举。  
  
## <a name="remarks"></a>备注  
 `GetEventMask2` 方法用于确定探查器已订阅了哪些回调。 通常，你可以执行的逻辑 OR`pdwEventsLow`和`pdwEventsHigh`值以及你想要设置，然后调用任何新位[SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)方法。  
  
 此方法是建议的替代项为[GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)方法。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerInfo5 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 [SetEventMask2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
