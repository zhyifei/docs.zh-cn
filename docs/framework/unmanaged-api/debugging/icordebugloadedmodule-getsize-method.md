---
title: ICorDebugLoadedModule::GetSize 方法
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
ms.openlocfilehash: f207cd1c612b6444a9512adaa356ac2d01de7b9f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788464"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="410c6-102">ICorDebugLoadedModule::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="410c6-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="410c6-103">获取加载模块的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="410c6-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="410c6-104">语法</span><span class="sxs-lookup"><span data-stu-id="410c6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="410c6-105">参数</span><span class="sxs-lookup"><span data-stu-id="410c6-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="410c6-106">[out] 指向已加载模块中字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="410c6-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="410c6-107">备注</span><span class="sxs-lookup"><span data-stu-id="410c6-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="410c6-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="410c6-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="410c6-109">需求</span><span class="sxs-lookup"><span data-stu-id="410c6-109">Requirements</span></span>  
 <span data-ttu-id="410c6-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="410c6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="410c6-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="410c6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="410c6-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="410c6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="410c6-113">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="410c6-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="410c6-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="410c6-114">See also</span></span>

- [<span data-ttu-id="410c6-115">ICorDebugLoadedModule 接口</span><span class="sxs-lookup"><span data-stu-id="410c6-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="410c6-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="410c6-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
