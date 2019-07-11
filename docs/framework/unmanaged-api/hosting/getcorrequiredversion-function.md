---
title: GetCORRequiredVersion 函数
ms.date: 03/30/2017
api_name:
- GetCORRequiredVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetCORRequiredVersion
helpviewer_keywords:
- GetCORRequiredVersion function [.NET Framework hosting]
ms.assetid: 1588fe7b-c378-4f4b-9c4b-48647f1119cc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8597b68b75d2b5f77f68fc13c3fb78bfdae46178
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736289"
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="36485-102">GetCORRequiredVersion 函数</span><span class="sxs-lookup"><span data-stu-id="36485-102">GetCORRequiredVersion Function</span></span>
<span data-ttu-id="36485-103">获取所需的公共语言运行时 (CLR) 版本数量。</span><span class="sxs-lookup"><span data-stu-id="36485-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="36485-104">.NET Framework 4 中已弃用此函数。</span><span class="sxs-lookup"><span data-stu-id="36485-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36485-105">语法</span><span class="sxs-lookup"><span data-stu-id="36485-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36485-106">参数</span><span class="sxs-lookup"><span data-stu-id="36485-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="36485-107">[out]包含指定的版本号的字符串的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="36485-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="36485-108">[in]以字节为单位的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="36485-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="36485-109">[out]在缓冲区中返回的字节数。</span><span class="sxs-lookup"><span data-stu-id="36485-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36485-110">要求</span><span class="sxs-lookup"><span data-stu-id="36485-110">Requirements</span></span>  
 <span data-ttu-id="36485-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="36485-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36485-112">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="36485-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="36485-113">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="36485-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="36485-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36485-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36485-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="36485-115">See also</span></span>

- [<span data-ttu-id="36485-116">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="36485-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
