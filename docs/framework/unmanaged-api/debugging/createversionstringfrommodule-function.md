---
title: CreateVersionStringFromModule 函数
ms.date: 03/30/2017
api_name:
- CreateVersionStringFromModule
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CreateVersionStringFromModule
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CreateVersionStringFromModule function
ms.assetid: 3d2fe9bd-75ef-4364-84a6-da1e1994ac1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ed8b85475dc7327c1aac6f920aba627215e27c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965797"
---
# <a name="createversionstringfrommodule-function"></a><span data-ttu-id="3c3c7-102">CreateVersionStringFromModule 函数</span><span class="sxs-lookup"><span data-stu-id="3c3c7-102">CreateVersionStringFromModule Function</span></span>
<span data-ttu-id="3c3c7-103">从目标进程中的公共语言运行时 (CLR) 路径创建版本字符串。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-103">Creates a version string from a common language runtime (CLR) path in a target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c3c7-104">语法</span><span class="sxs-lookup"><span data-stu-id="3c3c7-104">Syntax</span></span>  
  
```  
HRESULT CreateVersionStringFromModule (  
    [in]  DWORD      pidDebuggee,  
    [in]  LPCWSTR    szModuleName,  
    [out, size_is(cchBuffer),  
          length_is(*pdwLength)] LPWSTR Buffer,  
    [in]  DWORD      cchBuffer,  
    [out] DWORD*     pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c3c7-105">参数</span><span class="sxs-lookup"><span data-stu-id="3c3c7-105">Parameters</span></span>  
 `pidDebuggee`  
 <span data-ttu-id="3c3c7-106">[in] 在其中加载目标 CLR 的进程的标识符。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-106">[in] Identifier of the process in which the target CLR is loaded.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="3c3c7-107">[in] 指向进程中加载的目标 CLR 的完整路径或相对路径。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-107">[in] Full or relative path to the target CLR that is loaded in the process.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="3c3c7-108">[out] 返回用于存储目标 CLR 的版本字符串的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-108">[out] Return buffer for storing the version string for the target CLR.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="3c3c7-109">[in] `pBuffer` 的大小。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-109">[in] Size of `pBuffer`.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="3c3c7-110">[out] `pBuffer` 返回的版本字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-110">[out] Length of the version string returned by `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c3c7-111">返回值</span><span class="sxs-lookup"><span data-stu-id="3c3c7-111">Return Value</span></span>  
 <span data-ttu-id="3c3c7-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3c3c7-112">S_OK</span></span>  
 <span data-ttu-id="3c3c7-113">目标 CLR 的版本字符串已成功返回到 `pBuffer` 中。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-113">The version string for the target CLR was successfully returned in `pBuffer`.</span></span>  
  
 <span data-ttu-id="3c3c7-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3c3c7-114">E_INVALIDARG</span></span>  
 <span data-ttu-id="3c3c7-115">`szModuleName` 为 null，或 `pBuffer` 或 `cchBuffer` 为 null。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-115">`szModuleName` is null, or either `pBuffer` or `cchBuffer` is null.</span></span> <span data-ttu-id="3c3c7-116">`pBuffer` 和 `cchBuffer` 必须都为 null 或非 null。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-116">`pBuffer` and `cchBuffer` must both be null or non-null.</span></span>  
  
 <span data-ttu-id="3c3c7-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="3c3c7-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>  
 <span data-ttu-id="3c3c7-118">`pdwLength` 大于 `cchBuffer`。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-118">`pdwLength` is greater than `cchBuffer`.</span></span> <span data-ttu-id="3c3c7-119">如果已为 `pBuffer` 和 `cchBuffer` 都传递了 null，并且已通过使用 `pdwLength` 查询了必要的缓冲区大小，这可能为预期的结果。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-119">This may be an expected result if you have passed null for both `pBuffer` and `cchBuffer`, and queried the necessary buffer size by using `pdwLength`.</span></span>  
  
 <span data-ttu-id="3c3c7-120">HRESULT_FROM_WIN32(ERROR_MOD_NOT_FOUND)</span><span class="sxs-lookup"><span data-stu-id="3c3c7-120">HRESULT_FROM_WIN32(ERROR_MOD_NOT_FOUND)</span></span>  
 <span data-ttu-id="3c3c7-121">`szModuleName` 不包含指向目标进程中有效 CLR 的路径。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-121">`szModuleName` does not contain a path to a valid CLR in the target process.</span></span>  
  
 <span data-ttu-id="3c3c7-122">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="3c3c7-122">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="3c3c7-123">`pidDebuggee` 不引用有效进程，或其他故障。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-123">`pidDebuggee` does not refer to a valid process, or other failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c3c7-124">备注</span><span class="sxs-lookup"><span data-stu-id="3c3c7-124">Remarks</span></span>  
 <span data-ttu-id="3c3c7-125">此函数接受由 `pidDebuggee` 标识的 CLR 进程和由 `szModuleName` 指定的字符串路径。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-125">This function accepts a CLR process that is identified by `pidDebuggee` and a string path that is specified by `szModuleName`.</span></span> <span data-ttu-id="3c3c7-126">版本字符串返回 `pBuffer` 指向的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-126">The version string is returned in the buffer that `pBuffer` points to.</span></span> <span data-ttu-id="3c3c7-127">此字符串对函数用户是不透明的；这就是说，该版本字符串本身不具有任何实质意义。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-127">This string is opaque to the function user; that is, there is no intrinsic meaning in the version string itself.</span></span> <span data-ttu-id="3c3c7-128">在此函数的上下文中单独使用并[CreateDebuggingInterfaceFromVersion 函数](../../../../docs/framework/unmanaged-api/debugging/createdebugginginterfacefromversion-function-for-silverlight.md)。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-128">It is used solely in the context of this function and the [CreateDebuggingInterfaceFromVersion function](../../../../docs/framework/unmanaged-api/debugging/createdebugginginterfacefromversion-function-for-silverlight.md).</span></span>  
  
 <span data-ttu-id="3c3c7-129">应两次调用此函数。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-129">This function should be called twice.</span></span> <span data-ttu-id="3c3c7-130">第一次调用此函数时，为 `pBuffer` 和 `cchBuffer` 传递 null。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-130">When you call it the first time, pass null for both `pBuffer` and `cchBuffer`.</span></span> <span data-ttu-id="3c3c7-131">执行此操作时，`pBuffer` 所需的缓冲区大小将在 `pdwLength` 中返回。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-131">When you do this, the size of the buffer necessary for `pBuffer` will be returned in `pdwLength`.</span></span> <span data-ttu-id="3c3c7-132">然后可以第二次调用该函数，并将缓冲区传入 `pBuffer` 以及将缓冲区大小传入 `cchBuffer`。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-132">You can then call the function a second time, and pass the buffer in `pBuffer` and its size in `cchBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c3c7-133">要求</span><span class="sxs-lookup"><span data-stu-id="3c3c7-133">Requirements</span></span>  
 <span data-ttu-id="3c3c7-134">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3c3c7-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c3c7-135">**标头：** dbgshim.h</span><span class="sxs-lookup"><span data-stu-id="3c3c7-135">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="3c3c7-136">**库：** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="3c3c7-136">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="3c3c7-137">**.NET framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="3c3c7-137">**.NET Framework Versions:** 3.5 SP1</span></span>
