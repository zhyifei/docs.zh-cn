---
title: ICorDebugSymbolProvider::GetMethodParameterSymbols 方法
ms.date: 03/30/2017
ms.assetid: 58b7c0b9-f6ad-4b49-b92d-0e421cfd0ec6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 98efd1446c88c3a6c004b5a3254c9db835a43804
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197368"
---
# <a name="icordebugsymbolprovidergetmethodparametersymbols-method"></a><span data-ttu-id="3c846-102">ICorDebugSymbolProvider::GetMethodParameterSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="3c846-102">ICorDebugSymbolProvider::GetMethodParameterSymbols Method</span></span>
<span data-ttu-id="3c846-103">给定方法的相对虚拟地址 (RVA) 后，获取该方法的参数符号。</span><span class="sxs-lookup"><span data-stu-id="3c846-103">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c846-104">语法</span><span class="sxs-lookup"><span data-stu-id="3c846-104">Syntax</span></span>  
  
```  
HRESULT GetMethodParameterSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c846-105">参数</span><span class="sxs-lookup"><span data-stu-id="3c846-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="3c846-106">[in] 方法的本机相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="3c846-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="3c846-107">[in] 请求的本地符号数。</span><span class="sxs-lookup"><span data-stu-id="3c846-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="3c846-108">[out] 一个指针，指向由方法检索的符号的数量。</span><span class="sxs-lookup"><span data-stu-id="3c846-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="3c846-109">[out]一个指向[ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)数组，其中包含的方法本地符号。</span><span class="sxs-lookup"><span data-stu-id="3c846-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c846-110">备注</span><span class="sxs-lookup"><span data-stu-id="3c846-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c846-111">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="3c846-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c846-112">要求</span><span class="sxs-lookup"><span data-stu-id="3c846-112">Requirements</span></span>  
 <span data-ttu-id="3c846-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3c846-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c846-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c846-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c846-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c846-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3c846-116">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="3c846-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3c846-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c846-117">See also</span></span>

- [<span data-ttu-id="3c846-118">GetMethodLocalSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="3c846-118">GetMethodLocalSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)
- [<span data-ttu-id="3c846-119">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="3c846-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="3c846-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="3c846-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
