---
title: ICorProfilerInfo::GetClassFromToken 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
ms.openlocfilehash: 841953625235406f013e9f140ad91c7b65680e47
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863948"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="189f5-102">ICorProfilerInfo::GetClassFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="189f5-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="189f5-103">给定元数据标记，获取类的 ID。</span><span class="sxs-lookup"><span data-stu-id="189f5-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="189f5-104">此方法在 .NET Framework 版本2.0 中已过时。</span><span class="sxs-lookup"><span data-stu-id="189f5-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="189f5-105">改[为使用 ICorProfilerInfo2：： GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) 。</span><span class="sxs-lookup"><span data-stu-id="189f5-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="189f5-106">语法</span><span class="sxs-lookup"><span data-stu-id="189f5-106">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="189f5-107">参数</span><span class="sxs-lookup"><span data-stu-id="189f5-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="189f5-108">中包含类的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="189f5-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="189f5-109">中引用类的 `mdTypeDef` 元数据标记。</span><span class="sxs-lookup"><span data-stu-id="189f5-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="189f5-110">弄指向类 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="189f5-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="189f5-111">备注</span><span class="sxs-lookup"><span data-stu-id="189f5-111">Remarks</span></span>  
 <span data-ttu-id="189f5-112">此方法已过时;相反，请对所有类型使用 `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs`。</span><span class="sxs-lookup"><span data-stu-id="189f5-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="189f5-113">需求</span><span class="sxs-lookup"><span data-stu-id="189f5-113">Requirements</span></span>  
 <span data-ttu-id="189f5-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="189f5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="189f5-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="189f5-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="189f5-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="189f5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="189f5-117">**.NET Framework 版本：** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="189f5-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="189f5-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="189f5-118">See also</span></span>

- [<span data-ttu-id="189f5-119">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="189f5-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
