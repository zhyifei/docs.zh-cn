---
title: ICorDebug::DebugActiveProcess 方法
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84137e7163101f7eaa54a45df0fbaa4e7bcf70fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404581"
---
# <a name="icordebugdebugactiveprocess-method"></a>ICorDebug::DebugActiveProcess 方法
将调试器附加到现有的进程。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
#### <a name="parameters"></a>参数  
 `id`  
 [in]调试器是要附加的进程的 ID。  
  
 `win32Attach`  
 [in]布尔值，设置为`true`如果调试器应相当于 Win32 调试器进程并将其分派非托管的回调中; 否则为`false`。  
  
 `ppProcess`  
 [out]指向表示调试器附加到进程"ICorDebugProcess"对象的地址的指针。  
  
## <a name="remarks"></a>备注  
 不支持 Win9x 和非 x86 平台，例如-基于 IA-64 和 AMD64 基于平台进行互操作调试。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebug 接口](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
