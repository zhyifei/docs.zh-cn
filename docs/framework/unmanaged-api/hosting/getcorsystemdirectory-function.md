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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8608a5438b31cad64bb27d2866109f479dad441
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739493"
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="fd748-102">GetCORSystemDirectory 函数</span><span class="sxs-lookup"><span data-stu-id="fd748-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="fd748-103">返回加载到进程的公共语言运行时 (CLR) 的安装目录。</span><span class="sxs-lookup"><span data-stu-id="fd748-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="fd748-104">安装目录是完全限定，例如，"c:\windows\microsoft.net\framework\v1.0.3705"。</span><span class="sxs-lookup"><span data-stu-id="fd748-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="fd748-105">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="fd748-105">This function is deprecated.</span></span> <span data-ttu-id="fd748-106">被取代[iclrruntimeinfo:: Getruntimedirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md)方法中提供[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fd748-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd748-107">语法</span><span class="sxs-lookup"><span data-stu-id="fd748-107">Syntax</span></span>  
  
```  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd748-108">参数</span><span class="sxs-lookup"><span data-stu-id="fd748-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="fd748-109">[out]在缓冲区中运行时返回一个字符串，包含要加载到进程的运行时安装目录的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="fd748-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="fd748-110">如果尚未在流程中加载运行时，函数将返回在计算机上安装的运行时的最新版本的相应的目录信息。</span><span class="sxs-lookup"><span data-stu-id="fd748-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="fd748-111">[in]大小，以字节为单位的`pbuffer`。</span><span class="sxs-lookup"><span data-stu-id="fd748-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="fd748-112">[out]在中返回的字符数`pbuffer`。</span><span class="sxs-lookup"><span data-stu-id="fd748-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd748-113">备注</span><span class="sxs-lookup"><span data-stu-id="fd748-113">Remarks</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="fd748-114">在运行版本 4 的 CLR 的进程中不使用此函数。</span><span class="sxs-lookup"><span data-stu-id="fd748-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="fd748-115">如果在计算机上安装早期版本的 CLR，则此函数将返回该版本的安装目录。</span><span class="sxs-lookup"><span data-stu-id="fd748-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd748-116">要求</span><span class="sxs-lookup"><span data-stu-id="fd748-116">Requirements</span></span>  
 <span data-ttu-id="fd748-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fd748-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd748-118">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fd748-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd748-119">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fd748-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd748-120">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd748-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd748-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd748-121">See also</span></span>
- [<span data-ttu-id="fd748-122">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="fd748-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
