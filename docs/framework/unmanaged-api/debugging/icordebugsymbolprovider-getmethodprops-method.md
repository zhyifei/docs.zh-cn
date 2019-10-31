---
title: ICorDebugSymbolProvider：： GetMethodProps 方法
ms.date: 03/30/2017
ms.assetid: 8f836b80-b7a5-460b-bf76-5f0e45652aea
ms.openlocfilehash: 811106216e1e454ddf342af1578f74c80ba2acc9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138828"
---
# <a name="icordebugsymbolprovidergetmethodprops-method"></a><span data-ttu-id="f43c6-102">ICorDebugSymbolProvider：： GetMethodProps 方法</span><span class="sxs-lookup"><span data-stu-id="f43c6-102">ICorDebugSymbolProvider::GetMethodProps Method</span></span>
<span data-ttu-id="f43c6-103">给定方法的相对虚拟地址 (RVA)，返回有关该方法属性的信息，例如该方法的元数据标记及其泛型参数信息。</span><span class="sxs-lookup"><span data-stu-id="f43c6-103">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f43c6-104">语法</span><span class="sxs-lookup"><span data-stu-id="f43c6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodProps(  
   [in]  ULONG32 codeRva,  
   [out] mdToken *pMethodToken,  
   [out] ULONG32 *pcGenericParams,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f43c6-105">参数</span><span class="sxs-lookup"><span data-stu-id="f43c6-105">Parameters</span></span>  
 `codeRVA`  
 <span data-ttu-id="f43c6-106">[in] 方法中有关要检索哪些信息的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="f43c6-106">[in] A relative virtual address in the method about which information is to be retrieved.</span></span>  
  
 `pMethodToken`  
 <span data-ttu-id="f43c6-107">[out] 指向方法元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="f43c6-107">[out] A pointer to the method's metadata token.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="f43c6-108">[out] 指向与此方法关联的泛型参数个数的指针。</span><span class="sxs-lookup"><span data-stu-id="f43c6-108">[out] A pointer to the number of generic parameters associated with this method.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="f43c6-109">[in] `signature` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="f43c6-109">[in] The size of the `signature` array.</span></span> <span data-ttu-id="f43c6-110">请参见“备注”部分。</span><span class="sxs-lookup"><span data-stu-id="f43c6-110">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="f43c6-111">[out] 指向返回的 `signature` 数组的大小的指针。</span><span class="sxs-lookup"><span data-stu-id="f43c6-111">[out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="f43c6-112">[out] 保存所有泛型参数的 typespec 签名的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="f43c6-112">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f43c6-113">备注</span><span class="sxs-lookup"><span data-stu-id="f43c6-113">Remarks</span></span>  
 <span data-ttu-id="f43c6-114">若要获取方法的 `signature` 数组的所需大小，请将 `cbSignature` 参数设置为0，并将 `signature` 设置为**null**。</span><span class="sxs-lookup"><span data-stu-id="f43c6-114">To get the required size of the method's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="f43c6-115">当该方法返回时，`pcbSignature` 将包含 `signature` 数组所需的字节数。</span><span class="sxs-lookup"><span data-stu-id="f43c6-115">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f43c6-116">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="f43c6-116">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f43c6-117">要求</span><span class="sxs-lookup"><span data-stu-id="f43c6-117">Requirements</span></span>  
 <span data-ttu-id="f43c6-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f43c6-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f43c6-119">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f43c6-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f43c6-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f43c6-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f43c6-121">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f43c6-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f43c6-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="f43c6-122">See also</span></span>

- [<span data-ttu-id="f43c6-123">GetTypeProps 方法</span><span class="sxs-lookup"><span data-stu-id="f43c6-123">GetTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)
- [<span data-ttu-id="f43c6-124">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="f43c6-124">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="f43c6-125">调试接口</span><span class="sxs-lookup"><span data-stu-id="f43c6-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
