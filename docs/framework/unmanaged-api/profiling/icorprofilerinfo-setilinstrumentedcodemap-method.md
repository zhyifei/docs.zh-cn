---
title: ICorProfilerInfo::SetILInstrumentedCodeMap 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetILInstrumentedCodeMap method [.NET Framework profiling]
ms.assetid: bce1dcf8-b4ec-4e73-a917-f2df1ad49c8a
topic_type:
- apiref
ms.openlocfilehash: 32e63a6d2b6f739025d4c5558c16fe2d74fde73c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449863"
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a>ICorProfilerInfo::SetILInstrumentedCodeMap 方法

使用指定的 Microsoft 中间语言（MSIL）映射项为指定的函数设置代码图。

> [!NOTE]
> 在 .NET Framework 版本2.0 中，对表示特定应用程序域中的泛型函数的 `FunctionID` 调用 `SetILInstrumentedCodeMap` 将影响应用程序域中该函数的所有实例。

## <a name="syntax"></a>语法

```cpp
HRESULT SetILInstrumentedCodeMap(
    [in]  FunctionID functionId,
    [in]  BOOL       fStartJit,
    [in]  ULONG      cILMapEntries,
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);
```

## <a name="parameters"></a>参数

`functionId`\
中要为其设置代码图的函数的 ID。

`fStartJit`\
中一个布尔值，该值指示对 `SetILInstrumentedCodeMap` 方法的调用是否为特定 `FunctionID`的第一个。 将 `fStartJit` 设置为在第一次调用给定 `FunctionID``SetILInstrumentedCodeMap` 时 `true`，然后 `false`。

`cILMapEntries`\
中`cILMapEntries` 数组中的元素数。

`rgILMapEntries`\
中COR_IL_MAP 结构的数组，其中每个结构指定 MSIL 偏移量。

## <a name="remarks"></a>备注

探查器通常在方法的源代码中插入语句，以便检测该方法（例如，当到达给定的源行时发出通知）。 `SetILInstrumentedCodeMap` 使探查器能够将原始 MSIL 指令映射到新位置。 探查器可以使用[ICorProfilerInfo：： GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)方法获取给定本机偏移量的原始 MSIL 偏移量。

调试器将假设每个旧偏移都是在原始的、未修改的 MSIL 代码内引用 MSIL 偏移量，并且每个新偏移指的是新的、经过检测的代码内的 MSIL 偏移量。 地图应按递增顺序排序。 若要单步执行，请遵循以下准则：

- 不要对已检测的 MSIL 代码重新排序。

- 请勿删除原始的 MSIL 代码。

- 为映射中的程序数据库（PDB）文件中的所有序列点包含条目。 地图未插入缺失的条目。 因此，假设有以下映射：

  （0个旧，0个新的）

  （5个旧，10个新的）

  （9个旧，20个新的）

  - 早于0、1、2、3或4的偏移将映射到新的偏移量0。

  - 旧偏移量5、6、7或8将映射到新的偏移量10。

  - 旧偏移量9或更高将映射到新偏移量20。

  - 新偏移量为0、1、2、3、4、5、6、7、8或9，将映射到旧偏移量0。

  - 新偏移量为10、11、12、13、14、15、16、17、18或19，将映射到旧偏移量5。

  - 20或更高的新偏移量将映射到旧偏移量9。

在 .NET Framework 3.5 和以前的版本中，通过调用[CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc)方法来分配 `rgILMapEntries` 数组。 由于运行时取得了此内存的所有权，因此探查器不应尝试释放它。

## <a name="requirements"></a>要求

**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。

**头文件：** CorProf.idl、CorProf.h

**库：** CorGuids.lib

**.NET Framework 版本：** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]

## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
