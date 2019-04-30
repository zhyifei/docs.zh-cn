---
title: ICorDebugSymbolProvider::GetMethodLocalSymbols 方法
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99f76bd19ef274c3d4207fdd071914b736314a3a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61953317"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="f1b1d-102">ICorDebugSymbolProvider::GetMethodLocalSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="f1b1d-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>
<span data-ttu-id="f1b1d-103">给定方法的相对虚拟地址 (RVA)，获取该方法的本地符号。</span><span class="sxs-lookup"><span data-stu-id="f1b1d-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1b1d-104">语法</span><span class="sxs-lookup"><span data-stu-id="f1b1d-104">Syntax</span></span>  
  
```  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1b1d-105">参数</span><span class="sxs-lookup"><span data-stu-id="f1b1d-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="f1b1d-106">[in] 方法的本机相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="f1b1d-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="f1b1d-107">[in] 请求的本地符号数。</span><span class="sxs-lookup"><span data-stu-id="f1b1d-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="f1b1d-108">[out] 一个指针，指向由方法检索的符号的数量。</span><span class="sxs-lookup"><span data-stu-id="f1b1d-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="f1b1d-109">[out]一个指向[ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)数组，其中包含的方法本地符号。</span><span class="sxs-lookup"><span data-stu-id="f1b1d-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1b1d-110">备注</span><span class="sxs-lookup"><span data-stu-id="f1b1d-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1b1d-111">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="f1b1d-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1b1d-112">要求</span><span class="sxs-lookup"><span data-stu-id="f1b1d-112">Requirements</span></span>  
 <span data-ttu-id="f1b1d-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f1b1d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1b1d-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1b1d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1b1d-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1b1d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1b1d-116">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1b1d-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1b1d-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1b1d-117">See also</span></span>

- [<span data-ttu-id="f1b1d-118">GetMethodParameterSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="f1b1d-118">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [<span data-ttu-id="f1b1d-119">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="f1b1d-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="f1b1d-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="f1b1d-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
