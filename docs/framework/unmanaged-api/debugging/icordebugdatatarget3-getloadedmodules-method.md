---
title: "ICorDebugDataTarget3::GetLoadedModules 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3db6449abee4eed4a8e5d6c691834c52dc0717e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="8abab-102">ICorDebugDataTarget3::GetLoadedModules 方法</span><span class="sxs-lookup"><span data-stu-id="8abab-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="8abab-103">获取到目前为止已加载的模块的列表。</span><span class="sxs-lookup"><span data-stu-id="8abab-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8abab-104">语法</span><span class="sxs-lookup"><span data-stu-id="8abab-104">Syntax</span></span>  
  
```  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8abab-105">参数</span><span class="sxs-lookup"><span data-stu-id="8abab-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="8abab-106">[in] 请求了其信息的模块数。</span><span class="sxs-lookup"><span data-stu-id="8abab-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="8abab-107">[out] 指向返回了相关信息的模块数的指针。</span><span class="sxs-lookup"><span data-stu-id="8abab-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="8abab-108">[out]指向数组的指针[ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)加载模块提供了一些信息的对象。</span><span class="sxs-lookup"><span data-stu-id="8abab-108">[out] A pointer to an array of [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8abab-109">备注</span><span class="sxs-lookup"><span data-stu-id="8abab-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8abab-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="8abab-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8abab-111">惠?</span><span class="sxs-lookup"><span data-stu-id="8abab-111">Requirements</span></span>  
 <span data-ttu-id="8abab-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8abab-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8abab-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8abab-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8abab-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8abab-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8abab-115">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8abab-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8abab-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="8abab-116">See Also</span></span>  
 [<span data-ttu-id="8abab-117">ICorDebugDataTarget3 接口</span><span class="sxs-lookup"><span data-stu-id="8abab-117">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 [<span data-ttu-id="8abab-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="8abab-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
