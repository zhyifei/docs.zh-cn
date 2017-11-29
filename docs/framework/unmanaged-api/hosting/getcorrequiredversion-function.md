---
title: "GetCORRequiredVersion 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetCORRequiredVersion
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetCORRequiredVersion
helpviewer_keywords: GetCORRequiredVersion function [.NET Framework hosting]
ms.assetid: 1588fe7b-c378-4f4b-9c4b-48647f1119cc
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 05267819a1c61c55220f477173069ddf51edaeb4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="b4fce-102">GetCORRequiredVersion 函数</span><span class="sxs-lookup"><span data-stu-id="b4fce-102">GetCORRequiredVersion Function</span></span>
<span data-ttu-id="b4fce-103">获取所需的公共语言运行时 (CLR) 版本数。</span><span class="sxs-lookup"><span data-stu-id="b4fce-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="b4fce-104">此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b4fce-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4fce-105">语法</span><span class="sxs-lookup"><span data-stu-id="b4fce-105">Syntax</span></span>  
  
```  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4fce-106">参数</span><span class="sxs-lookup"><span data-stu-id="b4fce-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="b4fce-107">[out]包含一个字符串，指定的版本号的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="b4fce-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="b4fce-108">[in]以字节为单位，缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="b4fce-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="b4fce-109">[out]返回在缓冲区中的字节数。</span><span class="sxs-lookup"><span data-stu-id="b4fce-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4fce-110">要求</span><span class="sxs-lookup"><span data-stu-id="b4fce-110">Requirements</span></span>  
 <span data-ttu-id="b4fce-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b4fce-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4fce-112">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b4fce-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b4fce-113">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b4fce-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4fce-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4fce-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4fce-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4fce-115">See Also</span></span>  
 [<span data-ttu-id="b4fce-116">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="b4fce-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
