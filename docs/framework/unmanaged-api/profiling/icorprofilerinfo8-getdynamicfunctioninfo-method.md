---
title: ICorProfilerInfo8::GetDynamicFunctionInfo
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetDynamicFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: d59de04e6af6cfec473899e0a3edadcb3257d385
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69665685"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a>ICorProfilerInfo8:: GetDynamicFunctionInfo 方法

检索有关动态方法的信息。

## <a name="syntax"></a>语法

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

#### <a name="parameters"></a>参数

`functionId` \
中要为其检索信息的函数的 ID。

`moduleId` \
中指向定义函数父类的模块的指针。

`ppvSig` \
弄指向函数的签名的指针。

`pbSig` \
弄指向函数签名的字节计数的指针。

`cchName` \
[in] `wszName` 数组的最大大小。

`pcchName` \
弄`wszName`数组中的字符数。

`wszName` \
弄一个数组`WCHAR` , 它是函数的名称 (如果存在)。

## <a name="remarks"></a>备注

某些方法 (如 IL 存根或 LCG) 没有关联的元数据, 可以使用[IMetaDataImport](../metadata/imetadataimport-interface.md)和[IMetaDataImport2](../metadata/imetadataimport2-interface.md) api 来检索这些元数据。 探查器可以通过指令指针或通过侦听[ICorProfilerCallback8::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)来遇到此类方法。

此 API 可用于检索有关动态方法的信息, 包括友好名称 (如果可用)。

## <a name="requirements"></a>要求

**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。

**标头：** Corprof.idl, Corprof.idl

**类库**CorGuids.lib

**.NET Framework 版本:** [!包括[net_current_v472plus](../../../../includes/net-current-v472plus.md)

## <a name="see-also"></a>请参阅

- [ICorProfilerInfo8 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
