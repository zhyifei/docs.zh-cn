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
ms.openlocfilehash: f5b4ef7777c9d45c2d255cc2915f8c4ccdeef4a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432604"
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a><span data-ttu-id="528be-102">ICLRStrongName::StrongNameGetBlobFromImage 方法</span><span class="sxs-lookup"><span data-stu-id="528be-102">ICLRStrongName::StrongNameGetBlobFromImage Method</span></span>
<span data-ttu-id="528be-103">获取位于指定的内存地址处的二进制表示形式的程序集映像。</span><span class="sxs-lookup"><span data-stu-id="528be-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="528be-104">语法</span><span class="sxs-lookup"><span data-stu-id="528be-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="528be-105">参数</span><span class="sxs-lookup"><span data-stu-id="528be-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="528be-106">[in]映射程序集清单内存地址。</span><span class="sxs-lookup"><span data-stu-id="528be-106">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="528be-107">[in]大小，以字节为单位，在图像的`pbBase`。</span><span class="sxs-lookup"><span data-stu-id="528be-107">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="528be-108">[in]用于包含图像的二进制表示的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="528be-108">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="528be-109">[在中，out]请求的最大大小，以字节为单位， `pbBlob`。</span><span class="sxs-lookup"><span data-stu-id="528be-109">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="528be-110">返回时，实际大小，以字节为单位的`pbBlob`。</span><span class="sxs-lookup"><span data-stu-id="528be-110">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="528be-111">返回值</span><span class="sxs-lookup"><span data-stu-id="528be-111">Return Value</span></span>  
 <span data-ttu-id="528be-112">`S_OK` 如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="528be-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="528be-113">要求</span><span class="sxs-lookup"><span data-stu-id="528be-113">Requirements</span></span>  
 <span data-ttu-id="528be-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="528be-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="528be-115">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="528be-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="528be-116">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="528be-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="528be-117">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="528be-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="528be-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="528be-118">See Also</span></span>  
 [<span data-ttu-id="528be-119">StrongNameGetBlob 方法</span><span class="sxs-lookup"><span data-stu-id="528be-119">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [<span data-ttu-id="528be-120">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="528be-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
