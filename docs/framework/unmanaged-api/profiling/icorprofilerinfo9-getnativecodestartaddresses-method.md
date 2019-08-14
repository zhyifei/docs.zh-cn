---
title: ICorProfilerInfo9::GetNativeCodeStartAddresses
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetNativeCodeStartAddresses
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: f5c7f11a322e4cf3ed38608e0f380dd632bc8fb6
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973807"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a>ICorProfilerInfo9:: GetNativeCodeStartAddresses 方法
  
 给定一个 functionId 和 rejitId, 枚举此代码当前存在的所有实时编译版本的本机代码起始地址。   
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```  
  
#### <a name="parameters"></a>参数  
 `functionId`  
 中应返回其本机代码起始地址的函数的 ID。  
  
 `reJitId`  
 [in] JIT 重新编译的函数的标识。 
  
 `cCodeStartAddresses` \
 [in] `codeStartAddresses` 数组的最大大小。

 `pcCodeStartAddresses` \
 弄可用地址的数目。

 `codeStartAddresses` \
 弄的`UINT_PTR`数组, 其中每个都是指定函数的本机正文的开始地址。 

## <a name="remarks"></a>备注  
 启用分层编译后, 函数可能有多个本机代码体。 

## <a name="requirements"></a>要求  
 **适用**请参阅[支持 .Net Core 的操作系统](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)。  
  
 **标头：** Corprof.idl, Corprof.idl  
  
 **类库**CorGuids.lib  
  
 **.Net 版本:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)] 
  
## <a name="see-also"></a>请参阅
- [ICorProfilerInfo9 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)

