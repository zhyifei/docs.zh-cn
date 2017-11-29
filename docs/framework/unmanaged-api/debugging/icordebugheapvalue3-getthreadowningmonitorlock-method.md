---
title: "ICorDebugHeapValue3::GetThreadOwningMonitorLock 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapValue3.GetThreadOwningMonitorLock
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapValue3::GetThreadOwningMonitorLock
helpviewer_keywords:
- GetThreadOwningMonitorLock method [.NET Framework debugging]
- ICorDebugHeapValue3::GetThreadOwningMonitorLock method [.NET Framework debugging]
ms.assetid: e06fc19d-2cf4-4cad-81a3-137a68af8969
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3571f546f71515a980c5415e568ae85eb0863d42
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a>ICorDebugHeapValue3::GetThreadOwningMonitorLock 方法
返回拥有此对象的监视器锁的托管的线程。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppThread`  
 [out]拥有此对象的监视器锁的托管的线程。  
  
 `pAcquisitionCount`  
 [out]此线程将不得不之前它将返回给正在没有所有者释放锁的次数。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法已成功完成。|  
|S_FALSE|没有托管的线程拥有对此对象的监视器锁。|  
  
## <a name="exceptions"></a>异常  
  
## <a name="remarks"></a>备注  
 如果托管的线程拥有对此对象的监视器锁：  
  
-   该方法返回，则为 S_OK。  
  
-   使线程对象在线程退出才有效。  
  
 如果没有托管的线程拥有对此对象的监视器锁`ppThread`和`pAcquisitionCount`不变，并且该方法返回 S_FALSE。  
  
 如果`ppThread`或`pAcquisitionCount`不是有效的指针，结果不可确定。  
  
 出错时，无法确定哪些，如果有的话，线程拥有对此对象的监视器锁该方法将返回一个 HRESULT，指示失败。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
