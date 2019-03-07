---
title: ICLRStrongName::StrongNameGetBlobFromImage 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetBlobFromImage method [.NET Framework hosting]
ms.assetid: 0f5a2ec8-e776-4fd8-bda6-937b6834575a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 498dd5f8242b4db29d2bb292e01001f9240e6fc3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480996"
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a><span data-ttu-id="3826a-102">ICLRStrongName::StrongNameGetBlobFromImage 方法</span><span class="sxs-lookup"><span data-stu-id="3826a-102">ICLRStrongName::StrongNameGetBlobFromImage Method</span></span>
<span data-ttu-id="3826a-103">获取指定内存地址处程序集映像的二进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="3826a-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3826a-104">语法</span><span class="sxs-lookup"><span data-stu-id="3826a-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3826a-105">参数</span><span class="sxs-lookup"><span data-stu-id="3826a-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="3826a-106">[in]映射的程序集清单的内存地址。</span><span class="sxs-lookup"><span data-stu-id="3826a-106">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="3826a-107">[in]大小 （字节） 的图像`pbBase`。</span><span class="sxs-lookup"><span data-stu-id="3826a-107">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="3826a-108">[in]用于包含图像的二进制表示形式的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="3826a-108">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="3826a-109">[in、 out]请求的最大大小，以字节为单位， `pbBlob`。</span><span class="sxs-lookup"><span data-stu-id="3826a-109">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="3826a-110">在返回时，实际大小，以字节为单位的`pbBlob`。</span><span class="sxs-lookup"><span data-stu-id="3826a-110">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3826a-111">返回值</span><span class="sxs-lookup"><span data-stu-id="3826a-111">Return Value</span></span>  
 <span data-ttu-id="3826a-112">`S_OK` 如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="3826a-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3826a-113">要求</span><span class="sxs-lookup"><span data-stu-id="3826a-113">Requirements</span></span>  
 <span data-ttu-id="3826a-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3826a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3826a-115">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="3826a-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3826a-116">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3826a-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3826a-117">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3826a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3826a-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="3826a-118">See also</span></span>
- [<span data-ttu-id="3826a-119">StrongNameGetBlob 方法</span><span class="sxs-lookup"><span data-stu-id="3826a-119">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="3826a-120">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="3826a-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
