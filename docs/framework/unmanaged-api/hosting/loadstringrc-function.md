---
title: LoadStringRC 函数
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f17ecfe683de0739e4e1e063d38836eecf949336
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59146988"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="90d81-102">LoadStringRC 函数</span><span class="sxs-lookup"><span data-stu-id="90d81-102">LoadStringRC Function</span></span>
<span data-ttu-id="90d81-103">通过使用当前线程的默认区域性将 HRESULT 值转换成一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="90d81-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="90d81-104">此函数中不推荐[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="90d81-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90d81-105">语法</span><span class="sxs-lookup"><span data-stu-id="90d81-105">Syntax</span></span>  
  
```  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90d81-106">参数</span><span class="sxs-lookup"><span data-stu-id="90d81-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="90d81-107">[in]HRESULT。</span><span class="sxs-lookup"><span data-stu-id="90d81-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="90d81-108">[out]包含成功完成后的错误消息的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="90d81-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="90d81-109">[in]错误消息缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="90d81-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="90d81-110">[in]忽略。</span><span class="sxs-lookup"><span data-stu-id="90d81-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90d81-111">返回值</span><span class="sxs-lookup"><span data-stu-id="90d81-111">Return Value</span></span>  
 <span data-ttu-id="90d81-112">此方法返回标准的组件对象模型 (COM) 错误代码，定义在 WinError.h，除了以下值。</span><span class="sxs-lookup"><span data-stu-id="90d81-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="90d81-113">返回代码</span><span class="sxs-lookup"><span data-stu-id="90d81-113">Return code</span></span>|<span data-ttu-id="90d81-114">描述</span><span class="sxs-lookup"><span data-stu-id="90d81-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="90d81-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="90d81-115">S_OK</span></span>|<span data-ttu-id="90d81-116">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="90d81-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="90d81-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="90d81-117">E_INVALIDARG</span></span>|<span data-ttu-id="90d81-118">`szBuffer` 为 null 或`iMax`为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="90d81-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90d81-119">备注</span><span class="sxs-lookup"><span data-stu-id="90d81-119">Remarks</span></span>  
 <span data-ttu-id="90d81-120">如果该方法不成功，完成`szBuffer`包含空字符串。</span><span class="sxs-lookup"><span data-stu-id="90d81-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90d81-121">要求</span><span class="sxs-lookup"><span data-stu-id="90d81-121">Requirements</span></span>  
 <span data-ttu-id="90d81-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90d81-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90d81-123">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="90d81-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="90d81-124">**库：** MSCorEE.dll 和 Mscorwks.dll。</span><span class="sxs-lookup"><span data-stu-id="90d81-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="90d81-125">使用而不是 Mscorwks.dll MSCorEE.dll 确保面向.NET Framework 的正确版本。</span><span class="sxs-lookup"><span data-stu-id="90d81-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="90d81-126">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90d81-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90d81-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="90d81-127">See also</span></span>

- [<span data-ttu-id="90d81-128">LoadStringRCEx 函数</span><span class="sxs-lookup"><span data-stu-id="90d81-128">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [<span data-ttu-id="90d81-129">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="90d81-129">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
