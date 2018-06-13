---
title: ICorDebugThread2::GetActiveFunctions 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetActiveFunctions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetActiveFunctions
helpviewer_keywords:
- GetActiveFunctions method [.NET Framework debugging]
- ICorDebugThread2::GetActiveFunctions method [.NET Framework debugging]
ms.assetid: 27fae01a-ecec-423a-973e-24f8de55826c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7ed7787f0302826cab67664780177f05e551199
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421101"
---
# <a name="icordebugthread2getactivefunctions-method"></a>ICorDebugThread2::GetActiveFunctions 方法
每个此线程的帧中获取有关活动函数的信息。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cFunctions`  
 [in] `pFunctions` 数组的大小。  
  
 `pcFunctions`  
 [out]指向的对象中返回数的指针`pFunctions`数组。 返回的对象数将减至的堆栈上的托管帧的数目。  
  
 `pFunctions`  
 [在中，out]COR_ACTIVE_FUNCTION 对象数组，其中每个包含有关中此线程的帧的活动函数的信息。  
  
 第一个元素将用于叶帧和等回堆栈的根。  
  
## <a name="remarks"></a>备注  
 如果`pFunctions`的输入，为 null`GetActiveFunctions`返回仅位于堆栈上的函数的数量。 也就是说，如果`pFunctions`的输入，为 null`GetActiveFunctions`返回一个值仅在`pcFunctions`。  
  
 `GetActiveFunctions`方法旨在作为一种优化通过从堆栈跟踪中的帧中获取相同的信息，包括，则必须 ICorDebugILFrame 对象为其在完整的堆栈跟踪中的帧。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
