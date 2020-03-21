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
ms.openlocfilehash: f30516a8f59b90de9b4c052d92a8c88575ace3c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178826"
---
# <a name="icordebugilframegetip-method"></a>ICorDebugILFrame::GetIP 方法
获取指令指针的值和描述指令指针值的位组合值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a>parameters  
 `pnOffset`  
 [出]指令指针的值。  
  
 `pMappingResult`  
 [出]指向 CorDebugMappingResult 枚举值的位状组合的指针，用于描述如何获取指令指针的值。  
  
## <a name="remarks"></a>备注  
 指令指针的值是堆栈帧的偏移量到函数的 Microsoft 中间语言 （MSIL） 代码中。 如果堆栈帧处于活动状态，则此地址是执行的下一个指令。 如果堆栈帧未处于活动状态，则此地址是重新激活堆栈帧时执行的下一个指令。  
  
 如果此帧是实时 （JIT） 编译帧，则指令指针的值将通过从实际本机指令指针向后映射来确定，因此该值可能仅是近似值。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
