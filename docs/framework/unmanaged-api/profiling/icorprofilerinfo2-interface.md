---
title: ICorProfilerInfo2 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2
helpviewer_keywords:
- ICorProfilerInfo2 interface [.NET Framework profiling]
ms.assetid: 91bd49b6-4d12-494f-a8f1-2f251e8c65e3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8cec2a622a1a30881949ad5a9f2050077e195015
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo2-interface"></a>ICorProfilerInfo2 接口
提供代码探查器用于与公共语言运行时 (CLR)，从而控制事件监视并请求信息通信的方法。 `ICorProfilerInfo2`接口是的扩展[ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)接口。 也就是说，它提供了.NET Framework 2.0 版和更高版本中支持的新方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[DoStackSnapshot 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)|遍历指定的线程，以向探查器报告托管的调用帧的堆栈。|  
|[EnumModuleFrozenObjects 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)|获取允许迭代通过指定模块中的已冻结对象的枚举器。|  
|[GetAppDomainStaticAddress 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getappdomainstaticaddress-method.md)|获取指定的应用程序域范围内的指定的应用程序域的静态字段的地址。|  
|[GetArrayObjectInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getarrayobjectinfo-method.md)|获取一个数组对象的详细的信息。|  
|[GetBoxClassLayout 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getboxclasslayout-method.md)|获取指定的值类型进行装箱，类布局信息。|  
|[GetClassFromTokenAndTypeArgs 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)|获取`ClassID`通过使用指定元数据标记的类型和`ClassID`值的任何类型参数。|  
|[GetClassIDInfo2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)|获取指定泛型类，该类的元数据标记的父模块`ClassID`其父类和`ClassID`每个类型参数，（如果存在） 的类。|  
|[GetClassLayout 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclasslayout-method.md)|获取内存中由指定的类定义的字段的布局信息。 也就是说，此方法获取类的字段的偏移量。|  
|[GetCodeInfo2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)|获取与指定 `FunctionID` 关联的本机代码的范围。|  
|[GetContextStaticAddress 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcontextstaticaddress-method.md)|获取指定的上下文范围内的指定上下文的静态字段的地址。|  
|[GetFunctionFromTokenAndTypeArgs 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)|获取`FunctionID`通过使用指定元数据标记，包含类的函数和`ClassID`值的任何类型参数。|  
|[GetFunctionInfo2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)|获取每个类型参数或某个函数（如果存在）的父类、元数据标记和 `ClassID`。|  
|[GetGenerationBounds 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md)|获取构成代的垃圾回收堆的内存区域 （堆段）。|  
|[GetNotifiedExceptionClauseInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)|获取异常子句的本机地址和帧信息 (`catch`/`finally`/`filter`)，是要运行或只需运行。|  
|[GetObjectGeneration 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md)|获取包含指定的对象的堆的段。|  
|[GetRVAStaticAddress 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getrvastaticaddress-method.md)|获取指定的相对虚拟地址 (RVA) 的地址的静态字段。|  
|[GetStaticFieldInfo 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstaticfieldinfo-method.md)|获取在其中指定的字段是静态的范围。|  
|[GetStringLayout 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md)|获取有关字符串对象布局的信息。|  
|[GetThreadAppDomain 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)|获取在其中指定的线程当前正在执行代码的应用程序域的 ID。|  
|[GetThreadStaticAddress 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md)|获取指定线程的范围内的指定线程静态字段的地址。|  
|[SetEnterLeaveFunctionHooks2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)|指定要在"输入"、"保留"和"tailcall"挂钩托管函数调用的探查器实现的函数。|  
  
## <a name="remarks"></a>备注  
 探查器中调用一个方法`ICorProfilerInfo2`接口与 CLR 以控制事件监视及请求信息进行通信。  
  
 方法`ICorProfilerInfo2`由 CLR 使用自由线程模型实现接口。 每个方法均返回一个 HRESULT，指示成功或失败。 有关可能的返回代码的列表，请参阅 CorError.h 文件。  
  
 CLR 将传递`ICorProfilerInfo2`到每个代码探查器在初始化，期间使用探查器的实现的接口[icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)。 然后，代码探查器可以调用的方法`ICorProfilerInfo2`接口来获取有关正在 CLR 控件下执行的托管代码的信息。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
