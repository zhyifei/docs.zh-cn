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
ms.openlocfilehash: fce89cc2b3b0104ba017b7df9105dea3f6ec4e91
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868221"
---
# <a name="icorprofilerobjectenum-interface"></a>ICorProfilerObjectEnum 接口
提供按顺序循环访问[ngen.exe （本机映像生成器）](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)生成的冻结对象的集合的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Clone 方法](icorprofilerobjectenum-clone-method.md)|获取指向此 `ICorProfilerObjectEnum` 接口副本的接口指针。|  
|[GetCount 方法](icorprofilerobjectenum-getcount-method.md)|获取集合中冻结对象的总数。|  
|[Next 方法](icorprofilerobjectenum-next-method.md)|从对象的顺序集合中获取指定数目的连续对象，从该序列中的枚举器的当前位置开始。|  
|[Reset 方法](icorprofilerobjectenum-reset-method.md)|将此枚举器的光标移动到序列的起始位置。|  
|[Skip 方法](icorprofilerobjectenum-skip-method.md)|将此枚举器的光标从其当前位置前移，以便跳过指定数目的元素。|  
  
## <a name="remarks"></a>备注  
 `ICorProfilerObjectEnum` 接口是一个枚举器。 它可以让数组接收器以其合适的速率从发送器拉取元素。 换句话说，接收方能够显式控制数组元素的流，从而避免了将大型数组作为方法参数传递的相关问题。  
  
 使用[ICorProfilerInfo2：： EnumModuleFrozenObjects](icorprofilerinfo2-enummodulefrozenobjects-method.md)获取指向 `ICorProfilerObjectEnum` 接口的指针。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [Profiling 接口](profiling-interfaces.md)
- [EnumModuleFrozenObjects 方法](icorprofilerinfo2-enummodulefrozenobjects-method.md)
