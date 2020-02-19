---
title: COR_PRF_REJIT_FLAGS 枚举
ms.date: 08/06/2019
api_name:
- COR_PRF_REJIT_FLAGS Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_REJIT_FLAGS
helpviewer_keywords:
- COR_PRF_REJIT_FLAGS enumeration [.NET Framework profiling]
topic_type:
- apiref
author: davmason
ms.author: davmason
ms.openlocfilehash: 3b4f85072b9dcf87d696b979fa6cbf4e59393f82
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453034"
---
# <a name="cor_prf_rejit_flags-enumeration"></a>COR_PRF_REJIT_FLAGS 枚举
包含指示[ICorProfilerInfo10：： RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API 应如何运行的值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum  
{      
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a>Members  
  
|成员|说明|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| 将阻止在其他方法中内联 ReJITted 方法。 |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| 为内联 ReJITted 请求的方法的任何方法接收 `GetFunctionParameters` 回调。 |  

## <a name="requirements"></a>要求  
 **平台：** 请参阅[支持 .Net Core 的操作系统](../../../core/install/dependencies.md?pivots=os-windows)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)] 
  
## <a name="see-also"></a>另请参阅

- [分析枚举](profiling-enumerations.md)
