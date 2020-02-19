---
title: ICorProfilerInfo10::ResumeRuntime
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.ResumeRuntime
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: a3dca2cbb138dbc43f477488032e67335c8b15f9
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452157"
---
# <a name="icorprofilerinfo10resumeruntime-method"></a>ICorProfilerInfo10：： ResumeRuntime 方法

恢复运行时，而不执行 GC。

## <a name="syntax"></a>语法

```cpp
HRESULT ResumeRuntime();
```

## <a name="requirements"></a>要求

**平台：** 请参阅[支持 .Net Core 的操作系统](../../../core/install/dependencies.md?pivots=os-windows)。

**头文件：** CorProf.idl、CorProf.h

**库：** CorGuids.lib

**.Net 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo10 接口](icorprofilerinfo10-interface.md)
