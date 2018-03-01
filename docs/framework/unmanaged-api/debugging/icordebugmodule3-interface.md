---
title: "ICorDebugModule3 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugModule3
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3
helpviewer_keywords:
- ICorDebugModule3 interface [.NET Framework debugging]
ms.assetid: 0b69f945-263a-4e11-8512-89d27f6ea296
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b864b057e274424a8515ab1bb122da74538c4c63
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule3-interface"></a>ICorDebugModule3 接口
为动态模块创建符号读取器。  
  
## <a name="syntax"></a>语法  
  
```  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[ICorDebugModule3::CreateReaderForInMemorySymbols 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-createreaderforinmemorysymbols-method.md)|创建符号读取器 (通常[ISymUnmanagedReader 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) 为动态模块。|  
  
## <a name="remarks"></a>备注  
 此接口进行逻辑扩展的"icor 调试模块"和"ICorDebugModule2"接口。  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**4.5、 4、 3.5 SP1  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugRemoteTarget 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [ICorDebug 接口](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
