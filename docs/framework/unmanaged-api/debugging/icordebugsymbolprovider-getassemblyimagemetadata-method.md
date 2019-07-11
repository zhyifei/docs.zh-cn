---
title: ICorDebugSymbolProvider::GetAssemblyImageMetadata 方法
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d96aa82e9fd8b651ab005cba4945f6977c1e3d3a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771502"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="f1200-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata 方法</span><span class="sxs-lookup"><span data-stu-id="f1200-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="f1200-103">返回合并程序集中的元数据。</span><span class="sxs-lookup"><span data-stu-id="f1200-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1200-104">语法</span><span class="sxs-lookup"><span data-stu-id="f1200-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1200-105">参数</span><span class="sxs-lookup"><span data-stu-id="f1200-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="f1200-106">[out]指向的地址的指针[ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)对象，其中包含有关大小和合并程序集的元数据地址信息。</span><span class="sxs-lookup"><span data-stu-id="f1200-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1200-107">备注</span><span class="sxs-lookup"><span data-stu-id="f1200-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1200-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="f1200-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1200-109">要求</span><span class="sxs-lookup"><span data-stu-id="f1200-109">Requirements</span></span>  
 <span data-ttu-id="f1200-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f1200-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1200-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1200-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1200-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1200-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1200-113">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1200-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1200-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1200-114">See also</span></span>

- [<span data-ttu-id="f1200-115">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="f1200-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="f1200-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="f1200-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
