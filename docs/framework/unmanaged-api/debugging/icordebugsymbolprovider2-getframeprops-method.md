---
title: "ICorDebugSymbolProvider2::GetFrameProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f74ed8cdd7448d7ebeaa98108e84b42e86f428b1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a><span data-ttu-id="47d86-102">ICorDebugSymbolProvider2::GetFrameProps 方法</span><span class="sxs-lookup"><span data-stu-id="47d86-102">ICorDebugSymbolProvider2::GetFrameProps Method</span></span>
<span data-ttu-id="47d86-103">返回启动方法相对虚拟地址的方法和具有代码相对虚拟地址的父框架。</span><span class="sxs-lookup"><span data-stu-id="47d86-103">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47d86-104">语法</span><span class="sxs-lookup"><span data-stu-id="47d86-104">Syntax</span></span>  
  
```  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47d86-105">参数</span><span class="sxs-lookup"><span data-stu-id="47d86-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="47d86-106">[in] 代码相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="47d86-106">[in] A code relative virtual address.</span></span>  
  
 `pCodeStartRva`  
 <span data-ttu-id="47d86-107">[out] 指向方法的启动相对虚拟地址的指针。</span><span class="sxs-lookup"><span data-stu-id="47d86-107">[out] A pointer to the method's starting relative virtual address.</span></span>  
  
 `pParentFrameStartRva`  
 <span data-ttu-id="47d86-108">[out] 指向框架的启动相对虚拟地址的指针。</span><span class="sxs-lookup"><span data-stu-id="47d86-108">[out] A pointer to the frame's starting relative virtual address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47d86-109">备注</span><span class="sxs-lookup"><span data-stu-id="47d86-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47d86-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="47d86-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47d86-111">惠?</span><span class="sxs-lookup"><span data-stu-id="47d86-111">Requirements</span></span>  
 <span data-ttu-id="47d86-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="47d86-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47d86-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47d86-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47d86-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47d86-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47d86-115">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47d86-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47d86-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="47d86-116">See Also</span></span>  
 [<span data-ttu-id="47d86-117">ICorDebugSymbolProvider2 接口</span><span class="sxs-lookup"><span data-stu-id="47d86-117">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 [<span data-ttu-id="47d86-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="47d86-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
