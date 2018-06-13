---
title: ICorProfilerInfo::GetILFunctionBody 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bde194023ff6913db9a56e30eddaad8d7abc5ad1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452802"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a><span data-ttu-id="009f3-102">ICorProfilerInfo::GetILFunctionBody 方法</span><span class="sxs-lookup"><span data-stu-id="009f3-102">ICorProfilerInfo::GetILFunctionBody Method</span></span>
<span data-ttu-id="009f3-103">获取一个指针指向方法的正文在 Microsoft 中间语言 (MSIL) 代码中，开始其标头。</span><span class="sxs-lookup"><span data-stu-id="009f3-103">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="009f3-104">语法</span><span class="sxs-lookup"><span data-stu-id="009f3-104">Syntax</span></span>  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="009f3-105">参数</span><span class="sxs-lookup"><span data-stu-id="009f3-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="009f3-106">[in]函数所在模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="009f3-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodId`  
 <span data-ttu-id="009f3-107">[in]方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="009f3-107">[in] The metadata token for the method.</span></span>  
  
 `ppMethodHeader`  
 <span data-ttu-id="009f3-108">[out]指向方法的标头的指针。</span><span class="sxs-lookup"><span data-stu-id="009f3-108">[out] A pointer to the method's header.</span></span>  
  
 `pcbMethodSize`  
 <span data-ttu-id="009f3-109">[out]一个整数，指定方法的大小。</span><span class="sxs-lookup"><span data-stu-id="009f3-109">[out] An integer that specifies the size of the method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="009f3-110">备注</span><span class="sxs-lookup"><span data-stu-id="009f3-110">Remarks</span></span>  
 <span data-ttu-id="009f3-111">一种方法的作用范围由其所在的模块。</span><span class="sxs-lookup"><span data-stu-id="009f3-111">A method is scoped by the module in which it lives.</span></span> <span data-ttu-id="009f3-112">因为`GetILFunctionBody`方法旨在让 MSIL 代码的工具访问，公共语言运行时 (CLR) 加载之前，它使用该方法的元数据标记查找所需的实例。</span><span class="sxs-lookup"><span data-stu-id="009f3-112">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span></span>  
  
 <span data-ttu-id="009f3-113">`GetILFunctionBody` 如果可以返回 CORPROF_E_FUNCTION_NOT_IL HRESULT`methodId`指向一种方法，无任何 MSIL 代码 （例如，一个抽象方法或平台 invoke (PInvoke) 方法)。</span><span class="sxs-lookup"><span data-stu-id="009f3-113">`GetILFunctionBody` can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="009f3-114">要求</span><span class="sxs-lookup"><span data-stu-id="009f3-114">Requirements</span></span>  
 <span data-ttu-id="009f3-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="009f3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="009f3-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="009f3-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="009f3-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="009f3-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="009f3-118">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="009f3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="009f3-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="009f3-119">See Also</span></span>  
 [<span data-ttu-id="009f3-120">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="009f3-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
