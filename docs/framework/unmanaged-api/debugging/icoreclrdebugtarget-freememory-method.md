---
title: ICoreClrDebugTarget::FreeMemory 方法
ms.date: 03/30/2017
api_name:
- ICoreDebugTarget.FreeMemory
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::FreeMemory
helpviewer_keywords:
- remote debugging API [Silverlight]
- FreeMemory method, ICoreClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::FreeMemory method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 98f2a0db-a6ec-4f9b-861d-f82485237d08
topic_type:
- apiref
ms.openlocfilehash: cfa313d286d0decad82f51bcedc582470549c8e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790776"
---
# <a name="icoreclrdebugtargetfreememory-method"></a>ICoreClrDebugTarget::FreeMemory 方法
释放由[ICoreClrDebugTarget：： EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md)和[ICoreClrDebugTarget：： EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md)方法分配的内存。  
  
## <a name="syntax"></a>语法  
  
```cpp  
void FreeMemory (  
     [in] void*pMemory);  
```  
  
## <a name="parameters"></a>参数  
 `pMemory`  
 中指向由[ICoreClrDebugTarget：： EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md)或[ICoreClrDebugTarget：： EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md)方法返回的数组的指针。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CoreClrRemoteDebuggingInterfaces  
  
 **库：** mscordbi_macx86  
  
 **.NET Framework 版本：** 3.5 SP1  
  
## <a name="see-also"></a>另请参阅

- [ICoreClrDebugTarget 接口](icoreclrdebugtarget-interface.md)
