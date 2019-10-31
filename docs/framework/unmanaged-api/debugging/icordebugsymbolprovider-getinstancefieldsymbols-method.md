---
title: ICorDebugSymbolProvider：： GetInstanceFieldSymbols 方法
ms.date: 03/30/2017
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
ms.openlocfilehash: 0ad8ddd78d963681c0b2f69bf0f211ad464dc7b7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138875"
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a><span data-ttu-id="1ee8e-102">ICorDebugSymbolProvider：： GetInstanceFieldSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="1ee8e-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols Method</span></span>
<span data-ttu-id="1ee8e-103">获取与 Typespec 签名相对应的实例字段符号。</span><span class="sxs-lookup"><span data-stu-id="1ee8e-103">Gets the instance field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ee8e-104">语法</span><span class="sxs-lookup"><span data-stu-id="1ee8e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ee8e-105">参数</span><span class="sxs-lookup"><span data-stu-id="1ee8e-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="1ee8e-106">[in] `typeSig` 数组中的字节数。</span><span class="sxs-lookup"><span data-stu-id="1ee8e-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="1ee8e-107">[in] 包含 `typespec` 签名的字节数组。</span><span class="sxs-lookup"><span data-stu-id="1ee8e-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="1ee8e-108">[in] 请求的符号数。</span><span class="sxs-lookup"><span data-stu-id="1ee8e-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="1ee8e-109">[out] 一个指针，指向由方法检索的符号的数量。</span><span class="sxs-lookup"><span data-stu-id="1ee8e-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="1ee8e-110">弄指向[ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)数组的指针，该数组包含请求的实例字段符号。</span><span class="sxs-lookup"><span data-stu-id="1ee8e-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) array that contains the requested instance field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ee8e-111">备注</span><span class="sxs-lookup"><span data-stu-id="1ee8e-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1ee8e-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="1ee8e-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ee8e-113">要求</span><span class="sxs-lookup"><span data-stu-id="1ee8e-113">Requirements</span></span>  
 <span data-ttu-id="1ee8e-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1ee8e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ee8e-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ee8e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ee8e-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ee8e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ee8e-117">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ee8e-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ee8e-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ee8e-118">See also</span></span>

- [<span data-ttu-id="1ee8e-119">GetStaticFieldSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="1ee8e-119">GetStaticFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)
- [<span data-ttu-id="1ee8e-120">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="1ee8e-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="1ee8e-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="1ee8e-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
