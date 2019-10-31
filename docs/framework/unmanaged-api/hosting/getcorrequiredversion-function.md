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
ms.openlocfilehash: 661eb758e1651901bb56810640a68f0de0b4e851
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136481"
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="9e9ee-102">GetCORRequiredVersion 函数</span><span class="sxs-lookup"><span data-stu-id="9e9ee-102">GetCORRequiredVersion Function</span></span>
<span data-ttu-id="9e9ee-103">获取所需的公共语言运行时（CLR）版本号。</span><span class="sxs-lookup"><span data-stu-id="9e9ee-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="9e9ee-104">此函数已在 .NET Framework 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="9e9ee-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e9ee-105">语法</span><span class="sxs-lookup"><span data-stu-id="9e9ee-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e9ee-106">参数</span><span class="sxs-lookup"><span data-stu-id="9e9ee-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="9e9ee-107">弄包含指定版本号的字符串的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="9e9ee-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="9e9ee-108">中缓冲区的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="9e9ee-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="9e9ee-109">弄缓冲区中返回的字节数。</span><span class="sxs-lookup"><span data-stu-id="9e9ee-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e9ee-110">要求</span><span class="sxs-lookup"><span data-stu-id="9e9ee-110">Requirements</span></span>  
 <span data-ttu-id="9e9ee-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9e9ee-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e9ee-112">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9e9ee-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9e9ee-113">**库：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9e9ee-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e9ee-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e9ee-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e9ee-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e9ee-115">See also</span></span>

- [<span data-ttu-id="9e9ee-116">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="9e9ee-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
