---
title: ASM_CACHE_FLAGS 枚举
ms.date: 03/30/2017
api_name:
- ASM_CACHE_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_CACHE_FLAGS
helpviewer_keywords:
- ASM_CACHE_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 82e9a7da-321b-48b8-b239-52eaffda6be8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e3e9da3db71d3e24b2a60ff032a631680055b88
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795285"
---
# <a name="asm_cache_flags-enumeration"></a>ASM_CACHE_FLAGS 枚举
指示由全局程序集缓存中的[IAssemblyCacheItem](iassemblycacheitem-interface.md)表示的程序集的源。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|使用 Ngen.exe 枚举预编译程序集的缓存。|  
|`ASM_CACHE_GAC`|枚举全局程序集缓存。|  
|`ASM_CACHE_DOWNLOAD`|枚举已按需下载或已进行卷影复制的程序集。|  
|`ASM_CACHE_ROOT`|指示[GetCachePath](getcachepath-function.md)函数应返回公共语言运行时（CLR）版本2.0 的全局程序集缓存的路径。 仅在对[GetCachePath](getcachepath-function.md)的调用上下文中有意义。|  
|`ASM_CACHE_ROOT_EX`|指示[GetCachePath](getcachepath-function.md)函数应返回 CLR 版本4的全局程序集缓存的路径。 仅在对[GetCachePath](getcachepath-function.md)的调用上下文中有意义。|  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** 合成。h  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [GetCachePath 函数](getcachepath-function.md)
- [IAssemblyCacheItem 接口](iassemblycacheitem-interface.md)
- [合成枚举](fusion-enumerations.md)
