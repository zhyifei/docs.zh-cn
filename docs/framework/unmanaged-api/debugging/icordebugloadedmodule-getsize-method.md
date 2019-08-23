---
title: ICorDebugLoadedModule::GetSize 方法
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3067cdee1d3a5df0ad5594bce581139431fd1846
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936875"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="86c72-102">ICorDebugLoadedModule::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="86c72-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="86c72-103">获取加载模块的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="86c72-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86c72-104">语法</span><span class="sxs-lookup"><span data-stu-id="86c72-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86c72-105">参数</span><span class="sxs-lookup"><span data-stu-id="86c72-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="86c72-106">[out] 指向已加载模块中字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="86c72-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86c72-107">备注</span><span class="sxs-lookup"><span data-stu-id="86c72-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="86c72-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="86c72-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86c72-109">要求</span><span class="sxs-lookup"><span data-stu-id="86c72-109">Requirements</span></span>  
 <span data-ttu-id="86c72-110">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="86c72-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86c72-111">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="86c72-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86c72-112">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86c72-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86c72-113">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86c72-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86c72-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="86c72-114">See also</span></span>

- [<span data-ttu-id="86c72-115">ICorDebugLoadedModule 接口</span><span class="sxs-lookup"><span data-stu-id="86c72-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="86c72-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="86c72-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
