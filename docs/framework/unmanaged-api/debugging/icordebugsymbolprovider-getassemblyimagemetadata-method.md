---
title: "ICorDebugSymbolProvider::GetAssemblyImageMetadata 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 48e5e9daf191cb2f4112dd2a957f29c0a7521398
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="7ee86-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata 方法</span><span class="sxs-lookup"><span data-stu-id="7ee86-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="7ee86-103">返回合并程序集中的元数据。</span><span class="sxs-lookup"><span data-stu-id="7ee86-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ee86-104">语法</span><span class="sxs-lookup"><span data-stu-id="7ee86-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7ee86-105">参数</span><span class="sxs-lookup"><span data-stu-id="7ee86-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="7ee86-106">[out]指向的地址的指针[ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)对象，其中包含有关大小和合并程序集的元数据地址的信息。</span><span class="sxs-lookup"><span data-stu-id="7ee86-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ee86-107">备注</span><span class="sxs-lookup"><span data-stu-id="7ee86-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ee86-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="7ee86-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ee86-109">要求</span><span class="sxs-lookup"><span data-stu-id="7ee86-109">Requirements</span></span>  
 <span data-ttu-id="7ee86-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7ee86-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ee86-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ee86-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ee86-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ee86-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ee86-113">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ee86-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ee86-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ee86-114">See Also</span></span>  
 [<span data-ttu-id="7ee86-115">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="7ee86-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="7ee86-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="7ee86-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
