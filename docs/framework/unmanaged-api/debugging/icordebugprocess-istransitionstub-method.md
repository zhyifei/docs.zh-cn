---
title: ICorDebugProcess::IsTransitionStub 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsTransitionStub
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type:
- apiref
ms.openlocfilehash: 852c77be0dc8ef91933bacbbd3d6b3f5a69ae8c8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139386"
---
# <a name="icordebugprocessistransitionstub-method"></a>ICorDebugProcess::IsTransitionStub 方法
获取一个值，该值指示地址是否在将导致转换到托管代码的存根内。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a>参数  
 `address`  
 中一个 `CORDB_ADDRESS` 值，该值指定相关的地址。  
  
 `pbTransitionStub`  
 弄一个指向布尔值的指针，如果指定的地址在将导致转换到托管代码的存根（stub）内，则为 `true`;否则为 `false``pbTransitionStub`。  
  
## <a name="remarks"></a>备注  
 非托管的单步执行代码可以使用 `IsTransitionStub` 方法来确定何时将单步执行控件返回给托管分档器。  
  
 还可以通过查看可移植可执行（PE）文件中的信息来标识转换存根。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
