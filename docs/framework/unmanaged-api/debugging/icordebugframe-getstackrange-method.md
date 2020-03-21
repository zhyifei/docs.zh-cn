---
title: ICorDebugFrame::GetStackRange 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 7a35ce025360e0ec8b7085d68e54548026b7c7fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178901"
---
# <a name="icordebugframegetstackrange-method"></a>ICorDebugFrame::GetStackRange 方法
获取此堆栈帧的绝对地址范围。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>parameters  
 `pStart`  
 [出]指向`CORDB_ADDRESS`指定此`ICorDebugFrame`对象表示的堆栈帧的起始地址的指针。  
  
 `pEnd`  
 [出]指向`CORDB_ADDRESS`指定此`ICorDebugFrame`对象表示的堆栈帧的结束地址的指针。  
  
## <a name="remarks"></a>备注  
 堆栈的地址范围可用于拼凑从多个调试引擎收集的交错堆栈跟踪。 数值范围不提供有关堆栈帧内容的信息。 它仅对堆栈帧位置的比较有意义。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
