---
title: CloseCLREnumeration 函数
ms.date: 03/30/2017
api_name:
- CloseCLREnumeration
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CloseCLREnumeration
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CloseCLR Enumeration function
ms.assetid: 5e3c3958-80bb-43b1-a96b-dd3e6dbd9cd7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18903bd00b0a9d09365d03c155531a25dc013189
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406083"
---
# <a name="closeclrenumeration-function"></a><span data-ttu-id="093a1-102">CloseCLREnumeration 函数</span><span class="sxs-lookup"><span data-stu-id="093a1-102">CloseCLREnumeration Function</span></span>
<span data-ttu-id="093a1-103">关闭任何有效的公共语言运行时 (CLR) 继续启动事件位于返回的句柄数组[EnumerateCLRs 函数](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)，并释放句柄和字符串路径数组的内存。</span><span class="sxs-lookup"><span data-stu-id="093a1-103">Closes any valid common language runtime (CLR) continue-startup events located in an array of handles returned by the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="093a1-104">语法</span><span class="sxs-lookup"><span data-stu-id="093a1-104">Syntax</span></span>  
  
```  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="093a1-105">参数</span><span class="sxs-lookup"><span data-stu-id="093a1-105">Parameters</span></span>  
 `pHandleArray`  
 <span data-ttu-id="093a1-106">[in]从返回事件句柄数组的指针[EnumerateCLRs 函数](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)。</span><span class="sxs-lookup"><span data-stu-id="093a1-106">[in] Pointer to the array of event handles returned from the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span></span>  
  
 `pStringArray`  
 <span data-ttu-id="093a1-107">[in]指向从返回的 CLR 字符串路径数组的[EnumerateCLRs 函数](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)。</span><span class="sxs-lookup"><span data-stu-id="093a1-107">[in] Pointer to the array of CLR string paths returned from the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span></span>  
  
 `dwArrayLength`  
 <span data-ttu-id="093a1-108">[in] 包含 `pHandleArray` 或 `pStringArray`大小（长度）（它们是相同）的 DWORD。</span><span class="sxs-lookup"><span data-stu-id="093a1-108">[in] DWORD that contains the size (length) of either `pHandleArray` or `pStringArray` (they are the same).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="093a1-109">返回值</span><span class="sxs-lookup"><span data-stu-id="093a1-109">Return Value</span></span>  
 <span data-ttu-id="093a1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="093a1-110">S_OK</span></span>  
 <span data-ttu-id="093a1-111">通过打开的句柄[EnumerateCLRs 函数](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)均已关闭，并且将释放句柄和字符串数组分配内存。</span><span class="sxs-lookup"><span data-stu-id="093a1-111">Handles opened by the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md) are closed, and memory allocated for the handle and string arrays is freed.</span></span>  
  
 <span data-ttu-id="093a1-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="093a1-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="093a1-113">`pHandleArray` 的长度与传入 `dwArrayLength` 的长度不匹配。</span><span class="sxs-lookup"><span data-stu-id="093a1-113">The length of `pHandleArray` does not match the length that is passed in `dwArrayLength`.</span></span>  
  
 <span data-ttu-id="093a1-114">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="093a1-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="093a1-115">此函数无法释放 `pHandleArray` 和 `pStringArray` 的内存。</span><span class="sxs-lookup"><span data-stu-id="093a1-115">The function is unable to free the memory for `pHandleArray` and `pStringArray`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="093a1-116">要求</span><span class="sxs-lookup"><span data-stu-id="093a1-116">Requirements</span></span>  
 <span data-ttu-id="093a1-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="093a1-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="093a1-118">**标头：** dbgshim.h</span><span class="sxs-lookup"><span data-stu-id="093a1-118">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="093a1-119">**库：** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="093a1-119">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="093a1-120">**.NET framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="093a1-120">**.NET Framework Versions:** 3.5 SP1</span></span>
