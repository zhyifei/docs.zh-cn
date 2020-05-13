---
title: ICorDebugProcess2::GetDesiredNGENCompilerFlags 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags method [.NET Framework debugging]
- GetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: fc834580-3a90-4315-95d2-349b6bb7d059
topic_type:
- apiref
ms.openlocfilehash: d2e54f0b16300673409eb2f5757338dfa3011e61
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212992"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a>ICorDebugProcess2::GetDesiredNGENCompilerFlags 方法
获取当前编译器标志设置，公共语言运行时（CLR）使用这些设置来选择要加载到此进程中的正确预编译（即本机）映像。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a>参数  
 `pdwFlags`  
 弄指向[CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md)枚举值的按位组合的指针，这些值用于选择要加载的正确预编译映像。  
  
## <a name="remarks"></a>备注  
 使用[ICorDebugProcess2：： SetDesiredNGENCompilerFlags](icordebugprocess2-setdesiredngencompilerflags-method.md)方法设置 CLR 将用于选择要加载的正确预编译图像的标志。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
