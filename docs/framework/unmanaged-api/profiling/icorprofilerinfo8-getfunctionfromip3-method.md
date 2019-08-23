---
title: ICorProfilerInfo8::GetFunctionFromIP3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetFunctionFromIP3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 7b0d8033a5ea3b98623b9be384788ef7fc15bf04
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69665633"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a>ICorProfilerInfo8:: GetFunctionFromIP3 方法

将托管代码指令指针映射到 FunctionID。 此方法适用于动态和非动态方法。

## <a name="syntax"></a>语法

```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```

#### <a name="parameters"></a>参数

`ip` \
中托管代码中的指令指针。

`pFunctionId` \
弄函数 ID。

`pReJitId` \
弄函数的 JIT 重新编译版本的标识。

## <a name="remarks"></a>备注

此方法适用于动态和非动态方法。 它是[GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md)的超集, 只适用于具有元数据的函数。

## <a name="requirements"></a>要求

**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。

**标头：** Corprof.idl, Corprof.idl

**类库**CorGuids.lib

**.NET Framework 版本:** [!包括[net_current_v472plus](../../../../includes/net-current-v472plus.md)

## <a name="see-also"></a>请参阅

- [ICorProfilerInfo8 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
