---
title: ICorProfilerObjectEnum 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum
helpviewer_keywords:
- ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 13e1651c-9523-40ef-bfd7-87fb94519f8b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e3478364a415b145bed879cda5cc5c41cf22254c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerobjectenum-interface"></a>ICorProfilerObjectEnum 接口
提供按顺序循环访问集合的冻结对象生成的方法[Ngen.exe （本机映像生成器）](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Clone 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-clone-method.md)|获取指向此 `ICorProfilerObjectEnum` 接口副本的接口指针。|  
|[GetCount 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-getcount-method.md)|获取集合中的已冻结对象总数。|  
|[Next 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-next-method.md)|获取指定的数目的连续对象从序列中枚举器的当前位置开始的对象的有序集合。|  
|[Reset 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-reset-method.md)|将此枚举器的光标移动到序列的起始位置。|  
|[Skip 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-skip-method.md)|因此，跳过指定的数量的元素，请从其当前位置前移此枚举器的光标。|  
  
## <a name="remarks"></a>备注  
 `ICorProfilerObjectEnum` 接口是一个枚举器。 它可以让数组接收器以其合适的速率从发送器提取元素。 换而言之，接收方是可以显式控制数组元素流，从而避免将大型数组作为方法参数传递到相关的问题。  
  
 使用[icorprofilerinfo2:: Enummodulefrozenobjects](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)用于获取指向`ICorProfilerObjectEnum`接口。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [EnumModuleFrozenObjects 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)
