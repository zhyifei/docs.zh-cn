---
title: "ICorDebugLoadedModule::GetBaseAddress 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d71b1db35a9e2747e7e14787f385f42f98305c61
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="c557a-102">ICorDebugLoadedModule::GetBaseAddress 方法</span><span class="sxs-lookup"><span data-stu-id="c557a-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="c557a-103">获取已加载模块的基址。</span><span class="sxs-lookup"><span data-stu-id="c557a-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c557a-104">语法</span><span class="sxs-lookup"><span data-stu-id="c557a-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c557a-105">参数</span><span class="sxs-lookup"><span data-stu-id="c557a-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="c557a-106">[out] 指向已加载模块的基址的指针。</span><span class="sxs-lookup"><span data-stu-id="c557a-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c557a-107">备注</span><span class="sxs-lookup"><span data-stu-id="c557a-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c557a-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="c557a-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c557a-109">惠?</span><span class="sxs-lookup"><span data-stu-id="c557a-109">Requirements</span></span>  
 <span data-ttu-id="c557a-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c557a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c557a-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c557a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c557a-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c557a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c557a-113">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c557a-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c557a-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c557a-114">See Also</span></span>  
 [<span data-ttu-id="c557a-115">ICorDebugLoadedModule 接口</span><span class="sxs-lookup"><span data-stu-id="c557a-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 [<span data-ttu-id="c557a-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="c557a-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
