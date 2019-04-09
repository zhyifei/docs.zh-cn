---
title: ICorDebugSymbolProvider::GetAssemblyImageMetadata 方法
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0be0722db374ff49541b3c4b68f295774f34163e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104125"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="05f4b-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata 方法</span><span class="sxs-lookup"><span data-stu-id="05f4b-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="05f4b-103">返回合并程序集中的元数据。</span><span class="sxs-lookup"><span data-stu-id="05f4b-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05f4b-104">语法</span><span class="sxs-lookup"><span data-stu-id="05f4b-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05f4b-105">参数</span><span class="sxs-lookup"><span data-stu-id="05f4b-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="05f4b-106">[out]指向的地址的指针[ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)对象，其中包含有关大小和合并程序集的元数据地址信息。</span><span class="sxs-lookup"><span data-stu-id="05f4b-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05f4b-107">备注</span><span class="sxs-lookup"><span data-stu-id="05f4b-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05f4b-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="05f4b-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05f4b-109">要求</span><span class="sxs-lookup"><span data-stu-id="05f4b-109">Requirements</span></span>  
 <span data-ttu-id="05f4b-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="05f4b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05f4b-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05f4b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05f4b-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05f4b-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="05f4b-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="05f4b-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="05f4b-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="05f4b-114">See also</span></span>

- [<span data-ttu-id="05f4b-115">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="05f4b-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="05f4b-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="05f4b-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
