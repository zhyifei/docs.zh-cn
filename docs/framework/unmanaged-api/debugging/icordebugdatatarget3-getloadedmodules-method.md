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
ms.openlocfilehash: bc4820d2c71830b297ed690c440c90cfff1f9601
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="f7ad4-102">ICorDebugDataTarget3::GetLoadedModules 方法</span><span class="sxs-lookup"><span data-stu-id="f7ad4-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="f7ad4-103">获取到目前为止已加载的模块的列表。</span><span class="sxs-lookup"><span data-stu-id="f7ad4-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7ad4-104">语法</span><span class="sxs-lookup"><span data-stu-id="f7ad4-104">Syntax</span></span>  
  
```  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7ad4-105">参数</span><span class="sxs-lookup"><span data-stu-id="f7ad4-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="f7ad4-106">[in] 请求了其信息的模块数。</span><span class="sxs-lookup"><span data-stu-id="f7ad4-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="f7ad4-107">[out] 指向返回了相关信息的模块数的指针。</span><span class="sxs-lookup"><span data-stu-id="f7ad4-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="f7ad4-108">[out]指向数组的指针[ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)加载模块提供了一些信息的对象。</span><span class="sxs-lookup"><span data-stu-id="f7ad4-108">[out] A pointer to an array of [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7ad4-109">备注</span><span class="sxs-lookup"><span data-stu-id="f7ad4-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7ad4-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="f7ad4-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7ad4-111">要求</span><span class="sxs-lookup"><span data-stu-id="f7ad4-111">Requirements</span></span>  
 <span data-ttu-id="f7ad4-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f7ad4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7ad4-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7ad4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7ad4-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7ad4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7ad4-115">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7ad4-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7ad4-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7ad4-116">See Also</span></span>  
 [<span data-ttu-id="f7ad4-117">ICorDebugDataTarget3 接口</span><span class="sxs-lookup"><span data-stu-id="f7ad4-117">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 [<span data-ttu-id="f7ad4-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="f7ad4-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
