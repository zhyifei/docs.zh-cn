---
title: ICorDebugMergedAssemblyRecord::GetCulture 方法
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f2336c89a32b202c4226f1ed194d786be6fa020
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415352"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="b5e8d-102">ICorDebugMergedAssemblyRecord::GetCulture 方法</span><span class="sxs-lookup"><span data-stu-id="b5e8d-102">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>
<span data-ttu-id="b5e8d-103">获取程序集的区域性名称字符串。</span><span class="sxs-lookup"><span data-stu-id="b5e8d-103">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5e8d-104">语法</span><span class="sxs-lookup"><span data-stu-id="b5e8d-104">Syntax</span></span>  
  
```  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,   
   [out] ULONG32 *pcchCulture,   
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5e8d-105">参数</span><span class="sxs-lookup"><span data-stu-id="b5e8d-105">Parameters</span></span>  
 `cchCulture`  
 <span data-ttu-id="b5e8d-106">[in] `szCulture` 缓冲区中的字符数。</span><span class="sxs-lookup"><span data-stu-id="b5e8d-106">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="b5e8d-107">[out] 实际写入 `szCulture` 缓冲区的字符数。</span><span class="sxs-lookup"><span data-stu-id="b5e8d-107">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="b5e8d-108">[out] 包含区域性名称的字符数组。</span><span class="sxs-lookup"><span data-stu-id="b5e8d-108">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5e8d-109">备注</span><span class="sxs-lookup"><span data-stu-id="b5e8d-109">Remarks</span></span>  
 <span data-ttu-id="b5e8d-110">区域性名称是用于标识区域性的唯一字符串，例如“EN-US”（针对美式英语区域性）或“neutral”（针对非特定区域性）。</span><span class="sxs-lookup"><span data-stu-id="b5e8d-110">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5e8d-111">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="b5e8d-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5e8d-112">要求</span><span class="sxs-lookup"><span data-stu-id="b5e8d-112">Requirements</span></span>  
 <span data-ttu-id="b5e8d-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b5e8d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5e8d-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5e8d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5e8d-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5e8d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5e8d-116">**.NET framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5e8d-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5e8d-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5e8d-117">See Also</span></span>  
 [<span data-ttu-id="b5e8d-118">ICorDebugMergedAssemblyRecord 接口</span><span class="sxs-lookup"><span data-stu-id="b5e8d-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="b5e8d-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="b5e8d-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
