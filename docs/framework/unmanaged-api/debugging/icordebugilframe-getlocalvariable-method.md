---
title: ICorDebugILFrame::GetLocalVariable 方法
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetLocalVariable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetLocalVariable
helpviewer_keywords:
- ICorDebugILFrame::GetLocalVariable method [.NET Framework debugging]
- GetLocalVariable method [.NET Framework debugging]
ms.assetid: c8706356-d50b-4f87-a40c-39c3b7f4fd38
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29fc1b491aa4e340c3d8ad6f761d0d6d901649ac
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758561"
---
# <a name="icordebugilframegetlocalvariable-method"></a>ICorDebugILFrame::GetLocalVariable 方法
此 Microsoft 中间语言 (MSIL) 堆栈帧中获取指定的本地变量的值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a>参数  
 `dwIndex`  
 [in]此 MSIL 堆栈帧中局部变量的索引。  
  
 `ppValue`  
 [out]指向表示检索到的值的 ICorDebugValue 对象的地址的指针。  
  
## <a name="remarks"></a>备注  
 `GetLocalVariable` MSIL 堆栈帧中或在实时 (JIT) 编译帧中，可以使用方法。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
