---
title: ICorDebugNativeFrame::GetIP 方法
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
ms.openlocfilehash: 53576ca938074fb7e5974a96bb53a84cb6ed67ab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213590"
---
# <a name="icordebugnativeframegetip-method"></a>ICorDebugNativeFrame::GetIP 方法
获取指令指针当前所设置到的本机代码偏移位置。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a>参数  
 `pnOffset`  
 弄指向本机代码中的偏移位置的指针。  
  
## <a name="remarks"></a>备注  
 如果此 "ICorDebugNativeFrame" 表示的堆栈帧处于活动状态，则偏移量是要执行的下一条指令的地址。 如果此堆栈帧不处于活动状态，则偏移量是在重新激活堆栈帧时要执行的下一条指令的地址。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅
