---
title: ICorDebugAppDomain4::GetObjectForCCW 方法
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9eeb0b80ba691d813e3193f7ae746129c6725e1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506532"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a>ICorDebugAppDomain4::GetObjectForCCW 方法
从 COM 可调用包装器 (CCW) 指针获取托管对象。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ccwPointer`  
 [in] COM 可调用包装器 (CCW) 指针。  
  
 `ppManagedObject`  
 [out]指向表示给定 CCW 指针相对应的托管的对象的"ICorDebugValue"对象的地址的指针。  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>请参阅
- [ICorDebugAppDomain4 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
