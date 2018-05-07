---
title: ICorDebugThread::GetCurrentException 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetCurrentException
helpviewer_keywords:
- ICorDebugThread::GetCurrentException method [.NET Framework debugging]
- GetCurrentException method [.NET Framework debugging]
ms.assetid: 331ed465-a195-4359-8584-b82c6098b29b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82686fdd14783257987ec5bf9a24db7d87049d42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugthreadgetcurrentexception-method"></a>ICorDebugThread::GetCurrentException 方法
获取一个表示托管代码所引发的异常的 ICorDebugValue 对象的接口指针。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppExceptionObject`  
 [out]指向的地址的指针`ICorDebugValue`表示当前所引发的异常的对象托管代码。  
  
## <a name="remarks"></a>备注  
 从异常结束前的时间将存在的异常对象`catch`块。 由 ICorDebugEval 方法执行，则函数求值将清空在安装中的异常对象，并将其还原完成。  
  
 可以嵌套异常，（例如，如果筛选器中或函数求值，将引发异常），所以可能有对单个线程的多个未处理异常。 `GetCurrentException` 返回最新的异常。  
  
 在异常的生命周期更改可能的异常对象和类型。 例如，将引发异常的类型为 x 后，公共语言运行时 (CLR) 可能内存不足的情况并将其升级到内存不足异常。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
