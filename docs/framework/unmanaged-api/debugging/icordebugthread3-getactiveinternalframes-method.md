---
title: "ICorDebugThread3::GetActiveInternalFrames 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread3.GetActiveInternalFrames Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8ecfbaeff9416ee8e6541a23bac6ec76f99abd2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread3getactiveinternalframes-method"></a>ICorDebugThread3::GetActiveInternalFrames 方法
返回内部帧的数组 ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)对象) 堆栈上。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
#### <a name="parameters"></a>参数  
 `cInternalFrames`  
 [in]预期中的内部帧的数目`ppInternalFrames`。  
  
 `pcInternalFrames`  
 [out]指向的指针`ULONG32`，其中包含的堆栈上的内部帧的数目。  
  
 `ppInternalFrames`  
 [在中，out]指向数组内部堆栈上框架的地址的指针。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|[ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)已成功创建对象。|  
|E_INVALIDARG|`cInternalFrames`不为零和`ppInternalFrames`是`null`，或`pcInternalFrames`是`null`。|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|`ppInternalFrames`小于内部帧的计数。|  
  
## <a name="exceptions"></a>异常  
  
## <a name="remarks"></a>备注  
 内部帧是推送到堆栈由运行时存储临时数据的数据结构。  
  
 当你第一次调用`GetActiveInternalFrames`，应设置`cInternalFrames`参数设为 0 （零），和`ppInternalFrames`参数为 null。 当`GetActiveInternalFrames`首先返回，`pcInternalFrames`包含在堆栈上的内部帧的计数。  
  
 `GetActiveInternalFrames`然后应可以调用第二次。 应传递适当的计数 (`pcInternalFrames`) 中`cInternalFrames`参数，并指定指向数组中的相应大小的`ppInternalFrames`。  
  
 使用[icordebugstackwalk:: Getframe](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md)方法以返回实际堆栈帧。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
