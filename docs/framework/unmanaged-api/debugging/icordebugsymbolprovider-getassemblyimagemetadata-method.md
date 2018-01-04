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
ms.workload: dotnet
ms.openlocfilehash: ff6b26dd9a0ed56e5194dc997270cf9d2dbe42b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="832b7-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata 方法</span><span class="sxs-lookup"><span data-stu-id="832b7-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="832b7-103">返回合并程序集中的元数据。</span><span class="sxs-lookup"><span data-stu-id="832b7-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="832b7-104">语法</span><span class="sxs-lookup"><span data-stu-id="832b7-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="832b7-105">参数</span><span class="sxs-lookup"><span data-stu-id="832b7-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="832b7-106">[out]指向的地址的指针[ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)对象，其中包含有关大小和合并程序集的元数据地址的信息。</span><span class="sxs-lookup"><span data-stu-id="832b7-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="832b7-107">备注</span><span class="sxs-lookup"><span data-stu-id="832b7-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="832b7-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="832b7-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="832b7-109">惠?</span><span class="sxs-lookup"><span data-stu-id="832b7-109">Requirements</span></span>  
 <span data-ttu-id="832b7-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="832b7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="832b7-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="832b7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="832b7-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="832b7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="832b7-113">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="832b7-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="832b7-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="832b7-114">See Also</span></span>  
 [<span data-ttu-id="832b7-115">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="832b7-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="832b7-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="832b7-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
