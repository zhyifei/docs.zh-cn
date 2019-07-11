---
title: ICorDebugChain::GetStackRange 方法
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a6db1990df2ed6b29d548c147ed40b5bc98254d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745693"
---
# <a name="icordebugchaingetstackrange-method"></a>ICorDebugChain::GetStackRange 方法
获取此链堆栈段的地址范围。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>参数  
 `pStart`  
 [out]一个指向`CORDB_ADDRESS`堆栈段的起始地址的值。  
  
 `pEnd`  
 [out]一个指向`CORDB_ADDRESS`是堆栈段的结束地址的值。  
  
## <a name="remarks"></a>备注  
 数值范围是仅对的堆栈帧位置比较有意义。 不能进行任何假设实际存储在堆栈上的内容。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
