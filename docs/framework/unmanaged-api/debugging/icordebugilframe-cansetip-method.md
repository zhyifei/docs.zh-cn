---
title: ICorDebugILFrame::CanSetIP 方法
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type:
- apiref
ms.openlocfilehash: 2bd4ab4a080461c56b0287d24aa288847445d803
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210314"
---
# <a name="icordebugilframecansetip-method"></a>ICorDebugILFrame::CanSetIP 方法
获取 HRESULT，它指示在 Microsoft 中间语言（MSIL）代码中将指令指针设置为指定的偏移位置是安全的。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a>参数  
 `nOffset`  
 中指令指针所需的设置。  
  
## <a name="remarks"></a>备注  
 在 `CanSetIP` 调用[ICorDebugILFrame：： SetIP](icordebugilframe-setip-method.md)方法之前，请使用方法。 如果 `CanSetIP` 返回除 S_OK 以外的任何 HRESULT，则仍可调用 `ICorDebugILFrame::SetIP` ，但是无法保证调试器将继续安全且正确地执行正在调试的代码。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl、Cordebug.idl、h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
