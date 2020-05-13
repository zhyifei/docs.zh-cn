---
title: ICorDebugProcess::ThreadForFiberCookie 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ThreadForFiberCookie
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ThreadForFiberCookie
helpviewer_keywords:
- ICorDebugProcess::ThreadForFiberCookie method [.NET Framework debugging]
- ThreadForFiberCookie method [.NET Framework debugging]
ms.assetid: afe4e97f-bffc-47e1-adad-d6e842487f35
topic_type:
- apiref
ms.openlocfilehash: faaa118fa73a4c9b8750752d84a9dd980170ff66
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210444"
---
# <a name="icordebugprocessthreadforfibercookie-method"></a>ICorDebugProcess::ThreadForFiberCookie 方法
未实现此方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ThreadForFiberCookie (  
    [in] DWORD fiberCookie,  
    [out] ICorDebugThread **ppThread  
);  
```  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
