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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 721ee27522b316a561e2f64a322c225cb85a44c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992168"
---
# <a name="icorprofilerfunctioncontrol-interface"></a>ICorProfilerFunctionControl 接口
提供允许代码探查器与公共语言运行时 (CLR) 进行通信的方法，从而在重新编译特定方法时控制 JIT 探查器应生成代码的方式。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[SetCodegenFlags 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)|设置从一个或多个标志[COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md)枚举来控制代码生成的在实时 (JIT) 重新编译函数。|  
|[SetILFunctionBody 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilfunctionbody-method.md)|替换方法的公共中间语言 (CIL) 主体。|  
|[SetILInstrumentedCodeMap 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|使用指定的公共中间语言 (CIL) 映射项为指定的函数设置代码图。|  
  
## <a name="remarks"></a>备注  
 `ICorProfilerFunctionControl` 接口提供了用于控制单个重新编译函数的代码生成的方法。 探查器获取通过此接口的实例[ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)回调。 `ICorProfilerFunctionControl` 的每个实例都可控制一个函数的所有实例。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorProf.idl, CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorProfilerInfo4 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [EnumJITedFunctions2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)
