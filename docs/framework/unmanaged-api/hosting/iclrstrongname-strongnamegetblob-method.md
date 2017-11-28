---
title: "ICLRStrongName::StrongNameGetBlob 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName.StrongNameGetBlob
- ICLRStrongName.StrongNameGetBlob
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameGetBlob
helpviewer_keywords:
- ICLRStrongName::StrongNameGetBlob method [.NET Framework hosting]
- StrongNameGetBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: a24218f8-7196-44be-b7a2-ee9cdd7a85c4
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d4ae90367cb84c97d5964ceb815943249af7b240
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="7c1a9-102">ICLRStrongName::StrongNameGetBlob 方法</span><span class="sxs-lookup"><span data-stu-id="7c1a9-102">ICLRStrongName::StrongNameGetBlob Method</span></span>
<span data-ttu-id="7c1a9-103">用的二进制表示形式指定地址处的可执行文件填充指定的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="7c1a9-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c1a9-104">语法</span><span class="sxs-lookup"><span data-stu-id="7c1a9-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c1a9-105">参数</span><span class="sxs-lookup"><span data-stu-id="7c1a9-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="7c1a9-106">[in]要加载的可执行文件的有效路径。</span><span class="sxs-lookup"><span data-stu-id="7c1a9-106">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="7c1a9-107">[in]到用来加载可执行文件的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="7c1a9-107">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="7c1a9-108">[在中，out]请求的最大大小，以字节为单位， `pbBlob`。</span><span class="sxs-lookup"><span data-stu-id="7c1a9-108">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="7c1a9-109">返回时，实际大小，以字节为单位的`pbBlob`。</span><span class="sxs-lookup"><span data-stu-id="7c1a9-109">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c1a9-110">返回值</span><span class="sxs-lookup"><span data-stu-id="7c1a9-110">Return Value</span></span>  
 <span data-ttu-id="7c1a9-111">`S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="7c1a9-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c1a9-112">要求</span><span class="sxs-lookup"><span data-stu-id="7c1a9-112">Requirements</span></span>  
 <span data-ttu-id="7c1a9-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7c1a9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c1a9-114">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7c1a9-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7c1a9-115">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7c1a9-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c1a9-116">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c1a9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c1a9-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c1a9-117">See Also</span></span>  
 [<span data-ttu-id="7c1a9-118">StrongNameGetBlobFromImage 方法</span><span class="sxs-lookup"><span data-stu-id="7c1a9-118">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [<span data-ttu-id="7c1a9-119">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="7c1a9-119">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
