---
title: ICorDebugMergedAssemblyRecord::GetVersion 方法
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 762ac20c376f4161aa9c053f6e5213ba24c792ba
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499757"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="ec72b-102">ICorDebugMergedAssemblyRecord::GetVersion 方法</span><span class="sxs-lookup"><span data-stu-id="ec72b-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="ec72b-103">获取程序集的版本信息。</span><span class="sxs-lookup"><span data-stu-id="ec72b-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec72b-104">语法</span><span class="sxs-lookup"><span data-stu-id="ec72b-104">Syntax</span></span>  
  
```  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec72b-105">参数</span><span class="sxs-lookup"><span data-stu-id="ec72b-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="ec72b-106">[out] 指向主版本号的指针。</span><span class="sxs-lookup"><span data-stu-id="ec72b-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="ec72b-107">[out] 指向次版本号的指针。</span><span class="sxs-lookup"><span data-stu-id="ec72b-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="ec72b-108">[out] 指向内部版本号的指针。</span><span class="sxs-lookup"><span data-stu-id="ec72b-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="ec72b-109">[out] 指向修订号的指针。</span><span class="sxs-lookup"><span data-stu-id="ec72b-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec72b-110">备注</span><span class="sxs-lookup"><span data-stu-id="ec72b-110">Remarks</span></span>  
 <span data-ttu-id="ec72b-111">有关程序集版本号的信息，请参阅 <xref:System.Version> 类主题。</span><span class="sxs-lookup"><span data-stu-id="ec72b-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec72b-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="ec72b-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec72b-113">要求</span><span class="sxs-lookup"><span data-stu-id="ec72b-113">Requirements</span></span>  
 <span data-ttu-id="ec72b-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ec72b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec72b-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec72b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec72b-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec72b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec72b-117">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec72b-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec72b-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec72b-118">See also</span></span>
- [<span data-ttu-id="ec72b-119">ICorDebugMergedAssemblyRecord 接口</span><span class="sxs-lookup"><span data-stu-id="ec72b-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="ec72b-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="ec72b-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
