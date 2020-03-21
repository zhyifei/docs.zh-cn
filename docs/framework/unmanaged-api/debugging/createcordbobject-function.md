---
title: CreateCordbObject 函数
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
ms.openlocfilehash: 2716adcc8c79c8003202561ea2011c2469a6bc5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179236"
---
# <a name="createcordbobject-function"></a>CreateCordbObject 函数
创建调试器接口 （[ICorDebug](icordebug-interface.md)）， 提供在远程进程上实例化托管调试会话的功能。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a>parameters  
 `iDebuggerVersion`  
 [in] 目标进程的调试器版本。 此参数必须为 CorDebugVersion_2_0 以用于远程调试。  
  
 `ppCordb`  
 [出]指向将强制转换为[ICorDebug](icordebug-interface.md)接口并返回的对象的指针。  
  
## <a name="return-value"></a>返回值  
 S_OK  
 已成功确定该进程中的 CLR 的数目，并已正确填写相应的句柄数组和路径数组。  
  
 E_INVALIDARG  
 `ppCordb` 为 null，或 `iDebuggerVersion` 不是 CorDebugVersion_2_0。  
  
 E_OUTOFMEMORY  
 无法为 `ppCordb` 分配足够的内存  
  
 E_FAIL（或其他 E_ 返回代码）  
 其他故障。  
  
## <a name="remarks"></a>备注  
 返回的`ppCordb` [ICorDebug](icordebug-interface.md)接口是所有托管调试服务的顶级调试接口。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 核心Clr远程调试接口.h  
  
 **资料库：** mscordbi_macx86.dll  
  
 **.NET 框架版本：** 3.5 SP1
