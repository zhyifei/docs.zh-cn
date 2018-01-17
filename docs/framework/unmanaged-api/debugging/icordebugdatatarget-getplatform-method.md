---
title: "ICorDebugDataTarget::GetPlatform 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugDataTarget.GetPlatform Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c19e472ef571def1011d2a00701fea3a6fadfea8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatargetgetplatform-method"></a>ICorDebugDataTarget::GetPlatform 方法
提供有关平台，包括处理器体系结构和目标进程正在其运行的操作系统的信息。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
#### <a name="parameters"></a>参数  
 `pTargetPlatform`  
 [out]指向的指针[CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md)描述目标平台的枚举。  
  
## <a name="remarks"></a>备注  
 `CorDebugPlatformEnum`枚举返回的值由[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)接口来确定目标进程，如其指针大小、 地址空间布局、 注册设置、 指令格式、 上下文布局的详细信息和调用约定。  
  
 `pTargetPlatform`值可能引用而不是在使用指定实际硬件的目标模拟的平台。 例如，在 64 位版本的 Windows 操作系统在 Windows (WOW) 环境上的 Windows 中运行的进程应使用`CORDB_PLATFORM_WINDOWS_X86`值[CorDebugPlatformEnum](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md)枚举。  
  
 此方法必须成功。 如果失败，则目标平台是不可用。 该方法可能会出于以下原因失败：  
  
-   目标模拟该平台是不可用。  
  
-   目标平台上的实际硬件不可用。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugDataTarget 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
