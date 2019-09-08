---
title: GetHistoryFileDirectory 函数
ms.date: 03/30/2017
api_name:
- GetHistoryFileDirectory
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- GetHistoryFileDirectory
helpviewer_keywords:
- GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: adbbf94dc36c6d82360ed532b283cd666a1a52ed
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796848"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="63af1-102">GetHistoryFileDirectory 函数</span><span class="sxs-lookup"><span data-stu-id="63af1-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="63af1-103">检索应用程序历史记录目录的路径。</span><span class="sxs-lookup"><span data-stu-id="63af1-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63af1-104">语法</span><span class="sxs-lookup"><span data-stu-id="63af1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63af1-105">参数</span><span class="sxs-lookup"><span data-stu-id="63af1-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="63af1-106">弄用于保存应用程序历史记录目录路径的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="63af1-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="63af1-107">[in，out]缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="63af1-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63af1-108">返回值</span><span class="sxs-lookup"><span data-stu-id="63af1-108">Return Value</span></span>  
 <span data-ttu-id="63af1-109">除以下值外，此方法还返回 Winerror.h 文件中定义的标准 COM 错误代码。</span><span class="sxs-lookup"><span data-stu-id="63af1-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="63af1-110">返回代码</span><span class="sxs-lookup"><span data-stu-id="63af1-110">Return code</span></span>|<span data-ttu-id="63af1-111">描述</span><span class="sxs-lookup"><span data-stu-id="63af1-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="63af1-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="63af1-112">S_OK</span></span>|<span data-ttu-id="63af1-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="63af1-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="63af1-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="63af1-114">E_INVALIDARG</span></span>|<span data-ttu-id="63af1-115">`wzDir`或`pdwSize`为 null，或者版本字符串不正确。</span><span class="sxs-lookup"><span data-stu-id="63af1-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63af1-116">备注</span><span class="sxs-lookup"><span data-stu-id="63af1-116">Remarks</span></span>  
 <span data-ttu-id="63af1-117">成功完成后， `pdwSize`参数设置为路径字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="63af1-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63af1-118">要求</span><span class="sxs-lookup"><span data-stu-id="63af1-118">Requirements</span></span>  
 <span data-ttu-id="63af1-119">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="63af1-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63af1-120">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="63af1-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="63af1-121">**类库**合成 .dll 和 Mscorwks.dll。</span><span class="sxs-lookup"><span data-stu-id="63af1-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="63af1-122">使用 Mscorwks.dll 而不是来确保目标为正确的 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="63af1-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="63af1-123">**.NET Framework 版本：** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63af1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63af1-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="63af1-124">See also</span></span>

- [<span data-ttu-id="63af1-125">CreateHistoryReader 函数</span><span class="sxs-lookup"><span data-stu-id="63af1-125">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="63af1-126">NukeDownloadedCache 函数</span><span class="sxs-lookup"><span data-stu-id="63af1-126">NukeDownloadedCache Function</span></span>](nukedownloadedcache-function.md)
- [<span data-ttu-id="63af1-127">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="63af1-127">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
