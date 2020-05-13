---
title: ICorDebugMergedAssemblyRecord 接口
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: 721f6c1cf468b3b518d2ea213588ae2410249690
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208715"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="58741-102">ICorDebugMergedAssemblyRecord 接口</span><span class="sxs-lookup"><span data-stu-id="58741-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="58741-103">提供有关合并的程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="58741-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="58741-104">方法</span><span class="sxs-lookup"><span data-stu-id="58741-104">Methods</span></span>  
  
|<span data-ttu-id="58741-105">方法</span><span class="sxs-lookup"><span data-stu-id="58741-105">Method</span></span>|<span data-ttu-id="58741-106">描述</span><span class="sxs-lookup"><span data-stu-id="58741-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="58741-107">GetCulture 方法</span><span class="sxs-lookup"><span data-stu-id="58741-107">GetCulture Method</span></span>](icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="58741-108">获取程序集的区域性名称字符串。</span><span class="sxs-lookup"><span data-stu-id="58741-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="58741-109">GetIndex 方法</span><span class="sxs-lookup"><span data-stu-id="58741-109">GetIndex Method</span></span>](icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="58741-110">获取程序集的前缀索引。</span><span class="sxs-lookup"><span data-stu-id="58741-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="58741-111">GetPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="58741-111">GetPublicKey Method</span></span>](icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="58741-112">获取程序集的公钥。</span><span class="sxs-lookup"><span data-stu-id="58741-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="58741-113">GetPublicKeyToken 方法</span><span class="sxs-lookup"><span data-stu-id="58741-113">GetPublicKeyToken Method</span></span>](icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="58741-114">获取程序集的公钥标记。</span><span class="sxs-lookup"><span data-stu-id="58741-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="58741-115">GetSimpleName 方法</span><span class="sxs-lookup"><span data-stu-id="58741-115">GetSimpleName Method</span></span>](icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="58741-116">获取程序集的简单名。</span><span class="sxs-lookup"><span data-stu-id="58741-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="58741-117">GetVersion 方法</span><span class="sxs-lookup"><span data-stu-id="58741-117">GetVersion Method</span></span>](icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="58741-118">获取程序集的版本信息。</span><span class="sxs-lookup"><span data-stu-id="58741-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58741-119">备注</span><span class="sxs-lookup"><span data-stu-id="58741-119">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="58741-120">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="58741-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="58741-121">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="58741-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58741-122">要求</span><span class="sxs-lookup"><span data-stu-id="58741-122">Requirements</span></span>  
 <span data-ttu-id="58741-123">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="58741-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58741-124">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58741-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58741-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58741-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58741-126">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58741-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58741-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="58741-127">See also</span></span>

- [<span data-ttu-id="58741-128">调试接口</span><span class="sxs-lookup"><span data-stu-id="58741-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="58741-129">调试</span><span class="sxs-lookup"><span data-stu-id="58741-129">Debugging</span></span>](index.md)
