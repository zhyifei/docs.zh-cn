---
title: ICorProfilerInfo4 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4
helpviewer_keywords:
- ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f452a3324365fb23e1affc11dbdb2ede15346010
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462437"
---
# <a name="icorprofilerinfo4-interface"></a>ICorProfilerInfo4 接口
提供代码探查器用于与公共语言运行时 (CLR)，从而控制事件监视并请求信息通信的方法。 . `ICorProfilerInfo4`接口是其他扩展`ICorProfilerInfo`接口。 它提供了新方法，以支持实时 (JIT) 重新编译，在中添加[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[EnumJITedFunctions2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)|返回所有先前 JIT 编译和 JIT 重新编译的函数的枚举数。|  
|[EnumThreads 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumthreads-method.md)|获取一个枚举器，它提供方法以按顺序循环访问所分析进程中的所有托管线程的集合。|  
|[GetCodeInfo3 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)|获取本机代码的范围，该代码与指定函数的 JIT 重新编译版本相关联。|  
|[GetFunctionFromIP2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getfunctionfromip2-method.md)|将托管的代码指令指针映射到指定的函数的 JIT 重新编译版本。|  
|[GetILToNativeMapping2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)|获取的 Microsoft 中间语言 (MSIL) 偏移量到本机偏移量指定的函数的 JIT 重新编译版本中包含的代码的映射。|  
|[GetObjectSize2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)|返回指定对象的大小。|  
|[GetReJITIDs 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getrejitids-method.md)|返回一个标识 JIT 重新编译的所有版本的指定的函数仍分配的 Id 数组。|  
|[InitializeCurrentThread 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-initializecurrentthread-method.md)|初始化之前在同一线程调用的 API，因此可以避免该死锁的后续探查器的当前线程。|  
|[RequestReJIT 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)|请求 JIT 重新编译指定函数的所有实例。|  
|[RequestRevert 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)|将指定函数的所有实例还原为其初始版本。|  
  
## <a name="remarks"></a>备注  
 CLR 通过使用自由线程模型实现 `ICorProfilerInfo4` 接口的方法。 每个方法均返回一个 HRESULT，指示成功或失败。 有关可能的返回代码的列表，请参阅 CorError.h 文件。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
