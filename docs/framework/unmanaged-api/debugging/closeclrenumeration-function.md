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
ms.openlocfilehash: 1d42292705dae03e9bf1a1555508dfb69cebde82
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132439"
---
# <a name="closeclrenumeration-function"></a><span data-ttu-id="ee289-102">CloseCLREnumeration 函数</span><span class="sxs-lookup"><span data-stu-id="ee289-102">CloseCLREnumeration Function</span></span>
<span data-ttu-id="ee289-103">关闭位于[EnumerateCLRs 函数](enumerateclrs-function.md)所返回的句柄数组中的所有有效的公共语言运行时（CLR）继续启动事件，并释放该句柄和字符串路径数组的内存。</span><span class="sxs-lookup"><span data-stu-id="ee289-103">Closes any valid common language runtime (CLR) continue-startup events located in an array of handles returned by the [EnumerateCLRs function](enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee289-104">语法</span><span class="sxs-lookup"><span data-stu-id="ee289-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee289-105">参数</span><span class="sxs-lookup"><span data-stu-id="ee289-105">Parameters</span></span>  
 `pHandleArray`  
 <span data-ttu-id="ee289-106">中指向从[EnumerateCLRs 函数](enumerateclrs-function.md)返回的事件句柄的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="ee289-106">[in] Pointer to the array of event handles returned from the [EnumerateCLRs function](enumerateclrs-function.md).</span></span>  
  
 `pStringArray`  
 <span data-ttu-id="ee289-107">中一个指针，指向从[EnumerateCLRs 函数](enumerateclrs-function.md)返回的 CLR 字符串路径的数组。</span><span class="sxs-lookup"><span data-stu-id="ee289-107">[in] Pointer to the array of CLR string paths returned from the [EnumerateCLRs function](enumerateclrs-function.md).</span></span>  
  
 `dwArrayLength`  
 <span data-ttu-id="ee289-108">[in] 包含 `pHandleArray` 或 `pStringArray`大小（长度）（它们是相同）的 DWORD。</span><span class="sxs-lookup"><span data-stu-id="ee289-108">[in] DWORD that contains the size (length) of either `pHandleArray` or `pStringArray` (they are the same).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee289-109">返回值</span><span class="sxs-lookup"><span data-stu-id="ee289-109">Return Value</span></span>  
 <span data-ttu-id="ee289-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ee289-110">S_OK</span></span>  
 <span data-ttu-id="ee289-111">[EnumerateCLRs 函数](enumerateclrs-function.md)打开的句柄将关闭，并且将释放分配给句柄和字符串数组的内存。</span><span class="sxs-lookup"><span data-stu-id="ee289-111">Handles opened by the [EnumerateCLRs function](enumerateclrs-function.md) are closed, and memory allocated for the handle and string arrays is freed.</span></span>  
  
 <span data-ttu-id="ee289-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ee289-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="ee289-113">`pHandleArray` 的长度与传入 `dwArrayLength` 的长度不匹配。</span><span class="sxs-lookup"><span data-stu-id="ee289-113">The length of `pHandleArray` does not match the length that is passed in `dwArrayLength`.</span></span>  
  
 <span data-ttu-id="ee289-114">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="ee289-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="ee289-115">此函数无法释放 `pHandleArray` 和 `pStringArray` 的内存。</span><span class="sxs-lookup"><span data-stu-id="ee289-115">The function is unable to free the memory for `pHandleArray` and `pStringArray`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee289-116">要求</span><span class="sxs-lookup"><span data-stu-id="ee289-116">Requirements</span></span>  
 <span data-ttu-id="ee289-117">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ee289-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee289-118">**标头：** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="ee289-118">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="ee289-119">**库：** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="ee289-119">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="ee289-120">**.NET Framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="ee289-120">**.NET Framework Versions:** 3.5 SP1</span></span>
