---
title: ICorProfilerInfo10::GetLOHObjectSizeThreshold
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.GetLOHObjectSizeThreshold
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: d4d498c1d75625b2abc37dc1f4c88d73b58ec675
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790018"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a>ICorProfilerInfo10：： GetLOHObjectSizeThreshold 方法

获取已配置的大型对象堆（LOH）阈值的值。

## <a name="syntax"></a>语法

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a>参数

- `pThreshold`

  \[out] 大对象堆阈值（以字节为单位）。

## <a name="remarks"></a>备注

大于大型对象堆阈值的对象将在大型对象堆上分配。 从 .NET Core 3.0 开始，可以配置大对象堆阈值，`pThreshold` 将包含活动的大型对象堆阈值大小（以字节为单位）。

## <a name="requirements"></a>需求

**平台：** 请参阅[支持 .Net Core 的操作系统](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)。

**头文件：** CorProf.idl、CorProf.h

**库：** CorGuids.lib

**.Net 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo10 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
