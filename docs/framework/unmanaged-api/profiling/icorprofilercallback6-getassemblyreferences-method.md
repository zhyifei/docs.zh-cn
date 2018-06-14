---
title: ICorProfilerCallback6::GetAssemblyReferences 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerCallback6.GetAssemblyReferences
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: 8b391afb-d79f-41bd-94ce-43ce62c6b5fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a431283386f847c5fb0e7e8ac9d5a1d3d5875181
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460559"
---
# <a name="icorprofilercallback6getassemblyreferences-method"></a>ICorProfilerCallback6::GetAssemblyReferences 方法
[仅在 .NET Framework 4.5.2 及更高版本中受支持]  
  
 当公共语言运行时执行程序集引用闭包审核时，通知探查器程序集正处于非常早期的加载阶段。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetAssemblyReferences(        [in, string] const WCHAR* wszAssemblyPath,  
        [in] ICorProfilerAssemblyReferenceProvider* pAsmRefProvider  
);  
```  
  
#### <a name="parameters"></a>参数  
 `wszAssemblyPath`  
 [in] 元数据将发生修改的程序集的路径和名称。  
  
 `pAsmRefProvider`  
 [in]指向的地址的指针[ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)接口，用于指定该程序集引用添加。  
  
## <a name="return-value"></a>返回值  
 将忽略此回调的返回值。  
  
## <a name="remarks"></a>备注  
 通过设置控制此回调[COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)事件掩码标志时调用[ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)方法。 如果探查器注册[icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)回调方法中，运行时将传递的路径和名称的程序集进行加载，以及指向的指针[ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)接口到该方法的对象。 然后，探查器可调用[icorprofilerassemblyreferenceprovider:: Addassemblyreference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)方法替换`COR_PRF_ASSEMBLY_REFERENCE_INFO`它打算从中指定的程序集引用每个目标程序集的对象`GetAssemblyReferences`回调。  
  
 仅当探查器必须修改程序集的元数据以添加程序集引用时，才使用 `GetAssemblyReferences` 回调。 (但是请注意，在中执行程序集的元数据的实际修改[icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)回调方法。)探查器应该实现 `GetAssemblyReferences` 回调方法，从而通知公共语言运行时 (CLR)：将在加载完模块后添加程序集引用。  这有助于确保即使探查器打算以后修改元数据程序集引用，CLR 在此早期阶段作出的程序集共享决策也会保持有效。  这可以避免一些由于探查器元数据修改而导致 `SECURITY_E_INCOMPATIBLE_SHARE` 错误的实例。  
  
 探查器使用[ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)提供此方法可添加到 CLR 程序集引用闭包审核器的程序集引用的对象。  [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)对象应仅可从使用此回调内部。 调用[icorprofilerassemblyreferenceprovider:: Addassemblyreference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)从此回调的方法不会导致中修改的元数据，但只是在修改后的程序集引用闭包审核。 探查器仍将需要使用[IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)对象中显式添加程序集引用[icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)回调的引用程序集，即使它实现`GetAssemblyReferences`回调。  
  
 探查器应该准备接收同一程序集，对此回调的重复调用，并应完全相同地响应每个此类重复调用 (通过使属于同一套[ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)调用)。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerCallback6 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 [ModuleLoadFinished 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)  
 [COR_PRF_ASSEMBLY_REFERENCE_INFO 结构](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)  
 [ICorProfilerAssemblyReferenceProvider 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)
