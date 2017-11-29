---
title: "ICorDebugLoadedModule::GetSize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 29adc45df57c5f31c299dc28b611bcf0599d4aac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="fcc87-102">ICorDebugLoadedModule::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="fcc87-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="fcc87-103">获取加载模块的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="fcc87-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcc87-104">语法</span><span class="sxs-lookup"><span data-stu-id="fcc87-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fcc87-105">参数</span><span class="sxs-lookup"><span data-stu-id="fcc87-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="fcc87-106">[out] 指向已加载模块中字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="fcc87-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcc87-107">备注</span><span class="sxs-lookup"><span data-stu-id="fcc87-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fcc87-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="fcc87-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcc87-109">要求</span><span class="sxs-lookup"><span data-stu-id="fcc87-109">Requirements</span></span>  
 <span data-ttu-id="fcc87-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fcc87-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcc87-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fcc87-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fcc87-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcc87-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcc87-113">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcc87-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcc87-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fcc87-114">See Also</span></span>  
 [<span data-ttu-id="fcc87-115">ICorDebugLoadedModule 接口</span><span class="sxs-lookup"><span data-stu-id="fcc87-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 [<span data-ttu-id="fcc87-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="fcc87-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
