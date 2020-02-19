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
ms.openlocfilehash: 22fe5608b0a3f86baf80abb3810a512077954ac3
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449746"
---
# <a name="icorprofilerinfo9getiltonativemapping3-method"></a>ICorProfilerInfo9：： GetILToNativeMapping3 方法

给定本机代码起始地址，返回此实时编译版本的代码的本机到 IL 映射信息。

## <a name="syntax"></a>语法

```cpp
HRESULT GetILToNativeMapping3( [in]  UINT_PTR pNativeCodeStartAddress,
                               [in]  ULONG32 cMap,
                               [out] ULONG32 *pcMap,
                               [out] COR_DEBUG_IL_TO_NATIVE_MAP map[]);
```

## <a name="parameters"></a>参数

- `pNativeCodeStartAddress`

  \[中的）指向本机函数开头的指针。

- `cMap`

  \[] `map` 数组的最大大小。

- `pcMap`

  \[out] 可用 COR_DEBUG_IL_TO_NATIVE_MAP 结构的总数。

- `map`

  \[out] [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md)结构的数组，其中每个结构指定偏移量。 `GetILToNativeMapping3` 方法返回后，`map` 将包含部分或全部 `COR_DEBUG_IL_TO_NATIVE_MAP` 结构。

## <a name="remarks"></a>备注

当启用分层编译时，一个方法可能有多个本机代码体。 [ICorProfilerInfo9：： GetNativeCodeStartAddresses](icorprofilerinfo9-getnativecodestartaddresses-method.md)将返回所有本机代码正文的开始地址。

## <a name="requirements"></a>要求

**平台：** 请参阅[支持 .Net Core 的操作系统](../../../core/install/dependencies.md?pivots=os-windows)。

**头文件：** CorProf.idl、CorProf.h

**库：** CorGuids.lib

**.NET Framework 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo9 接口](icorprofilerinfo9-interface.md)
