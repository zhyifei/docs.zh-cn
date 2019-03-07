---
title: ICorDebugLoadedModule::GetName 方法
ms.date: 03/30/2017
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f8b3b25c5e6e80b45ffc97e116c8649078f00861
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478708"
---
# <a name="icordebugloadedmodulegetname-method"></a><span data-ttu-id="a9966-102">ICorDebugLoadedModule::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="a9966-102">ICorDebugLoadedModule::GetName Method</span></span>
<span data-ttu-id="a9966-103">获取加载模块的名称。</span><span class="sxs-lookup"><span data-stu-id="a9966-103">Gets the name of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9966-104">语法</span><span class="sxs-lookup"><span data-stu-id="a9966-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9966-105">参数</span><span class="sxs-lookup"><span data-stu-id="a9966-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="a9966-106">[in] `szName` 缓冲区中的字符数。</span><span class="sxs-lookup"><span data-stu-id="a9966-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="a9966-107">[out] 指向实际写入 `szName` 缓冲区的字符数。缓冲区的字符数的指针。</span><span class="sxs-lookup"><span data-stu-id="a9966-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="a9966-108">[out] 包含加载模块名称的字符数组。</span><span class="sxs-lookup"><span data-stu-id="a9966-108">[out] An array of characters that contain the name of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9966-109">备注</span><span class="sxs-lookup"><span data-stu-id="a9966-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a9966-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="a9966-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9966-111">要求</span><span class="sxs-lookup"><span data-stu-id="a9966-111">Requirements</span></span>  
 <span data-ttu-id="a9966-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a9966-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9966-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9966-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9966-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9966-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9966-115">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9966-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9966-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9966-116">See also</span></span>
- [<span data-ttu-id="a9966-117">ICorDebugLoadedModule 接口</span><span class="sxs-lookup"><span data-stu-id="a9966-117">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="a9966-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="a9966-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
