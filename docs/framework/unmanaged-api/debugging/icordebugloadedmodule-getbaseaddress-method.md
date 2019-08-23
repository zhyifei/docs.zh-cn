---
title: ICorDebugLoadedModule::GetBaseAddress 方法
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85748106edb34b98f975a40bcc2617401536e271
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910100"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="5bee8-102">ICorDebugLoadedModule::GetBaseAddress 方法</span><span class="sxs-lookup"><span data-stu-id="5bee8-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="5bee8-103">获取已加载模块的基址。</span><span class="sxs-lookup"><span data-stu-id="5bee8-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bee8-104">语法</span><span class="sxs-lookup"><span data-stu-id="5bee8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bee8-105">参数</span><span class="sxs-lookup"><span data-stu-id="5bee8-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="5bee8-106">[out] 指向已加载模块的基址的指针。</span><span class="sxs-lookup"><span data-stu-id="5bee8-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bee8-107">备注</span><span class="sxs-lookup"><span data-stu-id="5bee8-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5bee8-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="5bee8-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bee8-109">要求</span><span class="sxs-lookup"><span data-stu-id="5bee8-109">Requirements</span></span>  
 <span data-ttu-id="5bee8-110">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5bee8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bee8-111">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="5bee8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5bee8-112">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bee8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bee8-113">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bee8-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bee8-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="5bee8-114">See also</span></span>

- [<span data-ttu-id="5bee8-115">ICorDebugLoadedModule 接口</span><span class="sxs-lookup"><span data-stu-id="5bee8-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="5bee8-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="5bee8-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
