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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 48617022940d889abedb9a9d25f04782371c4a5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451940"
---
# <a name="corprfmoduleflags-enumeration"></a>COR_PRF_MODULE_FLAGS 枚举
指定模块的属性。  
  
## <a name="syntax"></a>语法  
  
```  
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
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|COR_PRF_MODULE_DISK|从磁盘加载了该模块。|  
|COR_PRF_MODULE_NGEN|该模块是由本机映像生成器 (Ngen.exe) 生成的。|  
|COR_PRF_MODULE_DYNAMIC|通过中的方法创建模块<xref:System.Reflection.Emit?displayProperty=nameWithType>命名空间。|  
|COR_PRF_MODULE_COLLECTIBLE|模块的生存期由垃圾回收器管理。|  
|COR_PRF_MODULE_RESOURCE|模块不包含元数据，通常仅限于作为资源。 此位的托管等效项是<xref:System.Reflection.Module.IsResource%2A?displayProperty=nameWithType>方法。|  
|COR_PRF_MODULE_FLAT_LAYOUT|在内存中的模块的布局不变，未映射。 如果模块已设置此位，探查器可读取必须直接从可移植可执行 (PE) 文件头的信息解释标头中的相对虚拟地址 (Rva) 时要小心。|  
|COR_PRF_MODULE_WINDOWS_RUNTIME|Windows 运行时的内容类型标志为元数据中设置此模块的程序集。 这是所有的 Windows 元数据 (.winmd) 模块的大小写。|  
  
## <a name="remarks"></a>备注  
 从 COR_PRF_MODULE_FLAGS 位将返回到探查器在`pdwModuleFlags`输出参数的[icorprofilerinfo3:: Getmoduleinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md)方法。 某些组合两个或多个标志是可能的但并非所有组合都都可能。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [分析枚举](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
