---
title: ICorDebugModule::GetClassFromToken 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetClassFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetClassFromToken
helpviewer_keywords:
- GetClassFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetClassFromToken method [.NET Framework debugging]
ms.assetid: 622a4d3c-0425-4c54-a7e4-0735377cdad2
topic_type:
- apiref
ms.openlocfilehash: f8a56dcf03748c6582bce07fc379113c5cdddd11
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212590"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a>ICorDebugModule::GetClassFromToken 方法
获取元数据标记指定的类。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a>参数  
 `typedef`  
 中`mdTypeDef`引用类的元数据的元数据标记。  
  
 `ppClass`  
 弄指向表示类的 ICorDebugClass 对象地址的指针。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
