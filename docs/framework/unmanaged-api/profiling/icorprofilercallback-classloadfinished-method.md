---
title: ICorProfilerCallback::ClassLoadFinished 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadFinished
helpviewer_keywords:
- ClassLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ClassLoadFinished method [.NET Framework profiling]
ms.assetid: 3dd80fbe-d62d-4d4d-acf8-5b7d0efe607e
topic_type:
- apiref
ms.openlocfilehash: e0ff90f99c1127b5a4626f47514ba7099b5d48af
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866593"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a>ICorProfilerCallback::ClassLoadFinished 方法
通知探查器类已经完成加载。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a>参数

- `classId`

  \[中的] 标识已加载的类。

- `hrStatus`

  \[中的] 表示是否已成功加载类的 HRESULT。

## <a name="remarks"></a>备注  
 在调用 `ClassLoadFinished` 方法之前，`classId` 的值对信息请求无效。  
  
 在 `ClassLoadFinished` 回调后，加载类的某些部分可能会继续。 如果 `hrStatus` 失败，则指示失败。 不过，`hrStatus` 中的 HRESULT 成功仅指示加载类的第一部分已成功。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerCallback 接口](icorprofilercallback-interface.md)
- [ClassLoadStarted 方法](icorprofilercallback-classloadstarted-method.md)
