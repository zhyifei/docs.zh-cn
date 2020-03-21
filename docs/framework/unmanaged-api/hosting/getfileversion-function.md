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
ms.openlocfilehash: f3b51c1b376fa9c664de53aa76ec724ca305ae6a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178180"
---
# <a name="getfileversion-function"></a><span data-ttu-id="81dfe-102">GetFileVersion 函数</span><span class="sxs-lookup"><span data-stu-id="81dfe-102">GetFileVersion Function</span></span>
<span data-ttu-id="81dfe-103">使用指定的缓冲区获取指定文件的常见语言运行时 （CLR） 版本信息。</span><span class="sxs-lookup"><span data-stu-id="81dfe-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="81dfe-104">此功能已在 .NET 框架 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="81dfe-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81dfe-105">语法</span><span class="sxs-lookup"><span data-stu-id="81dfe-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,
    [in, out] LPWSTR   szBuffer,
    [in]  DWORD        cchBuffer,
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81dfe-106">parameters</span><span class="sxs-lookup"><span data-stu-id="81dfe-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="81dfe-107">[在]要检查的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="81dfe-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="81dfe-108">[进出]为返回的版本信息分配的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="81dfe-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="81dfe-109">[在]的大小（以宽字符表示`szBuffer`）</span><span class="sxs-lookup"><span data-stu-id="81dfe-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="81dfe-110">[出]返回`szBuffer`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="81dfe-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81dfe-111">要求</span><span class="sxs-lookup"><span data-stu-id="81dfe-111">Requirements</span></span>  
 <span data-ttu-id="81dfe-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="81dfe-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81dfe-113">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="81dfe-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81dfe-114">**.NET 框架版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81dfe-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81dfe-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81dfe-115">See also</span></span>

- [<span data-ttu-id="81dfe-116">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="81dfe-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
