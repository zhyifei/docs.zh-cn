---
title: ICorDebugHeapValue3::GetThreadOwningMonitorLock 方法
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetThreadOwningMonitorLock
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetThreadOwningMonitorLock
helpviewer_keywords:
- GetThreadOwningMonitorLock method [.NET Framework debugging]
- ICorDebugHeapValue3::GetThreadOwningMonitorLock method [.NET Framework debugging]
ms.assetid: e06fc19d-2cf4-4cad-81a3-137a68af8969
topic_type:
- apiref
ms.openlocfilehash: 8be7c0e32f6183deb354d8b3936ef55c2520fe9f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788619"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a>ICorDebugHeapValue3::GetThreadOwningMonitorLock 方法
返回拥有此对象的监视器锁的托管线程。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a>参数  
 `ppThread`  
 弄拥有此对象的监视器锁的托管线程。  
  
 `pAcquisitionCount`  
 弄此线程在返回为无所有者之前必须释放该锁的次数。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该方法成功完成。|  
|S_FALSE|没有托管线程拥有此对象的监视器锁。|  
  
## <a name="exceptions"></a>异常  
  
## <a name="remarks"></a>备注  
 如果托管线程拥有此对象的监视器锁：  
  
- 方法返回 S_OK。  
  
- 线程对象在线程退出之前有效。  
  
 如果没有托管线程拥有此对象的监视器锁，`ppThread` 和 `pAcquisitionCount` 会保持不变，并且该方法返回 S_FALSE。  
  
 如果 `ppThread` 或 `pAcquisitionCount` 不是有效的指针，则结果是不确定的。  
  
 如果发生错误，因此无法确定线程（如果有）线程拥有此对象的监视器锁，则方法将返回指示失败的 HRESULT。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
- [调试](index.md)
