---
title: ICorDebugSymbolProvider::GetStaticFieldSymbols 方法
ms.date: 03/30/2017
ms.assetid: b178367f-a6e4-413c-b06f-daf3804b456b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 69ad0878daf57c379a5958dbeacddac8510c6eba
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476147"
---
# <a name="icordebugsymbolprovidergetstaticfieldsymbols-method"></a><span data-ttu-id="b5433-102">ICorDebugSymbolProvider::GetStaticFieldSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="b5433-102">ICorDebugSymbolProvider::GetStaticFieldSymbols Method</span></span>
<span data-ttu-id="b5433-103">获取与 Typespec 签名相对应的静态字段符号。</span><span class="sxs-lookup"><span data-stu-id="b5433-103">Gets the static field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5433-104">语法</span><span class="sxs-lookup"><span data-stu-id="b5433-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugStaticFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5433-105">参数</span><span class="sxs-lookup"><span data-stu-id="b5433-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="b5433-106">[in] `typeSig` 数组中的字节数。</span><span class="sxs-lookup"><span data-stu-id="b5433-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="b5433-107">[in] 包含 `typespec` 签名的字节数组。</span><span class="sxs-lookup"><span data-stu-id="b5433-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="b5433-108">[in] 请求的符号数。</span><span class="sxs-lookup"><span data-stu-id="b5433-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="b5433-109">[out] 一个指针，指向由方法检索的符号的数量。</span><span class="sxs-lookup"><span data-stu-id="b5433-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="b5433-110">[out]一个指向[ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)数组，其中包含请求的静态字段符号。</span><span class="sxs-lookup"><span data-stu-id="b5433-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) array that contains the requested static field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5433-111">备注</span><span class="sxs-lookup"><span data-stu-id="b5433-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5433-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="b5433-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5433-113">要求</span><span class="sxs-lookup"><span data-stu-id="b5433-113">Requirements</span></span>  
 <span data-ttu-id="b5433-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b5433-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5433-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5433-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5433-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5433-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5433-117">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5433-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5433-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5433-118">See also</span></span>
- [<span data-ttu-id="b5433-119">GetInstanceFieldSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="b5433-119">GetInstanceFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)
- [<span data-ttu-id="b5433-120">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="b5433-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="b5433-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="b5433-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
