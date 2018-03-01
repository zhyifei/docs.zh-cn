---
title: "ICorDebugFrame::GetStackRange 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3c4c9c0a531d93ca2c7c72f50bcd2f7ee98887e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugframegetstackrange-method"></a>ICorDebugFrame::GetStackRange 方法
获取此堆栈帧的绝对地址范围。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pStart`  
 [out]指向的指针`CORDB_ADDRESS`，指定表示此堆栈帧的起始地址`ICorDebugFrame`对象。  
  
 `pEnd`  
 [out]指向的指针`CORDB_ADDRESS`，指定表示此堆栈帧的结束地址`ICorDebugFrame`对象。  
  
## <a name="remarks"></a>备注  
 堆栈的地址范围可用于从多个调试引擎中收集的交错的堆栈跟踪进行汇总。 数值范围提供有关内容的堆栈帧的任何信息。 它是仅对比较的堆栈帧位置有意义。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
