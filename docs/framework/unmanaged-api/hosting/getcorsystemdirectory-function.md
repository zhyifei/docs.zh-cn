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
ms.openlocfilehash: 63fb505a92683fda21b6e71a6ca891ca35afba1d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136410"
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="7846d-102">GetCORSystemDirectory 函数</span><span class="sxs-lookup"><span data-stu-id="7846d-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="7846d-103">返回加载到进程中的公共语言运行时（CLR）的安装目录。</span><span class="sxs-lookup"><span data-stu-id="7846d-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="7846d-104">安装目录是完全限定的，例如 "c:\windows\microsoft.net\framework\v1.0.3705"。</span><span class="sxs-lookup"><span data-stu-id="7846d-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="7846d-105">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="7846d-105">This function is deprecated.</span></span> <span data-ttu-id="7846d-106">它被 .NET Framework 4 中提供的[ICLRRuntimeInfo：： GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md)方法取代。</span><span class="sxs-lookup"><span data-stu-id="7846d-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7846d-107">语法</span><span class="sxs-lookup"><span data-stu-id="7846d-107">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="7846d-108">参数</span><span class="sxs-lookup"><span data-stu-id="7846d-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="7846d-109">弄一个缓冲区，其中运行时返回一个字符串，其中包含加载到进程中的运行时的安装目录的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="7846d-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="7846d-110">如果运行时尚未加载到进程中，则该函数将为计算机上安装的最新版本的运行时返回相应的目录信息。</span><span class="sxs-lookup"><span data-stu-id="7846d-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="7846d-111">中`pbuffer`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="7846d-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="7846d-112">弄`pbuffer`中返回的字符数。</span><span class="sxs-lookup"><span data-stu-id="7846d-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7846d-113">备注</span><span class="sxs-lookup"><span data-stu-id="7846d-113">Remarks</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="7846d-114">不要在运行 CLR 版本4的进程中使用此函数。</span><span class="sxs-lookup"><span data-stu-id="7846d-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="7846d-115">如果计算机上安装了 CLR 的早期版本，则此函数将返回该版本的安装目录。</span><span class="sxs-lookup"><span data-stu-id="7846d-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7846d-116">要求</span><span class="sxs-lookup"><span data-stu-id="7846d-116">Requirements</span></span>  
 <span data-ttu-id="7846d-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7846d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7846d-118">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7846d-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7846d-119">**库：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7846d-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7846d-120">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7846d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7846d-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="7846d-121">See also</span></span>

- [<span data-ttu-id="7846d-122">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="7846d-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
