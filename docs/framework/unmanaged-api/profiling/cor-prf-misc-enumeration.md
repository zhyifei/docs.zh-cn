---
title: COR_PRF_MISC 枚举
ms.date: 03/30/2017
api_name:
- COR_PRF_MISC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MISC
helpviewer_keywords:
- COR_PRF_MISC enumeration [.NET Framework profiling]
ms.assetid: 619bb5de-e309-48b6-a3af-32d935a0ff46
topic_type:
- apiref
ms.openlocfilehash: 8105ba34ca400771fbc4273630f20941a4a9557d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432275"
---
# <a name="cor_prf_misc-enumeration"></a>COR_PRF_MISC 枚举
包含指定特殊标识符的常数值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a>Members  
  
|成员|说明|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|[ICorProfilerInfo：： GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)用于尚未附加到程序集的模块的默认标识符。|  
|`PROFILER_GLOBAL_CLASS`|不属于类的全局常数的默认类标识符。|  
|`PROFILER_GLOBAL_MODULE`|不属于模块的全局对象的默认模块标识符。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [分析枚举](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
