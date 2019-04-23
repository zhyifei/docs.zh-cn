---
title: ICorDebugDataTarget::GetPlatform 方法
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetPlatform Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 309c31dacd801f1c46a2d37932124638bc157cd6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214022"
---
# <a name="icordebugdatatargetgetplatform-method"></a>ICorDebugDataTarget::GetPlatform 方法
提供有关平台，包括处理器体系结构和操作系统，目标进程正在其运行的信息。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a>参数  
 `pTargetPlatform`  
 [out]一个指向[CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md)枚举，用于描述目标平台。  
  
## <a name="remarks"></a>备注  
 `CorDebugPlatformEnum`通过使用枚举返回值[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)接口，以确定目标进程，如其指针大小、 地址空间布局、 注册组、 指令格式、 上下文布局的详细信息和调用约定。  
  
 `pTargetPlatform`值可能引用一个平台，而不是在使用指定实际硬件的目标进行模拟。 例如，在 64 位版本的 Windows 操作系统运行在 Windows 上 Windows (WOW) 环境中的进程应使用`CORDB_PLATFORM_WINDOWS_X86`的值[CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md)枚举。  
  
 此方法必须成功完成。 如果失败，目标平台是不可用。 该方法可能会出于以下原因失败：  
  
-   目标进行模拟的平台是不可用。  
  
-   目标平台上的实际硬件是不可用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugDataTarget 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
