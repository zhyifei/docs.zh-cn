---
title: 'Icordebugmergedassemblyrecord:: Getpublickey 方法'
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 610e46d5cb550a266c5558c49239d1818c1e85de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107271"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="19517-102">Icordebugmergedassemblyrecord:: Getpublickey 方法</span><span class="sxs-lookup"><span data-stu-id="19517-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="19517-103">获取程序集的公钥。</span><span class="sxs-lookup"><span data-stu-id="19517-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19517-104">语法</span><span class="sxs-lookup"><span data-stu-id="19517-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19517-105">参数</span><span class="sxs-lookup"><span data-stu-id="19517-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="19517-106">[in] `pbPublicKey` 数组中的最大字节数。</span><span class="sxs-lookup"><span data-stu-id="19517-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="19517-107">[out] 指向写入 `pbPublicKey` 数组的实际字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="19517-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="19517-108">[out] 指向包含程序集公钥的字节数组的指针。</span><span class="sxs-lookup"><span data-stu-id="19517-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19517-109">备注</span><span class="sxs-lookup"><span data-stu-id="19517-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19517-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="19517-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19517-111">要求</span><span class="sxs-lookup"><span data-stu-id="19517-111">Requirements</span></span>  
 <span data-ttu-id="19517-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="19517-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19517-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19517-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19517-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19517-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19517-115">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19517-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19517-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="19517-116">See also</span></span>

- [<span data-ttu-id="19517-117">ICorDebugMergedAssemblyRecord 接口</span><span class="sxs-lookup"><span data-stu-id="19517-117">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="19517-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="19517-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
