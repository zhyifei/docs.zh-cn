---
title: ICorDebugProcess2::GetReferenceValueFromGCHandle 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21da325ee58df65ac449464f8292f2ba94d99338
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943298"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a>ICorDebugProcess2::GetReferenceValueFromGCHandle 方法
获取指向具有垃圾回收句柄的指定托管对象的引用指针。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a>参数  
 `handle`  
 中指向具有垃圾回收句柄的托管对象的指针。 此值是一个<xref:System.IntPtr>对象, 可以从托管对象的<xref:System.Runtime.InteropServices.GCHandle>检索。  
  
 `pOutValue`  
 弄指向 ICorDebugReferenceValue 对象的地址的指针, 该对象表示对指定托管对象的引用。  
  
## <a name="remarks"></a>备注  
 不要将返回的引用值与垃圾回收引用值混淆。  
  
 返回的引用的行为与常规引用相同。 当代码在断点后面继续执行时, 它会被禁用。 目标对象的生存期不受引用值的生存期的影响。  
  
> [!NOTE]
> `GetReferenceValueFromGCHandle`方法不会验证句柄。 因此, 如果`GetReferenceValueFromGCHandle`传递的句柄无效, 则该方法可能会损坏调试器和正在调试的代码。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl, Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
