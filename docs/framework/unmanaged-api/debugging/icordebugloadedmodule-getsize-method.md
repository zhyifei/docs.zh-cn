---
title: ICorDebugLoadedModule::GetSize 方法
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4601261971cce32b6d6d9ee7377f725a85103a1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183464"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="0bace-102">ICorDebugLoadedModule::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="0bace-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="0bace-103">获取加载模块的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="0bace-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bace-104">语法</span><span class="sxs-lookup"><span data-stu-id="0bace-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0bace-105">参数</span><span class="sxs-lookup"><span data-stu-id="0bace-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="0bace-106">[out] 指向已加载模块中字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="0bace-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bace-107">备注</span><span class="sxs-lookup"><span data-stu-id="0bace-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bace-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="0bace-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bace-109">要求</span><span class="sxs-lookup"><span data-stu-id="0bace-109">Requirements</span></span>  
 <span data-ttu-id="0bace-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0bace-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bace-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0bace-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0bace-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bace-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0bace-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="0bace-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0bace-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="0bace-114">See also</span></span>

- [<span data-ttu-id="0bace-115">ICorDebugLoadedModule 接口</span><span class="sxs-lookup"><span data-stu-id="0bace-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="0bace-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="0bace-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
