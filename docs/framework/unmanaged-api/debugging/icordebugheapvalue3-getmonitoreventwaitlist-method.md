---
title: ICorDebugHeapValue3::GetMonitorEventWaitList 方法
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetMonitorEventWaitList
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList
helpviewer_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList method [.NET Framework debugging]
- GetMonitorEventWaitList method [.NET Framework debugging]
ms.assetid: 035a9035-ac66-4953-b48a-99652b42b7fe
topic_type:
- apiref
ms.openlocfilehash: 0fbff178efd4d0dff3593907b3d40e946be2ff6e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121294"
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a>ICorDebugHeapValue3::GetMonitorEventWaitList 方法
提供在与监视器锁关联的事件上排队的线程的排序列表。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
## <a name="parameters"></a>参数  
 `ppThreadEnum`  
 弄提供线程有序列表的 ICorDebugThreadEnum 枚举器。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该列表不为空。|  
|S_FALSE|列表为空。|  
  
## <a name="exceptions"></a>异常  
  
## <a name="remarks"></a>备注  
 列表中的第一个线程是下一次调用 <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>释放的第一个线程。 此列表中的下一个线程将在以下调用上释放，依此类推。  
  
 如果列表不为空，则此方法返回 S_OK。 如果列表为空，则该方法将返回 S_FALSE;在这种情况下，枚举仍有效，但它是空的。  
  
 在任一情况下，枚举接口仅在当前已同步状态的持续时间内可用。 但是，在线程退出之前，从它分配的线程的接口是有效的。  
  
 如果 `ppThreadEnum` 不是有效的指针，则结果是不确定的。  
  
 如果发生错误，导致无法确定线程（如果有）正在等待监视器的线程，则该方法将返回一个指示失败的 HRESULT。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
