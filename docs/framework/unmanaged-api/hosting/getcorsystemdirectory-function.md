---
title: "GetCORSystemDirectory 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: GetCORSystemDirectory
helpviewer_keywords: GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 802e9a7bd4e6caedd657a8e8cf0132d75b4cbc2e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="e2f99-102">GetCORSystemDirectory 函数</span><span class="sxs-lookup"><span data-stu-id="e2f99-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="e2f99-103">返回加载到进程公共语言运行时 (CLR) 的安装目录。</span><span class="sxs-lookup"><span data-stu-id="e2f99-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="e2f99-104">安装目录是完全限定，例如，"c:\windows\microsoft.net\framework\v1.0.3705"。</span><span class="sxs-lookup"><span data-stu-id="e2f99-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="e2f99-105">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="e2f99-105">This function is deprecated.</span></span> <span data-ttu-id="e2f99-106">它已被取代[iclrruntimeinfo:: Getruntimedirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md)中提供的方法[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e2f99-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2f99-107">语法</span><span class="sxs-lookup"><span data-stu-id="e2f99-107">Syntax</span></span>  
  
```  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2f99-108">参数</span><span class="sxs-lookup"><span data-stu-id="e2f99-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="e2f99-109">[out]在运行时用于返回包含加载到进程的运行时安装目录的完全限定的名称的字符串缓冲区。</span><span class="sxs-lookup"><span data-stu-id="e2f99-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="e2f99-110">如果尚未到过程加载运行时，函数将返回在计算机上安装的运行时的最新版本的相应目录信息。</span><span class="sxs-lookup"><span data-stu-id="e2f99-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="e2f99-111">[in]大小，以字节为单位的`pbuffer`。</span><span class="sxs-lookup"><span data-stu-id="e2f99-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="e2f99-112">[out]在中返回的字符数`pbuffer`。</span><span class="sxs-lookup"><span data-stu-id="e2f99-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2f99-113">备注</span><span class="sxs-lookup"><span data-stu-id="e2f99-113">Remarks</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="e2f99-114">不要在运行版本 4 的 CLR 的进程中使用此函数。</span><span class="sxs-lookup"><span data-stu-id="e2f99-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="e2f99-115">如果在计算机上安装的 CLR 早期版本，此函数将返回该版本的安装目录。</span><span class="sxs-lookup"><span data-stu-id="e2f99-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2f99-116">要求</span><span class="sxs-lookup"><span data-stu-id="e2f99-116">Requirements</span></span>  
 <span data-ttu-id="e2f99-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e2f99-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2f99-118">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e2f99-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e2f99-119">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e2f99-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2f99-120">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2f99-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2f99-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2f99-121">See Also</span></span>  
 [<span data-ttu-id="e2f99-122">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="e2f99-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
