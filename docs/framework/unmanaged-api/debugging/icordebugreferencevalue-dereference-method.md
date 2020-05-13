---
title: ICorDebugReferenceValue::Dereference 方法
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.Dereference
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type:
- apiref
ms.openlocfilehash: 7c64823e1a5c519eb74b508af093afeb1132e608
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210080"
---
# <a name="icordebugreferencevaluedereference-method"></a>ICorDebugReferenceValue::Dereference 方法
获取所引用的对象。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a>参数  
 `ppValue`  
 弄一个指针，指向表示此 ICorDebugReferenceValue 对象指向的对象的 ICorDebugValue 的地址。  
  
## <a name="remarks"></a>备注  
 此 `ICorDebugValue` 对象仅在其引用尚未禁用时有效。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
