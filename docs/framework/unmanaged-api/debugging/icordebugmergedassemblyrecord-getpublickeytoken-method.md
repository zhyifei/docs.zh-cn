---
title: ICorDebugMergedAssemblyRecord::GetPublicKeyToken 方法
ms.date: 03/30/2017
ms.assetid: 72020b72-9611-4bc3-b1e7-5a16b023bfa3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 726ded615fb6d1bcd0a3a4b92e93f3675d9ce8fa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484558"
---
# <a name="icordebugmergedassemblyrecordgetpublickeytoken-method"></a><span data-ttu-id="7ba9f-102">ICorDebugMergedAssemblyRecord::GetPublicKeyToken 方法</span><span class="sxs-lookup"><span data-stu-id="7ba9f-102">ICorDebugMergedAssemblyRecord::GetPublicKeyToken Method</span></span>
<span data-ttu-id="7ba9f-103">获取程序集的公钥标记。</span><span class="sxs-lookup"><span data-stu-id="7ba9f-103">Gets the assembly's public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ba9f-104">语法</span><span class="sxs-lookup"><span data-stu-id="7ba9f-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
   [in] ULONG32 cbPublicKeyToken,   
   [out] ULONG32 *pcbPublicKeyToken,   
   [out, size_is(cbPublicKeyToken), length_is(*pcbPublicKeyToken)] BYTE pbPublicKeyToken[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ba9f-105">参数</span><span class="sxs-lookup"><span data-stu-id="7ba9f-105">Parameters</span></span>  
 `cbPublicKeyToken`  
 <span data-ttu-id="7ba9f-106">[in] `pbPublicKeyToken` 数组中的最大字节数。</span><span class="sxs-lookup"><span data-stu-id="7ba9f-106">[in] The maximum number of bytes in the `pbPublicKeyToken` array.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="7ba9f-107">[out] 指向写入 `pbPublicKeyToken` 数组的实际字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="7ba9f-107">[out] A pointer to the actual number of bytes written to the `pbPublicKeyToken` array.</span></span>  
  
 `pbPublicKeyToken`  
 <span data-ttu-id="7ba9f-108">[out] 指向包含程序集公钥标记的字节数组的指针。</span><span class="sxs-lookup"><span data-stu-id="7ba9f-108">[out] A pointer to a byte array that contains the assembly's public key token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ba9f-109">备注</span><span class="sxs-lookup"><span data-stu-id="7ba9f-109">Remarks</span></span>  
 <span data-ttu-id="7ba9f-110">程序集的公钥标记是指其公钥中 SHA1 哈希的最后 8 个字节。</span><span class="sxs-lookup"><span data-stu-id="7ba9f-110">An assembly's public key token is the last eight bytes of a SHA1 hash of its public key.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ba9f-111">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="7ba9f-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ba9f-112">要求</span><span class="sxs-lookup"><span data-stu-id="7ba9f-112">Requirements</span></span>  
 <span data-ttu-id="7ba9f-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7ba9f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ba9f-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ba9f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ba9f-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ba9f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ba9f-116">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ba9f-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ba9f-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ba9f-117">See also</span></span>
- [<span data-ttu-id="7ba9f-118">ICorDebugMergedAssemblyRecord 接口</span><span class="sxs-lookup"><span data-stu-id="7ba9f-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="7ba9f-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="7ba9f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
