---
title: ICorDebugSymbolProvider::GetCodeRange 方法
ms.date: 03/30/2017
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18fd8fdf9bcfa20b686ad1f04cd8dcc3b1c26de2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964642"
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a><span data-ttu-id="4f4dd-102">ICorDebugSymbolProvider::GetCodeRange 方法</span><span class="sxs-lookup"><span data-stu-id="4f4dd-102">ICorDebugSymbolProvider::GetCodeRange Method</span></span>
<span data-ttu-id="4f4dd-103">给定方法的相对虚拟地址 (RVA)，获取该方法的起始地址和大小。</span><span class="sxs-lookup"><span data-stu-id="4f4dd-103">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f4dd-104">语法</span><span class="sxs-lookup"><span data-stu-id="4f4dd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,   
   [out] ULONG32* pCodeStartAddress,   
   [out] ULONG32* pCodeSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f4dd-105">参数</span><span class="sxs-lookup"><span data-stu-id="4f4dd-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="4f4dd-106">[in] 方法中的相对虚拟地址 (RVA)。</span><span class="sxs-lookup"><span data-stu-id="4f4dd-106">[in] The relative virtual address (RVA) in a method.</span></span>  
  
 `pCodeStartAddress`  
 <span data-ttu-id="4f4dd-107">[out] 指向该方法的起始地址的指针。</span><span class="sxs-lookup"><span data-stu-id="4f4dd-107">[out] A pointer to the starting address of the method.</span></span>  
  
 `pCodeSize`  
 <span data-ttu-id="4f4dd-108">指向方法代码大小（该方法的代码的字节数）的指针。</span><span class="sxs-lookup"><span data-stu-id="4f4dd-108">A pointer to the method code size (the number of bytes of the method's code).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f4dd-109">备注</span><span class="sxs-lookup"><span data-stu-id="4f4dd-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f4dd-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="4f4dd-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f4dd-111">要求</span><span class="sxs-lookup"><span data-stu-id="4f4dd-111">Requirements</span></span>  
 <span data-ttu-id="4f4dd-112">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4f4dd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f4dd-113">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="4f4dd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f4dd-114">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f4dd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f4dd-115">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f4dd-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f4dd-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f4dd-116">See also</span></span>

- [<span data-ttu-id="4f4dd-117">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="4f4dd-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="4f4dd-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="4f4dd-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
