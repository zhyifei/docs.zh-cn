---
title: ICorDebugMutableDataTarget::ContinueStatusChanged 方法
ms.date: 03/30/2017
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
ms.openlocfilehash: 49f517c0c09771ce86e43b801f6d7fce695d907a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213304"
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a>ICorDebugMutableDataTarget::ContinueStatusChanged 方法
更改指定线程上未完成的调试事件的延续状态。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
## <a name="parameters"></a>参数  
 `dwThreadId`  
 由操作系统定义的线程标识符。  
  
 `continueStatus`  
 表示新请求的延续状态的 [COREDB_CONTINUE_STATUS](../common-data-types-unmanaged-api-reference.md) 值。  
  
## <a name="remarks"></a>备注  
 当调试器调用需要以不同于通常处理方式的方式处理当前的调试事件的 ICorDebug 方法时，该调试器将调用 `ContinueStatusChanged` 方法。 例如，如果存在未处理异常，并且调试器请求会取消此异常的操作（例如 [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) 或 `FuncEval`），则此 API 将用于请求取消此异常。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugMutableDataTarget 接口](icordebugmutabledatatarget-interface.md)
- [调试接口](debugging-interfaces.md)
