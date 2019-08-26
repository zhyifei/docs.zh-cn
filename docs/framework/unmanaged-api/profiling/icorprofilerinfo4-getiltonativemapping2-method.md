---
title: ICorProfilerInfo4::GetILToNativeMapping2 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetILToNativeMapping2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2
helpviewer_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2 method [.NET Framework profiling]
- GetILToNativeMapping2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 756c1c25-08a7-4060-9798-dbeaa2f3bee5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a8ffdb04bdf3fd2f605e2dffc5065a0d786bbaf7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967908"
---
# <a name="icorprofilerinfo4getiltonativemapping2-method"></a>ICorProfilerInfo4::GetILToNativeMapping2 方法
针对指定函数的 JIT 重新编译版本中包含的代码，获取 Microsoft 中间语言 (MSIL) 偏移量到本机偏移量的映射。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ReJITID reJitId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
## <a name="parameters"></a>参数  
 `functionId`  
 [in] 包含代码的函数 ID。  
  
 `pReJitId`  
 [in] JIT 重新编译的函数的标识。 .NET Framework 4.5 中的标识必须为零。  
  
 `cMap`  
 [in] `map` 数组的最大大小。  
  
 `pcMap`  
 弄可用的 COR_DEBUG_IL_TO_NATIVE_MAP 结构总数。  
  
 `map`  
 [out] `COR_DEBUG_IL_TO_NATIVE_MAP` 结构的数组，其中每个结构均指定偏移量。 `GetILToNativeMapping2` 方法返回后，`map` 将包含部分或全部 `COR_DEBUG_IL_TO_NATIVE_MAP` 结构。  
  
## <a name="remarks"></a>备注  
 `GetILToNativeMapping2`与[ICorProfilerInfo:: GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)方法类似, 只是它允许探查器在将来的版本中指定重新编译的函数的 ID。  
  
> [!NOTE]
> .NET Framework 4.5 中未实现[ICorProfilerFunctionControl:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)方法, 因此, JIT 重新编译的函数不能具有与最初编译的函数不同的 IL 到本机映射。 因此, `GetILToNativeMapping2`在 .NET Framework 4.5 中不能使用非零 JIT 重新编译的 ID 调用。  
  
 `GetILToNativeMapping2` 方法返回 `COR_DEBUG_IL_TO_NATIVE_MAP` 结构的数组。 为了传达特定范围的本机指令与代码的特殊区域 (例如序言) 相对应, 数组中的条目可以将其`ilOffset`字段设置为[CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md)枚举的值。  
  
 返回 `GetILToNativeMapping2` 后，必须验证 `map` 缓冲区大小是否足以包含所有 `COR_DEBUG_IL_TO_NATIVE_MAP` 结构。 为此，请将 `cMap` 的值和 `pcMap` 参数的值进行比较。 如果 `pcMap` 值乘以 `COR_DEBUG_IL_TO_NATIVE_MAP` 结构的大小所得的值大于 `cMap`，请分配更大的 `map` 缓冲区、将 `cMap` 更新为新的更大大小，并再次调用 `GetILToNativeMapping2`。  
  
 或者，可以先用长度为零的 `map` 缓冲区调用 `GetILToNativeMapping2` 以获取正确的缓冲区大小。 然后，可将缓冲区大小设置为 `pcMap` 中返回的值，并再次调用 `GetILToNativeMapping2`。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Corprof.idl, Corprof.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [GetILToNativeMapping 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [ICorProfilerInfo4 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [分析](../../../../docs/framework/unmanaged-api/profiling/index.md)
