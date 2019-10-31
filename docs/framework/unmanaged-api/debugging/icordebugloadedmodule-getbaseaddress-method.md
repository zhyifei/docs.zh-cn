---
title: ICorDebugLoadedModule::GetBaseAddress 方法
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: 8af814ff2eaaf3ae6dae9031c13bf37ea0c1236b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122647"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="601db-102">ICorDebugLoadedModule::GetBaseAddress 方法</span><span class="sxs-lookup"><span data-stu-id="601db-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="601db-103">获取已加载模块的基址。</span><span class="sxs-lookup"><span data-stu-id="601db-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="601db-104">语法</span><span class="sxs-lookup"><span data-stu-id="601db-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="601db-105">参数</span><span class="sxs-lookup"><span data-stu-id="601db-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="601db-106">[out] 指向已加载模块的基址的指针。</span><span class="sxs-lookup"><span data-stu-id="601db-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="601db-107">备注</span><span class="sxs-lookup"><span data-stu-id="601db-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="601db-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="601db-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="601db-109">要求</span><span class="sxs-lookup"><span data-stu-id="601db-109">Requirements</span></span>  
 <span data-ttu-id="601db-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="601db-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="601db-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="601db-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="601db-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="601db-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="601db-113">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="601db-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="601db-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="601db-114">See also</span></span>

- [<span data-ttu-id="601db-115">ICorDebugLoadedModule 接口</span><span class="sxs-lookup"><span data-stu-id="601db-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="601db-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="601db-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
