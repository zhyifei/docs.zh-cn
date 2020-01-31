---
title: ICorDebugMergedAssemblyRecord::GetVersion 方法
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
ms.openlocfilehash: 8b5995183be7f1c992cf3230e16456cb248eff0c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793078"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="3f362-102">ICorDebugMergedAssemblyRecord::GetVersion 方法</span><span class="sxs-lookup"><span data-stu-id="3f362-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="3f362-103">获取程序集的版本信息。</span><span class="sxs-lookup"><span data-stu-id="3f362-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f362-104">语法</span><span class="sxs-lookup"><span data-stu-id="3f362-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f362-105">参数</span><span class="sxs-lookup"><span data-stu-id="3f362-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="3f362-106">[out] 指向主版本号的指针。</span><span class="sxs-lookup"><span data-stu-id="3f362-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="3f362-107">[out] 指向次版本号的指针。</span><span class="sxs-lookup"><span data-stu-id="3f362-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="3f362-108">[out] 指向内部版本号的指针。</span><span class="sxs-lookup"><span data-stu-id="3f362-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="3f362-109">[out] 指向修订号的指针。</span><span class="sxs-lookup"><span data-stu-id="3f362-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f362-110">备注</span><span class="sxs-lookup"><span data-stu-id="3f362-110">Remarks</span></span>  
 <span data-ttu-id="3f362-111">有关程序集版本号的信息，请参阅 <xref:System.Version> 类主题。</span><span class="sxs-lookup"><span data-stu-id="3f362-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f362-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="3f362-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f362-113">需求</span><span class="sxs-lookup"><span data-stu-id="3f362-113">Requirements</span></span>  
 <span data-ttu-id="3f362-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3f362-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f362-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f362-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f362-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f362-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f362-117">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f362-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f362-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f362-118">See also</span></span>

- [<span data-ttu-id="3f362-119">ICorDebugMergedAssemblyRecord 接口</span><span class="sxs-lookup"><span data-stu-id="3f362-119">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="3f362-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="3f362-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
