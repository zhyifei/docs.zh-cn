---
title: ICorProfilerThreadEnum 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum
helpviewer_keywords:
- ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: 1e35031b-e095-4c14-9644-8deeb3081e0b
topic_type:
- apiref
ms.openlocfilehash: b9fb308f19ff09218c97b030296b9a3d4f0f2512
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868182"
---
# <a name="icorprofilerthreadenum-interface"></a>ICorProfilerThreadEnum 接口
提供方法以按顺序循环访问公共语言运行时中的线程集合。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Clone 方法](icorprofilerthreadenum-clone-method.md)|获取指向此 `ICorProfilerThreadEnum` 接口副本的接口指针。|  
|[GetCount 方法](icorprofilerthreadenum-getcount-method.md)|获取应用程序使用的线程数。|  
|[Next 方法](icorprofilerthreadenum-next-method.md)|从线程的序列集合获取指定的连续线程数，从序列中枚举器的当前位置开始。|  
|[Reset 方法](icorprofilerthreadenum-reset-method.md)|将枚举器的光标移动到序列的起始位置。|  
|[Skip 方法](icorprofilerthreadenum-skip-method.md)|从当前位置前移枚举器的光标，以便跳过指定的元素数量。|  
  
## <a name="remarks"></a>备注  
 `ICorProfilerThreadEnum` 接口是一个枚举器。 它可以让数组接收器以其合适的速率从发送器拉取元素。 换而言之，接收器可以显式控制数组元素流，从而避免将大型数组作为方法形参传递方面的相关问题。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo 接口](icorprofilerinfo-interface.md)
- [Profiling 接口](profiling-interfaces.md)
