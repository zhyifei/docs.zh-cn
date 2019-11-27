---
title: COR_PRF_MODULE_FLAGS 枚举
ms.date: 03/30/2017
api_name:
- COR_PRF_MODULE_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MODULE_FLAGS
helpviewer_keywords:
- COR_PRF_MODULE_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 7bc3a938-0df1-4739-9ff1-89cff454b704
topic_type:
- apiref
ms.openlocfilehash: bdbf93ba4df50cf26538f0e527fdc3c982bb274e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447330"
---
# <a name="cor_prf_module_flags-enumeration"></a>COR_PRF_MODULE_FLAGS 枚举
指定模块的属性。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum  
{  
    COR_PRF_MODULE_DISK             = 0x00000001,  
    COR_PRF_MODULE_NGEN             = 0x00000002,  
    COR_PRF_MODULE_DYNAMIC          = 0x00000004,  
    COR_PRF_MODULE_COLLECTIBLE      = 0x00000008,  
    COR_PRF_MODULE_RESOURCE         = 0x00000010,  
    COR_PRF_MODULE_FLAT_LAYOUT      = 0x00000020,  
    COR_PRF_MODULE_WINDOWS_RUNTIME  = 0x00000040  
}   COR_PRF_MODULE_FLAGS;  
```  
  
## <a name="members"></a>Members  
  
|成员|说明|  
|------------|-----------------|  
|COR_PRF_MODULE_DISK|模块是从磁盘加载的。|  
|COR_PRF_MODULE_NGEN|模块是由本机映像生成器（Ngen.exe）生成的。|  
|COR_PRF_MODULE_DYNAMIC|模块是由 <xref:System.Reflection.Emit?displayProperty=nameWithType> 命名空间中的方法创建的。|  
|COR_PRF_MODULE_COLLECTIBLE|模块的生存期由垃圾回收器管理。|  
|COR_PRF_MODULE_RESOURCE|该模块不包含元数据，并严格用作资源。 此位的托管等效项是 <xref:System.Reflection.Module.IsResource%2A?displayProperty=nameWithType> 方法。|  
|COR_PRF_MODULE_FLAT_LAYOUT|模块在内存中的布局是平面的，而不是映射的。 如果模块设置了此位，则当解释标头中的相对虚拟地址（Rva）时，直接从可移植可执行（PE）文件头读取信息的探查器将必须小心。|  
|COR_PRF_MODULE_WINDOWS_RUNTIME|在此模块的程序集的元数据中设置 Windows 运行时内容类型标志。 这适用于所有 Windows 元数据（winmd）模块。|  
  
## <a name="remarks"></a>备注  
 COR_PRF_MODULE_FLAGS 中的位将返回到探查器的[ICorProfilerInfo3：： GetModuleInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md)方法的 `pdwModuleFlags` output 参数中。 可能有两个或更多标志的一些组合，但并非所有组合都可行。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [分析枚举](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
