---
title: ICorDebugThread3::GetActiveInternalFrames 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.GetActiveInternalFrames Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type:
- apiref
ms.openlocfilehash: 680af5afa3ebef5bcaf9e34580e421dcc8093aaf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178468"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a>ICorDebugThread3::GetActiveInternalFrames 方法
返回堆栈上的内部帧数组[（ICorDebug内部Frame2](icordebuginternalframe2-interface.md)对象）。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a>parameters  
 `cInternalFrames`  
 [在]中预期的内部帧数`ppInternalFrames`。  
  
 `pcInternalFrames`  
 [出]指向`ULONG32`包含堆栈上内部帧数的 指针。  
  
 `ppInternalFrames`  
 [进出]指向堆栈上内部帧数组地址的指针。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|说明|  
|-------------|-----------------|  
|S_OK|已成功创建[ICorDebug 内部Frame2](icordebuginternalframe2-interface.md)对象。|  
|E_INVALIDARG|`cInternalFrames``ppInternalFrames`不是零，`null`是 ，`pcInternalFrames`或`null`是 。|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|`ppInternalFrames`小于内部帧的计数。|  
  
## <a name="exceptions"></a>例外  
  
## <a name="remarks"></a>备注  
 内部帧是运行时推送到堆栈以存储临时数据的数据结构。  
  
 首次调用`GetActiveInternalFrames`时，应将`cInternalFrames`参数设置为 0（零），并将`ppInternalFrames`参数设置为 null。 首次`GetActiveInternalFrames`返回时，`pcInternalFrames`包含堆栈上内部帧的计数。  
  
 `GetActiveInternalFrames`然后，应调用第二次。 应在`pcInternalFrames``cInternalFrames`参数中传递正确的计数 （ ），并在 中指定指向适当大小的数组的`ppInternalFrames`指针。  
  
 使用[ICorDebugStackWalk：getFrame](icordebugthread3-getactiveinternalframes-method.md)方法返回实际堆栈帧。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
- [调试](index.md)
