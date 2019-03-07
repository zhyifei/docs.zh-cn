---
title: PreBindAssemblyEx 函数
ms.date: 03/30/2017
api_name:
- PreBindAssemblyEx
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- PreBindAssemblyEx
helpviewer_keywords:
- PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07b3b3a32796b5805dbf86449921518a77e95d6b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480528"
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="93935-102">PreBindAssemblyEx 函数</span><span class="sxs-lookup"><span data-stu-id="93935-102">PreBindAssemblyEx Function</span></span>
<span data-ttu-id="93935-103">获取程序集的策略后的显示名称。</span><span class="sxs-lookup"><span data-stu-id="93935-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="93935-104">此函数支持.NET Framework 基础结构，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="93935-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93935-105">语法</span><span class="sxs-lookup"><span data-stu-id="93935-105">Syntax</span></span>  
  
```  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="93935-106">参数</span><span class="sxs-lookup"><span data-stu-id="93935-106">Parameters</span></span>  
 `pAppCtx`  
 <span data-ttu-id="93935-107">[in]标识应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="93935-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="93935-108">[in]标识程序集名称。</span><span class="sxs-lookup"><span data-stu-id="93935-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="93935-109">[in]标识父程序集。</span><span class="sxs-lookup"><span data-stu-id="93935-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="93935-110">忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="93935-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="93935-111">[in]标识运行时版本。</span><span class="sxs-lookup"><span data-stu-id="93935-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="93935-112">[out]包含策略后的显示名称。</span><span class="sxs-lookup"><span data-stu-id="93935-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="93935-113">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="93935-113">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="93935-114">`pvReserved` 必须是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="93935-114">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93935-115">备注</span><span class="sxs-lookup"><span data-stu-id="93935-115">Remarks</span></span>  
 <span data-ttu-id="93935-116">`ppNamePostPolicy`仅当该函数将返回 HRESULT FUSION_E_REF_DEF_MISMATCH 设置输出参数。</span><span class="sxs-lookup"><span data-stu-id="93935-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="93935-117">否则，它为 null。</span><span class="sxs-lookup"><span data-stu-id="93935-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93935-118">要求</span><span class="sxs-lookup"><span data-stu-id="93935-118">Requirements</span></span>  
 <span data-ttu-id="93935-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="93935-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93935-120">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="93935-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="93935-121">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="93935-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="93935-122">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93935-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93935-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="93935-123">See also</span></span>
- [<span data-ttu-id="93935-124">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="93935-124">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
