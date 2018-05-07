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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd421d705a96778159cb80ad92d9ac654e88985f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugilframegetip-method"></a>ICorDebugILFrame::GetIP 方法
获取指令指针的值和一个描述如何获取指令指针的值的按位组合值。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pnOffset`  
 [out]指令指针的值。  
  
 `pMappingResult`  
 [out]指向 CorDebugMappingResult 枚举值，用于描述如何获取指令指针的值的按位组合的指针。  
  
## <a name="remarks"></a>备注  
 指令指针的值是到函数的 Microsoft 中间语言 (MSIL) 代码的堆栈帧的偏移量。 如果堆栈帧处于活动状态，则此地址是要执行的下一步指令。 如果堆栈帧不处于活动状态，此地址是在堆栈帧重新激活时执行的下一个指令。  
  
 如果此帧中实时 (JIT) 编译的帧，则将通过向后将映射从实际的本机指令指针，因此该值可能只是近似确定指令指针的值。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
