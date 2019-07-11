---
title: ICorDebugStaticFieldSymbol::GetAddress 方法
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a45f233fdec23a504a71a68370e9da8e38ac0bd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760869"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="ad5ab-102">ICorDebugStaticFieldSymbol::GetAddress 方法</span><span class="sxs-lookup"><span data-stu-id="ad5ab-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="ad5ab-103">获取静态字段的地址。</span><span class="sxs-lookup"><span data-stu-id="ad5ab-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad5ab-104">语法</span><span class="sxs-lookup"><span data-stu-id="ad5ab-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad5ab-105">参数</span><span class="sxs-lookup"><span data-stu-id="ad5ab-105">Parameters</span></span>  
 <span data-ttu-id="ad5ab-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="ad5ab-106">pRVA</span></span>  
 <span data-ttu-id="ad5ab-107">[out] 指向静态字段的相对虚拟地址 (RVA) 的指针。</span><span class="sxs-lookup"><span data-stu-id="ad5ab-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad5ab-108">备注</span><span class="sxs-lookup"><span data-stu-id="ad5ab-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad5ab-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="ad5ab-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad5ab-110">要求</span><span class="sxs-lookup"><span data-stu-id="ad5ab-110">Requirements</span></span>  
 <span data-ttu-id="ad5ab-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ad5ab-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad5ab-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad5ab-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad5ab-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad5ab-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad5ab-114">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad5ab-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad5ab-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad5ab-115">See also</span></span>

- [<span data-ttu-id="ad5ab-116">ICorDebugStaticFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="ad5ab-116">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="ad5ab-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="ad5ab-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
