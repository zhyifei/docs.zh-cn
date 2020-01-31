---
title: ICorProfilerInfo7：： ApplyMetaData 方法
ms.date: 02/15/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo7.ApplyMetaData
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
ms.openlocfilehash: b9e488a512ad506a8975bfff44ae02cd84c29f74
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861692"
---
# <a name="icorprofilerinfo7applymetadata-method"></a>ICorProfilerInfo7：： ApplyMetaData 方法
[仅在 .NET Framework 4.6.1 及更高版本中受支持]  
  
 将 `IMetadataEmit::Define*` 方法新定义的元数据应用于指定的模块。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a>参数  
 `moduleID`  
 中已更改其元数据的模块的标识符。  
  
## <a name="remarks"></a>备注  
 如果在[ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)回调之后进行元数据更改，则必须在使用新元数据之前调用此方法。  
  
 `ApplyMetaData` 仅支持添加以下类型的元数据：  
  
- `AssemblyRef` 记录，可通过调用[IMetaDataAssemblyEmit：:D efineassemblyref](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)创建。 方法中的 URL。  
  
- `TypeRef` 记录，可通过调用[IMetaDataEmit：:D efinetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)方法创建。  
  
- `TypeSpec` 记录，可以通过调用[IMetaDataEmit：： GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md)方法创建。  
  
- `MemberRef` 记录，可通过调用[IMetaDataEmit：:D efinememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)方法创建。  
  
- `MemberSpec` 记录，可通过调用[IMetaDataEmit2：:D efinemethodspec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)方法创建。  
  
- `UserString` 记录，可通过调用[IMetaDataEmit：:D efineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)方法创建。  

从 .NET Core 3.0 开始，`ApplyMetaData` 还支持以下类型：

- `TypeDef` 记录，可通过调用[IMetaDataEmit：:D efinetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)方法创建。

- `MethodDef` 记录，可通过调用[IMetaDataEmit：:D efinemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)方法创建。 但是，不支持向现有类型添加虚拟方法。 必须在[ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)回调之前添加虚拟方法。

## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo7 接口](icorprofilerinfo7-interface.md)
