---
title: GetCORSystemDirectory 函数
ms.date: 03/30/2017
api_name:
- GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORSystemDirectory
helpviewer_keywords:
- GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type:
- apiref
ms.openlocfilehash: bdafacfe52d678aacfcd44de1e924bcb88547424
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178209"
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="0c285-102">GetCORSystemDirectory 函数</span><span class="sxs-lookup"><span data-stu-id="0c285-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="0c285-103">返回加载到进程中的通用语言运行时 （CLR） 的安装目录。</span><span class="sxs-lookup"><span data-stu-id="0c285-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="0c285-104">安装目录完全限定，例如，"c：_windows_microsoft.net_framework_v1.0.3705"。</span><span class="sxs-lookup"><span data-stu-id="0c285-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="0c285-105">不推荐使用此函数。</span><span class="sxs-lookup"><span data-stu-id="0c285-105">This function is deprecated.</span></span> <span data-ttu-id="0c285-106">它被[ICLRRuntimeInfo 取代：获取](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md).NET 框架 4 中提供的 RuntimeDirectory 方法。</span><span class="sxs-lookup"><span data-stu-id="0c285-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c285-107">语法</span><span class="sxs-lookup"><span data-stu-id="0c285-107">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (
    [out] LPWSTR  pbuffer,
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="0c285-108">parameters</span><span class="sxs-lookup"><span data-stu-id="0c285-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="0c285-109">[出]运行时返回一个字符串，其中包含加载到进程的运行时安装目录的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="0c285-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="0c285-110">如果运行时尚未加载到进程中，该函数将返回计算机上安装的最新版本的运行时的相应目录信息。</span><span class="sxs-lookup"><span data-stu-id="0c285-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="0c285-111">[在]的大小（以字节为单位）的大小`pbuffer`。</span><span class="sxs-lookup"><span data-stu-id="0c285-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="0c285-112">[出]中`pbuffer`返回的字符数。</span><span class="sxs-lookup"><span data-stu-id="0c285-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c285-113">备注</span><span class="sxs-lookup"><span data-stu-id="0c285-113">Remarks</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="0c285-114">请勿在运行 CLR 版本 4 的进程中使用此功能。</span><span class="sxs-lookup"><span data-stu-id="0c285-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="0c285-115">如果计算机上安装了 CLR 的早期版本，则此功能将返回该版本的安装目录。</span><span class="sxs-lookup"><span data-stu-id="0c285-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c285-116">要求</span><span class="sxs-lookup"><span data-stu-id="0c285-116">Requirements</span></span>  
 <span data-ttu-id="0c285-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0c285-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c285-118">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0c285-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c285-119">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0c285-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c285-120">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c285-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c285-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c285-121">See also</span></span>

- [<span data-ttu-id="0c285-122">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="0c285-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
