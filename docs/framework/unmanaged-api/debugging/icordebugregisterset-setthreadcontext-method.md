---
title: ICorDebugRegisterSet::SetThreadContext 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b1ea34c187de99d23b05b5e1a30c53bc54a6c0c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197394"
---
# <a name="icordebugregistersetsetthreadcontext-method"></a>ICorDebugRegisterSet::SetThreadContext 方法
`SetThreadContext` 在.NET Framework 2.0 版中未实现。 请勿调用此方法。  
  
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
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** 1.1, 1.0  
  
## <a name="see-also"></a>请参阅

- [ICorDebugRegisterSet 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
