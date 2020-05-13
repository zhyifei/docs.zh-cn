---
title: ICorDebugFunction::GetILCode 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetILCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type:
- apiref
ms.openlocfilehash: 8c7be2d48a30a9f649c6d86e4edbc10085195b68
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213616"
---
# <a name="icordebugfunctiongetilcode-method"></a>ICorDebugFunction::GetILCode 方法
获取表示与此 ICorDebugFunction 对象关联的 Microsoft 中间语言（MSIL）代码的 ICorDebugCode 实例。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>参数  
 `ppCode`  
 弄指向实例的指针 `ICorDebugCode` ，如果该函数未编译为 MSIL，则为 null。  
  
## <a name="remarks"></a>备注  
 如果此函数允许使用 "编辑并继续"，则该 `GetILCode` 方法将在公共语言运行时（CLR）中获取与此函数的编辑版本代码相对应的 MSIL 代码。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
