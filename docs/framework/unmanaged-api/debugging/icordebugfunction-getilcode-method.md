---
title: "ICorDebugFunction::GetILCode 方法"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ba960246c5aa1057df517d776819817d777402f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunctiongetilcode-method"></a>ICorDebugFunction::GetILCode 方法
获取表示与此 ICorDebugFunction 对象关联的 Microsoft 中间语言 (MSIL) 代码的 ICorDebugCode 实例。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppCode`  
 [out]指向的指针`ICorDebugCode`实例，则为 null，如果函数不编译为 MSIL。  
  
## <a name="remarks"></a>备注  
 如果编辑并继续对该函数，允许有`GetILCode`方法将获取与此函数的公共语言运行时 (CLR) 中的代码编辑版本对应的 MSIL 代码。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
