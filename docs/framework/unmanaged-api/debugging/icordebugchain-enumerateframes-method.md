---
title: ICorDebugChain::EnumerateFrames 方法
ms.date: 03/30/2017
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
ms.openlocfilehash: c8a62d8b4a4db0f36d991c32dbfc5bad68780f1b
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894697"
---
# <a name="icordebugchainenumerateframes-method"></a>ICorDebugChain::EnumerateFrames 方法
获取一个枚举数，该枚举数包含链中所有托管堆栈帧（从最新帧开始）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a>参数  
 `ppFrames`  
 弄指向 ICorDebugFrameEnum 对象地址的指针，该对象是堆栈帧的枚举器。  
  
## <a name="remarks"></a>备注  
 链表示线程的物理调用堆栈。  
  
 只`EnumerateFrames`应为托管链调用方法。 调试 API 不提供用于获取非托管链中包含的帧的方法。 调试器必须使用其他方法来获取此信息。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
