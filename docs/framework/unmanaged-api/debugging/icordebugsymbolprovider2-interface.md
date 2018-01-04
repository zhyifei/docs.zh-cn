---
title: "ICorDebugSymbolProvider2 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7666b8d64b689d3640594f07614be97b72e85a8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="b7eef-102">ICorDebugSymbolProvider2 接口</span><span class="sxs-lookup"><span data-stu-id="b7eef-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="b7eef-103">合理扩展[ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)接口以检索其他调试符号信息。</span><span class="sxs-lookup"><span data-stu-id="b7eef-103">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b7eef-104">方法</span><span class="sxs-lookup"><span data-stu-id="b7eef-104">Methods</span></span>  
  
|<span data-ttu-id="b7eef-105">方法</span><span class="sxs-lookup"><span data-stu-id="b7eef-105">Method</span></span>|<span data-ttu-id="b7eef-106">描述</span><span class="sxs-lookup"><span data-stu-id="b7eef-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b7eef-107">GetFrameProps 方法</span><span class="sxs-lookup"><span data-stu-id="b7eef-107">GetFrameProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="b7eef-108">返回启动方法相对虚拟地址的方法和具有代码相对虚拟地址的父框架。</span><span class="sxs-lookup"><span data-stu-id="b7eef-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="b7eef-109">GetGenericDictionaryInfo 方法</span><span class="sxs-lookup"><span data-stu-id="b7eef-109">GetGenericDictionaryInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="b7eef-110">检索泛型字典映射。</span><span class="sxs-lookup"><span data-stu-id="b7eef-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7eef-111">备注</span><span class="sxs-lookup"><span data-stu-id="b7eef-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7eef-112">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="b7eef-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="b7eef-113">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="b7eef-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7eef-114">惠?</span><span class="sxs-lookup"><span data-stu-id="b7eef-114">Requirements</span></span>  
 <span data-ttu-id="b7eef-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b7eef-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7eef-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7eef-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7eef-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7eef-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7eef-118">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7eef-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7eef-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7eef-119">See Also</span></span>  
 [<span data-ttu-id="b7eef-120">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="b7eef-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="b7eef-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="b7eef-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="b7eef-122">调试</span><span class="sxs-lookup"><span data-stu-id="b7eef-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
