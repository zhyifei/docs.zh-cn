---
title: ICorDebugMergedAssemblyRecord：： GetPublicKey 方法
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
ms.openlocfilehash: 9cf5f6b6d12303b3f59588c5fb663c457da79cb9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131399"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="83b5b-102">ICorDebugMergedAssemblyRecord：： GetPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="83b5b-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="83b5b-103">获取程序集的公钥。</span><span class="sxs-lookup"><span data-stu-id="83b5b-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83b5b-104">语法</span><span class="sxs-lookup"><span data-stu-id="83b5b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83b5b-105">参数</span><span class="sxs-lookup"><span data-stu-id="83b5b-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="83b5b-106">[in] `pbPublicKey` 数组中的最大字节数。</span><span class="sxs-lookup"><span data-stu-id="83b5b-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="83b5b-107">[out] 指向写入 `pbPublicKey` 数组的实际字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="83b5b-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="83b5b-108">[out] 指向包含程序集公钥的字节数组的指针。</span><span class="sxs-lookup"><span data-stu-id="83b5b-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83b5b-109">备注</span><span class="sxs-lookup"><span data-stu-id="83b5b-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="83b5b-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="83b5b-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83b5b-111">要求</span><span class="sxs-lookup"><span data-stu-id="83b5b-111">Requirements</span></span>  
 <span data-ttu-id="83b5b-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="83b5b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83b5b-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83b5b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83b5b-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83b5b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83b5b-115">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83b5b-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83b5b-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="83b5b-116">See also</span></span>

- [<span data-ttu-id="83b5b-117">ICorDebugMergedAssemblyRecord 接口</span><span class="sxs-lookup"><span data-stu-id="83b5b-117">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="83b5b-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="83b5b-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
