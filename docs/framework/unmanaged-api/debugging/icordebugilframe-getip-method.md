---
title: ICorDebugILFrame::GetIP 方法
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::GetIP method [.NET Framework debugging]
ms.assetid: 18217ba1-1776-4297-a3b9-f77e64b0fead
topic_type:
- apiref
ms.openlocfilehash: 3890cb4236f113bc6efc23bfb606d19a525ec234
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210262"
---
# <a name="icordebugilframegetip-method"></a>ICorDebugILFrame::GetIP 方法
获取指令指针的值和按位组合值，它描述如何获取指令指针的值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a>参数  
 `pnOffset`  
 弄指令指针的值。  
  
 `pMappingResult`  
 弄一个指针，指向 CorDebugMappingResult 枚举值的按位组合，这些枚举值描述如何获取指令指针的值。  
  
## <a name="remarks"></a>备注  
 指令指针的值是堆栈帧偏移函数的 Microsoft 中间语言（MSIL）代码的偏移量。 如果堆栈帧处于活动状态，则此地址为要执行的下一条指令。 如果堆栈帧不处于活动状态，则该地址是在重新激活堆栈帧时要执行的下一条指令。  
  
 如果此框架是实时（JIT）编译的帧，则会通过从实际的本机指令指针反向映射来确定指令指针的值，因此该值可能只是近似的。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
