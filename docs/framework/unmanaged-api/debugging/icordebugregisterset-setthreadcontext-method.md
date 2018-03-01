---
title: "ICorDebugRegisterSet::SetThreadContext 方法"
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
- ICorDebugRegisterSet.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetThreadContext
helpviewer_keywords:
- ICorDebugRegisterSet::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 73afa930-32cb-4c40-81f8-83e8e6fbe213
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1ac081cbd1fef0ca46750d8d7a74a22f23dbf0bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregistersetsetthreadcontext-method"></a>ICorDebugRegisterSet::SetThreadContext 方法
`SetThreadContext`在.NET Framework 2.0 版中未实现。 请勿调用此方法。  
  
> [!NOTE]
>  使用更高级别的操作[icordebugnativeframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)设置线程的上下文。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** 1.1、 1.0  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugRegisterSet 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [ICorDebugRegisterSet2 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
