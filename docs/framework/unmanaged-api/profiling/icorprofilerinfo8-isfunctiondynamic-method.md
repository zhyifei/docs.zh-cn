---
title: ICorProfilerInfo8::IsFunctionDynamic
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.IsFunctionDynamic
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 046db493db77572904a8454a5b002dcae15b9e1d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661160"
---
# <a name="icorprofilerinfo8isfunctiondynamic-method"></a>ICorProfilerInfo8:: IsFunctionDynamic 方法

确定函数是否没有关联的元数据。

## <a name="syntax"></a>语法

```cpp
HRESULT IsFunctionDynamic( [in]  FunctionID  functionId,
                           [out] BOOL        *isDynamic);
```

#### <a name="parameters"></a>参数

`functionId` \
中 `FunctionID`标识相关函数的。

`isDynamic` \
弄指向的指针`BOOL` , 它将包含一个值, 该值指示函数是否没有元数据。

## <a name="remarks"></a>备注

如果函数没有元数据, 则将其视为动态函数。 某些方法 (如 IL 存根或 LCG 方法) 没有关联的元数据, 可以使用 IMetaDataImport Api 来检索这些元数据。 探查器可以通过指令指针或通过侦听 ICorProfilerCallback 来完成这些方法[::D ynamicmethodjitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)。

## <a name="requirements"></a>要求

**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。

**标头：** Corprof.idl, Corprof.idl

**类库**CorGuids.lib

**.NET Framework 版本:** [!包括[net_current_v472plus](../../../../includes/net-current-v472plus.md)

## <a name="see-also"></a>请参阅

- [ICorProfilerInfo8 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
