---
title: ICorProfilerFunctionControl 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl
helpviewer_keywords:
- ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 4e3d3141-4662-4166-8f05-bc857c1b4216
topic_type:
- apiref
ms.openlocfilehash: 1286ce953c96eb3e3164ba5b209031dd1ec5c453
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864688"
---
# <a name="icorprofilerfunctioncontrol-interface"></a>ICorProfilerFunctionControl 接口
提供允许代码探查器与公共语言运行时 (CLR) 进行通信的方法，从而在重新编译特定方法时控制 JIT 探查器应生成代码的方式。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[SetCodegenFlags 方法](icorprofilerfunctioncontrol-setcodegenflags-method.md)|设置[COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md)枚举中的一个或多个标志，以控制实时（JIT）重新编译函数的代码生成。|  
|[SetILFunctionBody 方法](icorprofilerfunctioncontrol-setilfunctionbody-method.md)|替换方法的公共中间语言 (CIL) 主体。|  
|[SetILInstrumentedCodeMap 方法](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|使用指定的公共中间语言 (CIL) 映射项为指定的函数设置代码图。|  
  
## <a name="remarks"></a>备注  
 `ICorProfilerFunctionControl` 接口提供了用于控制单个重新编译函数的代码生成的方法。 探查器通过[ICorProfilerCallback4：： GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md)回调获取此接口的实例。 `ICorProfilerFunctionControl` 的每个实例都可控制一个函数的所有实例。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo4 接口](icorprofilerinfo4-interface.md)
- [Profiling 接口](profiling-interfaces.md)
- [EnumJITedFunctions2 方法](icorprofilerinfo4-enumjitedfunctions2-method.md)
