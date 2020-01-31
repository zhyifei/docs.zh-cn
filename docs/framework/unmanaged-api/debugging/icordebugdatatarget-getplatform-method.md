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
ms.openlocfilehash: 3654c94975d16e35d5c3d8e762730d17509a2c6d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788882"
---
# <a name="icordebugdatatargetgetplatform-method"></a>ICorDebugDataTarget::GetPlatform 方法
提供有关平台的信息，包括在其上运行目标进程的处理器体系结构和操作系统。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a>参数  
 `pTargetPlatform`  
 弄指向描述目标平台的[CorDebugPlatformEnum](cordebugplatform-enumeration.md)枚举的指针。  
  
## <a name="remarks"></a>备注  
 `CorDebugPlatformEnum` 枚举返回值由[ICorDebug](icordebug-interface.md)接口用于确定目标进程的详细信息，例如，其指针大小、地址空间布局、寄存器集、指令格式、上下文布局和调用约定。  
  
 `pTargetPlatform` 值可能引用正在为目标模拟的平台，而不是指定使用中的实际硬件。 例如，在 windows 操作系统的64位版本上，在 windows on windows （WOW）环境中运行的进程应使用[CorDebugPlatformEnum](cordebugplatform-enumeration.md)枚举的 `CORDB_PLATFORM_WINDOWS_X86` 值。  
  
 此方法必须成功。 如果该操作失败，目标平台将无法使用。 此方法可能会由于以下原因而失败：  
  
- 正在为目标模拟的平台不可用。  
  
- 目标平台上的实际硬件不可用。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugDataTarget 接口](icordebugdatatarget-interface.md)
- [调试接口](debugging-interfaces.md)
- [调试](index.md)
