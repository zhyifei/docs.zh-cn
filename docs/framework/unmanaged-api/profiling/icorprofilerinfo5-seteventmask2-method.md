---
title: ICorProfilerInfo5::SetEventMask2 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- IcorProfilerInfo5.SetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 05dbbe2b-049c-4a60-be69-2ad7a949405e
topic_type:
- apiref
ms.openlocfilehash: 10e84b729c8af607165009a8591a69dbc1afcb1e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868377"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a>ICorProfilerInfo5::SetEventMask2 方法
[仅在 .NET Framework 4.5.2 及更高版本中受支持]  
  
 设置一个值，用于指定探查器需要从公共语言运行时 (CLR) 接收其事件通知的事件的类型。 它提供的功能比[ICorProfilerInfo：： SetEventMask](icorprofilerinfo-seteventmask-method.md)方法更多。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a>参数  
 `dwEventsLow`  
 [in] 一个指定事件类别的 4 字节的值。 每个位都可控制不同的功能、行为或事件类型。 [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md)枚举中描述了这些位。  
  
 `dwEventsHigh`  
 [in] 一个指定事件类别的 4 字节的值。  每个位都可控制不同的功能、行为或事件类型。 [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md)枚举中描述了这些位。  
  
## <a name="remarks"></a>备注  
 `SetEventMask2` 方法用于设置探查器订阅的回调。 通常，你可以调用[GetEventMask2](icorprofilerinfo5-geteventmask2-method.md)方法来确定设置了哪些位、执行 `pdwEventsLow` 的逻辑或，并 `pdwEventsHigh` 值和要设置的任何新位，然后调用 `SetEventMask2` 方法。  
  
 此方法是[SetEventMask](icorprofilerinfo-seteventmask-method.md)方法的建议替代方法。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo5 接口](icorprofilerinfo5-interface.md)
- [GetEventMask2 方法](icorprofilerinfo5-geteventmask2-method.md)
