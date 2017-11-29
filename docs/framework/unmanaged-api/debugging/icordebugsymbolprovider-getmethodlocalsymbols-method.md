---
title: "ICorDebugSymbolProvider::GetMethodLocalSymbols 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3533157f25bda881fdbd0c77186c590d5a49f8c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="b4e99-102">ICorDebugSymbolProvider::GetMethodLocalSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="b4e99-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>
<span data-ttu-id="b4e99-103">给定方法的相对虚拟地址 (RVA)，获取该方法的本地符号。</span><span class="sxs-lookup"><span data-stu-id="b4e99-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4e99-104">语法</span><span class="sxs-lookup"><span data-stu-id="b4e99-104">Syntax</span></span>  
  
```  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4e99-105">参数</span><span class="sxs-lookup"><span data-stu-id="b4e99-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="b4e99-106">[in] 方法的本机相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="b4e99-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="b4e99-107">[in] 请求的本地符号数。</span><span class="sxs-lookup"><span data-stu-id="b4e99-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="b4e99-108">[out] 一个指针，指向由方法检索的符号的数量。</span><span class="sxs-lookup"><span data-stu-id="b4e99-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="b4e99-109">[out]指向的指针[ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)数组，其中包含方法的本地符号。</span><span class="sxs-lookup"><span data-stu-id="b4e99-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4e99-110">备注</span><span class="sxs-lookup"><span data-stu-id="b4e99-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4e99-111">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="b4e99-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4e99-112">要求</span><span class="sxs-lookup"><span data-stu-id="b4e99-112">Requirements</span></span>  
 <span data-ttu-id="b4e99-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e99-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4e99-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4e99-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4e99-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4e99-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4e99-116">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4e99-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4e99-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4e99-117">See Also</span></span>  
 [<span data-ttu-id="b4e99-118">GetMethodParameterSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="b4e99-118">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)  
 [<span data-ttu-id="b4e99-119">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="b4e99-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="b4e99-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="b4e99-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
