---
title: ICorProfilerInfo2::GetClassIDInfo2 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassIDInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassIDInfo2
helpviewer_keywords:
- GetClassIDInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassIDInfo2 method [.NET Framework profiling]
ms.assetid: 0141d582-d066-4d49-8d1f-ae82129a1960
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2af0eacbff8220be7f2286f7f345f14126972261
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458518"
---
# <a name="icorprofilerinfo2getclassidinfo2-method"></a>ICorProfilerInfo2::GetClassIDInfo2 方法
打开泛型定义中指定的类中，令牌获取的父模块和元数据`ClassID`其父类和`ClassID`每个类型参数，（如果存在） 的类。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetClassIDInfo2(  
    [in]  ClassID classId,  
    [out] ModuleID *pModuleId,  
    [out] mdTypeDef *pTypeDefToken,  
    [out] ClassID *pParentClassId,  
    [in]  ULONG32 cNumTypeArgs,  
    [out] ULONG32 *pcNumTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
#### <a name="parameters"></a>参数  
 `classId`  
 [in] 将为其检索信息的类的 ID。  
  
 `pModuleId`  
 [out]打开泛型定义中指定的类的父模块 id 的指针。  
  
 `pTypeDefToken`  
 [out]打开泛型定义中指定的类的元数据标记的指针。  
  
 `pParentClassId`  
 [out] 指向父类 ID 的指针。  
  
 `cNumTypeArgs`  
 [in] `typeArgs` 数组的大小。  
  
 `pcNumTypeArgs`  
 [out] 指向可用元素总数的指针。  
  
 `typeArgs`  
 [out] `ClassID` 值的数组，其中每个值表示类的类型参数 ID。 方法返回时，`typeArgs` 将包含部分或全部可用 `ClassID` 值。  
  
## <a name="remarks"></a>备注  
 `GetClassIDInfo2`方法类似于是[icorprofilerinfo:: Getclassidinfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)方法，但`GetClassIDInfo2`包含有关泛型类型的其他信息。  
  
 探查器代码可以调用[icorprofilerinfo:: Getmodulemetadata](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)获取[元数据](../../../../docs/framework/unmanaged-api/metadata/index.md)给定模块的接口。 返回至 `pTypeDefToken` 所引用的位置的元数据标记可用于访问类的元数据。  
  
 `GetClassIDInfo2` 返回后，必须验证 `typeArgs` 缓冲区是否足够大，可包含所有 `ClassID` 值。 为此，请比较 `pcNumTypeArgs` 指向的值和 `cNumTypeArgs` 参数的值。 如果 `pcNumTypeArgs` 指向的值大于 `cNumTypeArgs`，请分配更大的 `typeArgs` 缓冲区，并用新的、更大的大小更新 `cNumTypeArgs`，然后再次调用 `GetClassIDInfo2`。  
  
 或者，可以先用长度为零的 `typeArgs` 缓冲区调用 `GetClassIDInfo2` 以获取正确的缓冲区大小。 然后，可将 `typeArgs` 缓冲区大小设置为 `pcNumTypeArgs` 中返回的值，并再次调用 `GetClassIDInfo2`。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [分析](../../../../docs/framework/unmanaged-api/profiling/index.md)
