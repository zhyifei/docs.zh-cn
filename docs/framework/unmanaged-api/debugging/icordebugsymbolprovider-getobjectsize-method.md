---
title: ICorDebugSymbolProvider::GetObjectSize 方法
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 10374f76edb9446093b89d064570ce05193129b3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498323"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="e5a6c-102">ICorDebugSymbolProvider::GetObjectSize 方法</span><span class="sxs-lookup"><span data-stu-id="e5a6c-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="e5a6c-103">基于对象的 TypeSpec 签名返回对象的大小。</span><span class="sxs-lookup"><span data-stu-id="e5a6c-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5a6c-104">语法</span><span class="sxs-lookup"><span data-stu-id="e5a6c-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5a6c-105">参数</span><span class="sxs-lookup"><span data-stu-id="e5a6c-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="e5a6c-106">[in] TypeSpec 签名中的字节数。</span><span class="sxs-lookup"><span data-stu-id="e5a6c-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="e5a6c-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="e5a6c-107">typeSig</span></span>  
 <span data-ttu-id="e5a6c-108">[in] TypeSpec 签名。</span><span class="sxs-lookup"><span data-stu-id="e5a6c-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="e5a6c-109">[out] 指向对象大小的指针。</span><span class="sxs-lookup"><span data-stu-id="e5a6c-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5a6c-110">备注</span><span class="sxs-lookup"><span data-stu-id="e5a6c-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5a6c-111">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="e5a6c-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5a6c-112">要求</span><span class="sxs-lookup"><span data-stu-id="e5a6c-112">Requirements</span></span>  
 <span data-ttu-id="e5a6c-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e5a6c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5a6c-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5a6c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5a6c-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5a6c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5a6c-116">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5a6c-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5a6c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5a6c-117">See also</span></span>
- [<span data-ttu-id="e5a6c-118">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="e5a6c-118">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="e5a6c-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="e5a6c-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
