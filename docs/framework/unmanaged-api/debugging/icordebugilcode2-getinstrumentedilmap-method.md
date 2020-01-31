---
title: ICorDebugILCode2::GetInstrumentedILMap 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetInstrumentedILMap
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type:
- apiref
ms.openlocfilehash: 728a6c83dc321fa28dc4ff84c4e874d886524b36
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788560"
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a>ICorDebugILCode2::GetInstrumentedILMap 方法
[仅在 .NET Framework 4.5.2 及更高版本中受支持]  
  
 返回从探查器检测到的中间语言 (IL) 偏移量到此实例的原始方法的 IL 偏移量的映射。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
## <a name="parameters"></a>参数  
 cMap  
 [in] `map` 数组的存储容量。 有关详细信息，请参阅备注部分。  
  
 pcMap  
 [out] 写入映射数组的 COR_IL_MAP 值的数量。  
  
 map  
 [out] 一个 COR_IL_MAP 值的数组，提供了有关从探查器检测到的 IL 到原始方法的 IL 的映射信息。  
  
## <a name="remarks"></a>备注  
 如果探查器通过调用[ICorProfilerInfo：： SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)方法设置映射，则调试器可以调用此方法来检索映射，并在计算堆栈跟踪和变量生存期的 IL 偏移量时在内部使用该映射。  
  
 如果 `cMap` 为0且 `pcMap` 为非**null**，则 `pcMap` 设置为可用 COR_IL_MAP 值的数目。 如果 、`map``cMap` 为非零，则它表示  数组的存储容量。 当方法返回时，`map` 最多包含 `cMap` 项，`pcMap` 设置为实际写入 `map` 数组的 COR_IL_MAP 值的数目。  
  
 如果尚未检测到 IL 或探查器没有提供映射，则此方法将返回 `S_OK` 并将 `pcMap` 设置为 0。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl，Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [ICorDebugILCode2 接口](icordebugilcode2-interface.md)
- [调试接口](debugging-interfaces.md)
