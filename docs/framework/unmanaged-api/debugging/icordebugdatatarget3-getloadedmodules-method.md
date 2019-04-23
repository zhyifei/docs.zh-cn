---
title: ICorDebugDataTarget3::GetLoadedModules 方法
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 464fd9ac44d6ba5717dbc4ecfbe03b6e6ad52276
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59138653"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="a343e-102">ICorDebugDataTarget3::GetLoadedModules 方法</span><span class="sxs-lookup"><span data-stu-id="a343e-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="a343e-103">获取到目前为止已加载的模块的列表。</span><span class="sxs-lookup"><span data-stu-id="a343e-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a343e-104">语法</span><span class="sxs-lookup"><span data-stu-id="a343e-104">Syntax</span></span>  
  
```  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a343e-105">参数</span><span class="sxs-lookup"><span data-stu-id="a343e-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="a343e-106">[in] 请求了其信息的模块数。</span><span class="sxs-lookup"><span data-stu-id="a343e-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="a343e-107">[out] 指向返回了相关信息的模块数的指针。</span><span class="sxs-lookup"><span data-stu-id="a343e-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="a343e-108">[out]指向数组的指针[ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)提供有关的信息的对象加载的模块。</span><span class="sxs-lookup"><span data-stu-id="a343e-108">[out] A pointer to an array of [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a343e-109">备注</span><span class="sxs-lookup"><span data-stu-id="a343e-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a343e-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="a343e-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a343e-111">要求</span><span class="sxs-lookup"><span data-stu-id="a343e-111">Requirements</span></span>  
 <span data-ttu-id="a343e-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a343e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a343e-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a343e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a343e-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a343e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a343e-115">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a343e-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a343e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a343e-116">See also</span></span>

- [<span data-ttu-id="a343e-117">ICorDebugDataTarget3 接口</span><span class="sxs-lookup"><span data-stu-id="a343e-117">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)
- [<span data-ttu-id="a343e-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="a343e-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
