---
title: ICorDebugModule::GetSize 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetSize method [.NET Framework debugging]
ms.assetid: 5c68375d-145d-46ef-a7c8-2dc4257472de
topic_type:
- apiref
ms.openlocfilehash: 4f9818137016dc3e0522ed516c52df2550ffdfca
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212511"
---
# <a name="icordebugmodulegetsize-method"></a>ICorDebugModule::GetSize 方法
获取模块的大小（以字节为单位）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetSize(  
    [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a>参数  
 `pcBytes`  
 弄模块的大小（以字节为单位）。  
  
 如果该模块是通过本机映像生成器（Ngen.exe）生成的，则该模块的大小将为零。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
