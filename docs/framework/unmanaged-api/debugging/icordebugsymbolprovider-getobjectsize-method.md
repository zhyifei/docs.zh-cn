---
title: ICorDebugSymbolProvider::GetObjectSize 方法
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbcdb5541fdd49944f462321dc24131a32a42391
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61953759"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="1a233-102">ICorDebugSymbolProvider::GetObjectSize 方法</span><span class="sxs-lookup"><span data-stu-id="1a233-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="1a233-103">基于对象的 TypeSpec 签名返回对象的大小。</span><span class="sxs-lookup"><span data-stu-id="1a233-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a233-104">语法</span><span class="sxs-lookup"><span data-stu-id="1a233-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a233-105">参数</span><span class="sxs-lookup"><span data-stu-id="1a233-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="1a233-106">[in] TypeSpec 签名中的字节数。</span><span class="sxs-lookup"><span data-stu-id="1a233-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="1a233-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="1a233-107">typeSig</span></span>  
 <span data-ttu-id="1a233-108">[in] TypeSpec 签名。</span><span class="sxs-lookup"><span data-stu-id="1a233-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="1a233-109">[out] 指向对象大小的指针。</span><span class="sxs-lookup"><span data-stu-id="1a233-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a233-110">备注</span><span class="sxs-lookup"><span data-stu-id="1a233-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a233-111">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="1a233-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a233-112">要求</span><span class="sxs-lookup"><span data-stu-id="1a233-112">Requirements</span></span>  
 <span data-ttu-id="1a233-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1a233-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a233-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a233-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a233-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a233-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a233-116">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a233-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a233-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a233-117">See also</span></span>

- [<span data-ttu-id="1a233-118">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="1a233-118">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="1a233-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="1a233-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
