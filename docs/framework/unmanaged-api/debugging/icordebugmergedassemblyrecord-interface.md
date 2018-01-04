---
title: "ICorDebugMergedAssemblyRecord 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6086d1a82b5f086d857ac612a9d454a6ed77ba1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="f90a6-102">ICorDebugMergedAssemblyRecord 接口</span><span class="sxs-lookup"><span data-stu-id="f90a6-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="f90a6-103">提供有关合并的程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="f90a6-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f90a6-104">方法</span><span class="sxs-lookup"><span data-stu-id="f90a6-104">Methods</span></span>  
  
|<span data-ttu-id="f90a6-105">方法</span><span class="sxs-lookup"><span data-stu-id="f90a6-105">Method</span></span>|<span data-ttu-id="f90a6-106">描述</span><span class="sxs-lookup"><span data-stu-id="f90a6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f90a6-107">GetCulture 方法</span><span class="sxs-lookup"><span data-stu-id="f90a6-107">GetCulture Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="f90a6-108">获取程序集的区域性名称字符串。</span><span class="sxs-lookup"><span data-stu-id="f90a6-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="f90a6-109">GetIndex 方法</span><span class="sxs-lookup"><span data-stu-id="f90a6-109">GetIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="f90a6-110">获取程序集的前缀索引。</span><span class="sxs-lookup"><span data-stu-id="f90a6-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="f90a6-111">GetPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="f90a6-111">GetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="f90a6-112">获取程序集的公钥。</span><span class="sxs-lookup"><span data-stu-id="f90a6-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="f90a6-113">GetPublicKeyToken 方法</span><span class="sxs-lookup"><span data-stu-id="f90a6-113">GetPublicKeyToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="f90a6-114">获取程序集的公钥标记。</span><span class="sxs-lookup"><span data-stu-id="f90a6-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="f90a6-115">GetSimpleName 方法</span><span class="sxs-lookup"><span data-stu-id="f90a6-115">GetSimpleName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="f90a6-116">获取程序集的简单名。</span><span class="sxs-lookup"><span data-stu-id="f90a6-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="f90a6-117">GetVersion 方法</span><span class="sxs-lookup"><span data-stu-id="f90a6-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="f90a6-118">获取程序集的版本信息。</span><span class="sxs-lookup"><span data-stu-id="f90a6-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f90a6-119">备注</span><span class="sxs-lookup"><span data-stu-id="f90a6-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f90a6-120">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="f90a6-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="f90a6-121">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="f90a6-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f90a6-122">惠?</span><span class="sxs-lookup"><span data-stu-id="f90a6-122">Requirements</span></span>  
 <span data-ttu-id="f90a6-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f90a6-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f90a6-124">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f90a6-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f90a6-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f90a6-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f90a6-126">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f90a6-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f90a6-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="f90a6-127">See Also</span></span>  
 [<span data-ttu-id="f90a6-128">调试接口</span><span class="sxs-lookup"><span data-stu-id="f90a6-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="f90a6-129">调试</span><span class="sxs-lookup"><span data-stu-id="f90a6-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
