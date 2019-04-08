---
title: ICorDebugSymbolProvider2::GetFrameProps 方法
ms.date: 03/30/2017
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b20d78abbfa1db43047872a596289028833de37d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098983"
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a><span data-ttu-id="6b18b-102">ICorDebugSymbolProvider2::GetFrameProps 方法</span><span class="sxs-lookup"><span data-stu-id="6b18b-102">ICorDebugSymbolProvider2::GetFrameProps Method</span></span>
<span data-ttu-id="6b18b-103">返回启动方法相对虚拟地址的方法和具有代码相对虚拟地址的父框架。</span><span class="sxs-lookup"><span data-stu-id="6b18b-103">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b18b-104">语法</span><span class="sxs-lookup"><span data-stu-id="6b18b-104">Syntax</span></span>  
  
```  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b18b-105">参数</span><span class="sxs-lookup"><span data-stu-id="6b18b-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="6b18b-106">[in] 代码相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="6b18b-106">[in] A code relative virtual address.</span></span>  
  
 `pCodeStartRva`  
 <span data-ttu-id="6b18b-107">[out] 指向方法的启动相对虚拟地址的指针。</span><span class="sxs-lookup"><span data-stu-id="6b18b-107">[out] A pointer to the method's starting relative virtual address.</span></span>  
  
 `pParentFrameStartRva`  
 <span data-ttu-id="6b18b-108">[out] 指向框架的启动相对虚拟地址的指针。</span><span class="sxs-lookup"><span data-stu-id="6b18b-108">[out] A pointer to the frame's starting relative virtual address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b18b-109">备注</span><span class="sxs-lookup"><span data-stu-id="6b18b-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b18b-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="6b18b-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b18b-111">要求</span><span class="sxs-lookup"><span data-stu-id="6b18b-111">Requirements</span></span>  
 <span data-ttu-id="6b18b-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6b18b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b18b-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b18b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b18b-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b18b-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6b18b-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="6b18b-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6b18b-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b18b-116">See also</span></span>

- [<span data-ttu-id="6b18b-117">ICorDebugSymbolProvider2 接口</span><span class="sxs-lookup"><span data-stu-id="6b18b-117">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="6b18b-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="6b18b-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
