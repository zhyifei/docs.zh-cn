---
title: ICorDebugChain::GetCallee 方法
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79743b78ea3d19bab4756b580d2feddd07e0a23b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744981"
---
# <a name="icordebugchaingetcallee-method"></a>ICorDebugChain::GetCallee 方法
获取此链调用链。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a>参数  
 `ppChain`  
 [out]指向一个 ICorDebugChain 对象，表示被调用的链的地址的指针。 如果当前正在执行此链，（即，如果此证书链不等待被调用链返回），`ppChain`将为 null。  
  
## <a name="remarks"></a>备注  
 此链将等待被调用链返回，然后再继续执行。 调用的链可能对于跨线程封送调用另一个线程上。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
