---
title: ICorProfilerInfo::GetObjectSize 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetObjectSize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetObjectSize
helpviewer_keywords:
- GetObjectSize method [.NET Framework profiling]
- ICorProfilerInfo::GetObjectSize method [.NET Framework profiling]
ms.assetid: 9f02e763-73f7-42cb-a41c-f78499d9482c
topic_type:
- apiref
ms.openlocfilehash: b860cf6eb07c3f063e3e51514f8492cf4af9e8ed
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869667"
---
# <a name="icorprofilerinfogetobjectsize-method"></a>ICorProfilerInfo::GetObjectSize 方法
获取指定对象的大小。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a>参数  
 `objectId`  
 中对象的 ID。  
  
 `pcSize`  
 弄一个指针，指向对象的大小（以字节为单位）。  
  
## <a name="remarks"></a>备注  
  
> [!IMPORTANT]
> 此方法已过时。 它在64位平台上为大于4GB 的对象返回 COR_E_OVERFLOW。 改为使用[ICorProfilerInfo4：： GetObjectSize2](icorprofilerinfo4-getobjectsize2-method.md)方法。  
  
 相同类型的不同对象通常具有相同的大小。 但是，某些类型（例如数组或字符串）对于每个对象可能有不同的大小。  
  
 `GetObjectSize` 方法返回的大小不包括对象在垃圾回收堆上时可能出现的任何对齐填充。 如果使用 `GetObjectSize` 方法从对象到垃圾回收堆上的对象前进，请根据需要手动添加对齐填充。  
  
- 在32位 Windows 上，COR_PRF_GC_GEN_0、COR_PRF_GC_GEN_1 和 COR_PRF_GC_GEN_2 使用4字节对齐，COR_PRF_GC_LARGE_OBJECT_HEAP 使用8字节对齐。  
  
- 在64位 Windows 上，对齐始终为8个字节。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo 接口](icorprofilerinfo-interface.md)
