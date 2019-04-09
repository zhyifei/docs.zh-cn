---
title: ICorDebugMergedAssemblyRecord 接口
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1118c879da4376bda0c73368a8b15df4f7a3d014
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180461"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="545f0-102">ICorDebugMergedAssemblyRecord 接口</span><span class="sxs-lookup"><span data-stu-id="545f0-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="545f0-103">提供有关合并的程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="545f0-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="545f0-104">方法</span><span class="sxs-lookup"><span data-stu-id="545f0-104">Methods</span></span>  
  
|<span data-ttu-id="545f0-105">方法</span><span class="sxs-lookup"><span data-stu-id="545f0-105">Method</span></span>|<span data-ttu-id="545f0-106">描述</span><span class="sxs-lookup"><span data-stu-id="545f0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="545f0-107">GetCulture 方法</span><span class="sxs-lookup"><span data-stu-id="545f0-107">GetCulture Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="545f0-108">获取程序集的区域性名称字符串。</span><span class="sxs-lookup"><span data-stu-id="545f0-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="545f0-109">GetIndex 方法</span><span class="sxs-lookup"><span data-stu-id="545f0-109">GetIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="545f0-110">获取程序集的前缀索引。</span><span class="sxs-lookup"><span data-stu-id="545f0-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="545f0-111">GetPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="545f0-111">GetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="545f0-112">获取程序集的公钥。</span><span class="sxs-lookup"><span data-stu-id="545f0-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="545f0-113">GetPublicKeyToken 方法</span><span class="sxs-lookup"><span data-stu-id="545f0-113">GetPublicKeyToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="545f0-114">获取程序集的公钥标记。</span><span class="sxs-lookup"><span data-stu-id="545f0-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="545f0-115">GetSimpleName 方法</span><span class="sxs-lookup"><span data-stu-id="545f0-115">GetSimpleName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="545f0-116">获取程序集的简单名。</span><span class="sxs-lookup"><span data-stu-id="545f0-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="545f0-117">GetVersion 方法</span><span class="sxs-lookup"><span data-stu-id="545f0-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="545f0-118">获取程序集的版本信息。</span><span class="sxs-lookup"><span data-stu-id="545f0-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="545f0-119">备注</span><span class="sxs-lookup"><span data-stu-id="545f0-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="545f0-120">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="545f0-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="545f0-121">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="545f0-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="545f0-122">要求</span><span class="sxs-lookup"><span data-stu-id="545f0-122">Requirements</span></span>  
 <span data-ttu-id="545f0-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="545f0-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="545f0-124">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="545f0-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="545f0-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="545f0-125">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="545f0-126">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="545f0-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="545f0-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="545f0-127">See also</span></span>

- [<span data-ttu-id="545f0-128">调试接口</span><span class="sxs-lookup"><span data-stu-id="545f0-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="545f0-129">调试</span><span class="sxs-lookup"><span data-stu-id="545f0-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
