---
title: ICorDebugEval::GetResult 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetResult
helpviewer_keywords:
- ICorDebugEval::GetResult method [.NET Framework debugging]
- GetResult method [.NET Framework debugging]
ms.assetid: 50dbb9af-58a1-41f4-b56d-3da20011884f
topic_type:
- apiref
ms.openlocfilehash: 52bfe669d3b078657916554255a11cecfc07d484
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085089"
---
# <a name="icordebugevalgetresult-method"></a>ICorDebugEval::GetResult 方法
获取此计算的结果。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
## <a name="parameters"></a>参数  
 `ppResult`  
 弄一个指针，指向表示此计算结果的 ICorDebugValue 对象的地址（如果计算正常完成）。  
  
## <a name="remarks"></a>备注  
 只有完成计算后，`GetResult` 方法才有效。  
  
 如果计算正常完成，`ppResult` 将指定结果。 如果终止时出现异常，则结果为引发的异常。 如果计算为新的对象，则结果是对新的对象的引用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
