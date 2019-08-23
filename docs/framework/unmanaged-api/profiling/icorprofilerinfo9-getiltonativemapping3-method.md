---
title: ICorProfilerInfo9::GetILToNativeMapping3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetILToNativeMapping3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 9e8e4c7e6c367970100c98dc3dc8237b25f99221
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69665600"
---
# <a name="icorprofilerinfo9getiltonativemapping3-method"></a>ICorProfilerInfo9:: GetILToNativeMapping3 方法

给定本机代码起始地址, 返回此实时编译版本的代码的本机到 IL 映射信息。

## <a name="syntax"></a>语法

```cpp
HRESULT GetILToNativeMapping3( [in]  UINT_PTR pNativeCodeStartAddress,
                               [in]  ULONG32 cMap,
                               [out] ULONG32 *pcMap,
                               [out] COR_DEBUG_IL_TO_NATIVE_MAP map[]);
```

#### <a name="parameters"></a>参数

`pNativeCodeStartAddress` \
中指向本机函数开头的指针。

`cMap` \
[in] `map` 数组的最大大小。

`pcMap` \
弄可用的 COR_DEBUG_IL_TO_NATIVE_MAP 结构总数。

`map` \
弄[COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md)结构的数组, 其中每个结构都指定了偏移量。 `GetILToNativeMapping3` 方法返回后，`map` 将包含部分或全部 `COR_DEBUG_IL_TO_NATIVE_MAP` 结构。

## <a name="remarks"></a>备注

当启用分层编译时, 一个方法可能有多个本机代码体。 [ICorProfilerInfo9:: GetNativeCodeStartAddresses](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md)将返回所有本机代码正文的开始地址。

## <a name="requirements"></a>要求

**适用**请参阅[支持 .Net Core 的操作系统](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)。

**标头：** Corprof.idl, Corprof.idl

**类库**CorGuids.lib

**.NET Framework 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>请参阅

- [ICorProfilerInfo9 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)
