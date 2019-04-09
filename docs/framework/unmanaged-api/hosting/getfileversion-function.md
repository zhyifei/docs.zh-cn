---
title: GetFileVersion 函数
ms.date: 03/30/2017
api_name:
- GetFileVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetFileVersion
helpviewer_keywords:
- GetFileVersion function [.NET Framework hosting]
ms.assetid: b3222c85-da88-4485-97d7-3a6ee3e8d358
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d25a3ccdd66ff7acb70f1f5e6c60157b53cc97c5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123718"
---
# <a name="getfileversion-function"></a><span data-ttu-id="57d70-102">GetFileVersion 函数</span><span class="sxs-lookup"><span data-stu-id="57d70-102">GetFileVersion Function</span></span>
<span data-ttu-id="57d70-103">获取指定的文件，使用指定的缓冲区的公共语言运行时 (CLR) 版本信息。</span><span class="sxs-lookup"><span data-stu-id="57d70-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="57d70-104">此函数中不推荐[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="57d70-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57d70-105">语法</span><span class="sxs-lookup"><span data-stu-id="57d70-105">Syntax</span></span>  
  
```  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57d70-106">参数</span><span class="sxs-lookup"><span data-stu-id="57d70-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="57d70-107">[in]要检查的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="57d70-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="57d70-108">[in、 out]有关返回的版本信息分配的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="57d70-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="57d70-109">[in]大小，以宽字符为单位的`szBuffer`。</span><span class="sxs-lookup"><span data-stu-id="57d70-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="57d70-110">[out]大小 （字节），则返回的`szBuffer`。</span><span class="sxs-lookup"><span data-stu-id="57d70-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57d70-111">要求</span><span class="sxs-lookup"><span data-stu-id="57d70-111">Requirements</span></span>  
 <span data-ttu-id="57d70-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="57d70-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57d70-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="57d70-113">**Header:** MSCorEE.h</span></span>  
  
 **<span data-ttu-id="57d70-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="57d70-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="57d70-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="57d70-115">See also</span></span>

- [<span data-ttu-id="57d70-116">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="57d70-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
