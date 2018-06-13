---
title: ICorProfilerModuleEnum::GetCount 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::GetCount
helpviewer_keywords:
- ICorProfilerModuleEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: f0a4a5e0-4689-474b-b0f4-37ca0639c918
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91572887713216f94707e5d21e5767f4cc54e0d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456253"
---
# <a name="icorprofilermoduleenumgetcount-method"></a>ICorProfilerModuleEnum::GetCount 方法
获取已加载到应用程序的托管模块数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
#### <a name="parameters"></a>参数  
 `celt`  
 [out]集合中的运行时模块数。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerModuleEnum 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
