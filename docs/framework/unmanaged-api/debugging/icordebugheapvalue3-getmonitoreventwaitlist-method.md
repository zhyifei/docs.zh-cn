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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a395579892ff2410865a4fcdd19cf20449b82b88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421066"
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a>ICorDebugHeapValue3::GetMonitorEventWaitList 方法
提供有关与监视器锁关联的事件将排队等待的线程的已排序的列表。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppThreadEnum`  
 [out]ICorDebugThreadEnum 枚举器提供的线程的已排序的列表。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|该列表不为空。|  
|S_FALSE|列表为空。|  
  
## <a name="exceptions"></a>异常  
  
## <a name="remarks"></a>备注  
 在列表中的第一个线程是发布到的下一个调用的第一个线程<xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>。 在列表中的下一个线程释放以下调用，依次类推。  
  
 如果列表不为空，则此方法返回，则为 S_OK。 如果列表为空，该方法返回 S_FALSE;在这种情况下，枚举是仍然有效，但它是空。  
  
 在任一情况下，枚举接口可以仅为当前的同步状态的持续时间是可用。 但是，从其分配的线程的接口都有效，直到线程退出。  
  
 如果`ppThreadEnum`不是有效的指针，结果不可确定。  
  
 出错时，无法确定哪些，如果有的话，线程在等待监视器，该方法将返回一个 HRESULT，指示失败。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
