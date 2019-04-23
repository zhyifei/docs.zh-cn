---
title: ICorDebugMergedAssemblyRecord::GetVersion 方法
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36cf8647b3caafeaae2db3c2fd53471496e922fa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109534"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="bb418-102">ICorDebugMergedAssemblyRecord::GetVersion 方法</span><span class="sxs-lookup"><span data-stu-id="bb418-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="bb418-103">获取程序集的版本信息。</span><span class="sxs-lookup"><span data-stu-id="bb418-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb418-104">语法</span><span class="sxs-lookup"><span data-stu-id="bb418-104">Syntax</span></span>  
  
```  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb418-105">参数</span><span class="sxs-lookup"><span data-stu-id="bb418-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="bb418-106">[out] 指向主版本号的指针。</span><span class="sxs-lookup"><span data-stu-id="bb418-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="bb418-107">[out] 指向次版本号的指针。</span><span class="sxs-lookup"><span data-stu-id="bb418-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="bb418-108">[out] 指向内部版本号的指针。</span><span class="sxs-lookup"><span data-stu-id="bb418-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="bb418-109">[out] 指向修订号的指针。</span><span class="sxs-lookup"><span data-stu-id="bb418-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb418-110">备注</span><span class="sxs-lookup"><span data-stu-id="bb418-110">Remarks</span></span>  
 <span data-ttu-id="bb418-111">有关程序集版本号的信息，请参阅 <xref:System.Version> 类主题。</span><span class="sxs-lookup"><span data-stu-id="bb418-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb418-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="bb418-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb418-113">要求</span><span class="sxs-lookup"><span data-stu-id="bb418-113">Requirements</span></span>  
 <span data-ttu-id="bb418-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bb418-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb418-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb418-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb418-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb418-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb418-117">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb418-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb418-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb418-118">See also</span></span>

- [<span data-ttu-id="bb418-119">ICorDebugMergedAssemblyRecord 接口</span><span class="sxs-lookup"><span data-stu-id="bb418-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="bb418-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="bb418-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
