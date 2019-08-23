---
title: 'ICorDebugSymbolProvider:: GetInstanceFieldSymbols 方法'
ms.date: 03/30/2017
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6bba47500b024bc1f2a2be21d461a6f5933f0ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964608"
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a><span data-ttu-id="581c8-102">ICorDebugSymbolProvider:: GetInstanceFieldSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="581c8-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols Method</span></span>
<span data-ttu-id="581c8-103">获取与 Typespec 签名相对应的实例字段符号。</span><span class="sxs-lookup"><span data-stu-id="581c8-103">Gets the instance field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="581c8-104">语法</span><span class="sxs-lookup"><span data-stu-id="581c8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="581c8-105">参数</span><span class="sxs-lookup"><span data-stu-id="581c8-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="581c8-106">[in] `typeSig` 数组中的字节数。</span><span class="sxs-lookup"><span data-stu-id="581c8-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="581c8-107">[in] 包含 `typespec` 签名的字节数组。</span><span class="sxs-lookup"><span data-stu-id="581c8-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="581c8-108">[in] 请求的符号数。</span><span class="sxs-lookup"><span data-stu-id="581c8-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="581c8-109">[out] 一个指针，指向由方法检索的符号的数量。</span><span class="sxs-lookup"><span data-stu-id="581c8-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="581c8-110">弄指向[ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)数组的指针, 该数组包含请求的实例字段符号。</span><span class="sxs-lookup"><span data-stu-id="581c8-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) array that contains the requested instance field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="581c8-111">备注</span><span class="sxs-lookup"><span data-stu-id="581c8-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="581c8-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="581c8-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="581c8-113">要求</span><span class="sxs-lookup"><span data-stu-id="581c8-113">Requirements</span></span>  
 <span data-ttu-id="581c8-114">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="581c8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="581c8-115">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="581c8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="581c8-116">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="581c8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="581c8-117">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="581c8-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="581c8-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="581c8-118">See also</span></span>

- [<span data-ttu-id="581c8-119">GetStaticFieldSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="581c8-119">GetStaticFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)
- [<span data-ttu-id="581c8-120">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="581c8-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="581c8-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="581c8-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
