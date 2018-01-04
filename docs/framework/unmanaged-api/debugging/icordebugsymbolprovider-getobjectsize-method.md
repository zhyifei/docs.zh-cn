---
title: "ICorDebugSymbolProvider::GetObjectSize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8817eb79c825a02ec5654ec340dedd6c77889a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="4af54-102">ICorDebugSymbolProvider::GetObjectSize 方法</span><span class="sxs-lookup"><span data-stu-id="4af54-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="4af54-103">基于对象的 Typespec 签名返回对象的大小。</span><span class="sxs-lookup"><span data-stu-id="4af54-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4af54-104">语法</span><span class="sxs-lookup"><span data-stu-id="4af54-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4af54-105">参数</span><span class="sxs-lookup"><span data-stu-id="4af54-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="4af54-106">[in] TypeSpec 签名中的字节数。</span><span class="sxs-lookup"><span data-stu-id="4af54-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="4af54-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="4af54-107">typeSig</span></span>  
 <span data-ttu-id="4af54-108">[in] TypeSpec 签名。</span><span class="sxs-lookup"><span data-stu-id="4af54-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="4af54-109">[out] 指向对象大小的指针。</span><span class="sxs-lookup"><span data-stu-id="4af54-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4af54-110">备注</span><span class="sxs-lookup"><span data-stu-id="4af54-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4af54-111">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="4af54-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4af54-112">惠?</span><span class="sxs-lookup"><span data-stu-id="4af54-112">Requirements</span></span>  
 <span data-ttu-id="4af54-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4af54-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4af54-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4af54-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4af54-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4af54-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4af54-116">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4af54-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af54-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="4af54-117">See Also</span></span>  
 [<span data-ttu-id="4af54-118">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="4af54-118">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="4af54-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="4af54-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
