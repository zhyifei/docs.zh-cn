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
ms.openlocfilehash: e064a7db131a671adc4d0b6df522f3456e3a31d5
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377157"
---
# <a name="icordebugthread2getactivefunctions-method"></a>ICorDebugThread2::GetActiveFunctions 方法
获取有关此线程的每个帧中的活动函数的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
## <a name="parameters"></a>参数  
 `cFunctions`  
 [in] `pFunctions` 数组的大小。  
  
 `pcFunctions`  
 弄一个指针，它指向数组中返回的对象的数目 `pFunctions` 。 返回的对象数将等于堆栈上托管帧的数目。  
  
 `pFunctions`  
 [in，out]COR_ACTIVE_FUNCTION 对象的数组，其中每个对象都包含有关此线程的帧中的活动函数的信息。  
  
 第一个元素将用于叶帧，并回到堆栈的根目录。  
  
## <a name="remarks"></a>备注  
 如果 `pFunctions` 在输入时为 null，则 `GetActiveFunctions` 仅返回堆栈上的函数数目。 也就是说，如果在 `pFunctions` 输入时为 null，则 `GetActiveFunctions` 仅返回中的值 `pcFunctions` 。  
  
 `GetActiveFunctions`方法旨在优化堆栈跟踪中的帧获取相同的信息，并且仅包含在完整堆栈跟踪中具有 ICorDebugILFrame 对象的帧。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
