---
title: ICorDebugSymbolProvider2 接口
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea60ecd542300bf3833c4977b7f0910399a2e409
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504023"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="80e36-102">ICorDebugSymbolProvider2 接口</span><span class="sxs-lookup"><span data-stu-id="80e36-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="80e36-103">进行逻辑扩展[ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)接口来检索其他调试符号信息。</span><span class="sxs-lookup"><span data-stu-id="80e36-103">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="80e36-104">方法</span><span class="sxs-lookup"><span data-stu-id="80e36-104">Methods</span></span>  
  
|<span data-ttu-id="80e36-105">方法</span><span class="sxs-lookup"><span data-stu-id="80e36-105">Method</span></span>|<span data-ttu-id="80e36-106">描述</span><span class="sxs-lookup"><span data-stu-id="80e36-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80e36-107">GetFrameProps 方法</span><span class="sxs-lookup"><span data-stu-id="80e36-107">GetFrameProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="80e36-108">返回启动方法相对虚拟地址的方法和具有代码相对虚拟地址的父框架。</span><span class="sxs-lookup"><span data-stu-id="80e36-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="80e36-109">GetGenericDictionaryInfo 方法</span><span class="sxs-lookup"><span data-stu-id="80e36-109">GetGenericDictionaryInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="80e36-110">检索泛型字典映射。</span><span class="sxs-lookup"><span data-stu-id="80e36-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80e36-111">备注</span><span class="sxs-lookup"><span data-stu-id="80e36-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80e36-112">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="80e36-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="80e36-113">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="80e36-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80e36-114">要求</span><span class="sxs-lookup"><span data-stu-id="80e36-114">Requirements</span></span>  
 <span data-ttu-id="80e36-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="80e36-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80e36-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80e36-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80e36-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80e36-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80e36-118">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80e36-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80e36-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="80e36-119">See also</span></span>
- [<span data-ttu-id="80e36-120">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="80e36-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="80e36-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="80e36-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="80e36-122">调试</span><span class="sxs-lookup"><span data-stu-id="80e36-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
