---
title: ICorDebugSymbolProvider::GetCodeRange 方法
ms.date: 03/30/2017
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
ms.openlocfilehash: dbe042641cadae182efac30502a70631be359bbe
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791644"
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a><span data-ttu-id="c9b65-102">ICorDebugSymbolProvider::GetCodeRange 方法</span><span class="sxs-lookup"><span data-stu-id="c9b65-102">ICorDebugSymbolProvider::GetCodeRange Method</span></span>
<span data-ttu-id="c9b65-103">给定方法的相对虚拟地址 (RVA)，获取该方法的起始地址和大小。</span><span class="sxs-lookup"><span data-stu-id="c9b65-103">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9b65-104">语法</span><span class="sxs-lookup"><span data-stu-id="c9b65-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,   
   [out] ULONG32* pCodeStartAddress,   
   [out] ULONG32* pCodeSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9b65-105">参数</span><span class="sxs-lookup"><span data-stu-id="c9b65-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="c9b65-106">[in] 方法中的相对虚拟地址 (RVA)。</span><span class="sxs-lookup"><span data-stu-id="c9b65-106">[in] The relative virtual address (RVA) in a method.</span></span>  
  
 `pCodeStartAddress`  
 <span data-ttu-id="c9b65-107">[out] 指向该方法的起始地址的指针。</span><span class="sxs-lookup"><span data-stu-id="c9b65-107">[out] A pointer to the starting address of the method.</span></span>  
  
 `pCodeSize`  
 <span data-ttu-id="c9b65-108">指向方法代码大小（该方法的代码的字节数）的指针。</span><span class="sxs-lookup"><span data-stu-id="c9b65-108">A pointer to the method code size (the number of bytes of the method's code).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9b65-109">备注</span><span class="sxs-lookup"><span data-stu-id="c9b65-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c9b65-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="c9b65-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9b65-111">需求</span><span class="sxs-lookup"><span data-stu-id="c9b65-111">Requirements</span></span>  
 <span data-ttu-id="c9b65-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c9b65-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9b65-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9b65-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9b65-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9b65-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9b65-115">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9b65-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9b65-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9b65-116">See also</span></span>

- [<span data-ttu-id="c9b65-117">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="c9b65-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="c9b65-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="c9b65-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
