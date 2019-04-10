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
ms.openlocfilehash: b2960bc0cfc39adb9b7cbca236d495baf630a173
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201411"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a><span data-ttu-id="e4c00-102">ICorProfilerInfo::GetILFunctionBody 方法</span><span class="sxs-lookup"><span data-stu-id="e4c00-102">ICorProfilerInfo::GetILFunctionBody Method</span></span>
<span data-ttu-id="e4c00-103">获取一个指针指向方法的主体在 Microsoft 中间语言 (MSIL) 代码中，从其标头处开始。</span><span class="sxs-lookup"><span data-stu-id="e4c00-103">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4c00-104">语法</span><span class="sxs-lookup"><span data-stu-id="e4c00-104">Syntax</span></span>  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4c00-105">参数</span><span class="sxs-lookup"><span data-stu-id="e4c00-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="e4c00-106">[in]该函数所在的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="e4c00-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodId`  
 <span data-ttu-id="e4c00-107">[in]方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="e4c00-107">[in] The metadata token for the method.</span></span>  
  
 `ppMethodHeader`  
 <span data-ttu-id="e4c00-108">[out]指向方法的标头的指针。</span><span class="sxs-lookup"><span data-stu-id="e4c00-108">[out] A pointer to the method's header.</span></span>  
  
 `pcbMethodSize`  
 <span data-ttu-id="e4c00-109">[out]一个整数，指定方法的大小。</span><span class="sxs-lookup"><span data-stu-id="e4c00-109">[out] An integer that specifies the size of the method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4c00-110">备注</span><span class="sxs-lookup"><span data-stu-id="e4c00-110">Remarks</span></span>  
 <span data-ttu-id="e4c00-111">一种方法是按其所在的模块限定范围。</span><span class="sxs-lookup"><span data-stu-id="e4c00-111">A method is scoped by the module in which it lives.</span></span> <span data-ttu-id="e4c00-112">因为`GetILFunctionBody`方法旨在为访问工具提供对 MSIL 代码，然后加载公共语言运行时 (CLR)，它使用的元数据标记的方法来查找所需的实例。</span><span class="sxs-lookup"><span data-stu-id="e4c00-112">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span></span>  
  
 `GetILFunctionBody` <span data-ttu-id="e4c00-113">如果可以返回 CORPROF_E_FUNCTION_NOT_IL HRESULT`methodId`指向一种方法，没有任何 MSIL 代码 （如一个抽象方法或平台调用 (PInvoke) 方法）。</span><span class="sxs-lookup"><span data-stu-id="e4c00-113">can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4c00-114">要求</span><span class="sxs-lookup"><span data-stu-id="e4c00-114">Requirements</span></span>  
 <span data-ttu-id="e4c00-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e4c00-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4c00-116">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e4c00-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e4c00-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4c00-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e4c00-118">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="e4c00-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e4c00-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4c00-119">See also</span></span>

- [<span data-ttu-id="e4c00-120">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="e4c00-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
