---
title: ICorDebugFunction2::GetVersionNumber 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fdd2151c4886959647de4f9e27a20a93ffc07429
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420048"
---
# <a name="icordebugfunction2getversionnumber-method"></a>ICorDebugFunction2::GetVersionNumber 方法
获取此函数的编辑并继续版本。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pnVersion`  
 [out]指向一个整数，表示此 ICorDebugFunction2 对象表示的函数的版本号的指针。  
  
## <a name="remarks"></a>备注  
 运行时将跟踪的调试会话期间对每个模块所进行的编辑数。 函数的版本号是以上引入了函数的编辑次数。 函数的原始版本是版本 1。 该数字递增模块每次[icordebugmodule2:: Applychanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)称为该模块。 因此，如果在第一个和第三个调用替换为函数的正文`ICorDebugModule2::ApplyChanges`，`GetVersionNumber`可能会返回版本 1、 2 或 4 该函数，但不是版本 3。 （该函数将有没有版本 3。）  
  
 为每个模块单独跟踪的版本号。 因此，如果上模块 1 和无模块 2 上执行四个编辑时，模块 1 你下一次编辑将的模块 1 中的所有编辑函数分配的版本号为 6。 如果相同编辑改动模块 2，模块 2 中的函数将获得的版本号为 2。  
  
 通过获取的版本号`GetVersionNumber`方法可能会低于获取通过[icordebugfunction:: Getcurrentversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)。  
  
 [Icordebugcode:: Getversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)方法执行相同的操作`ICorDebugFunction2::GetVersionNumber`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
