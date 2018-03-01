---
title: "ICorDebugProcess2::GetReferenceValueFromGCHandle 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0ac4cc32be6914ea858d32b8699a695588f0a1e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a>ICorDebugProcess2::GetReferenceValueFromGCHandle 方法
获取指定的托管对象具有垃圾回收句柄引用指针。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
#### <a name="parameters"></a>参数  
 `handle`  
 [in]指向具有垃圾回收句柄的托管对象的指针。 此值是<xref:System.IntPtr>对象，并可以从检索<xref:System.Runtime.InteropServices.GCHandle>托管对象。  
  
 `pOutValue`  
 [out]指向一个 ICorDebugReferenceValue 对象，表示对指定的托管对象的引用的地址的指针。  
  
## <a name="remarks"></a>备注  
 不要混淆的返回的引用值与垃圾回收引用值。  
  
 返回的引用的行为类似于普通的引用。 禁用断点后继续执行代码时。 目标对象的生存期不会影响受生存期的引用值。  
  
> [!NOTE]
>  `GetReferenceValueFromGCHandle`方法不会验证该句柄。 因此，`GetReferenceValueFromGCHandle`方法可能会损坏调试器并传递一个无效的句柄如果正在调试的代码。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
