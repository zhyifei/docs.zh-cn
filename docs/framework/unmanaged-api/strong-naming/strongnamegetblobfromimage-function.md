---
title: StrongNameGetBlobFromImage 函数
ms.date: 03/30/2017
api_name:
- StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c9f53c1d0c06498c6c9cede938d115f38a47569
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478786"
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="b3f9d-102">StrongNameGetBlobFromImage 函数</span><span class="sxs-lookup"><span data-stu-id="b3f9d-102">StrongNameGetBlobFromImage Function</span></span>
<span data-ttu-id="b3f9d-103">获取指定内存地址处程序集映像的二进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="b3f9d-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="b3f9d-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="b3f9d-104">This function has been deprecated.</span></span> <span data-ttu-id="b3f9d-105">使用[iclrstrongname:: Strongnamegetblobfromimage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="b3f9d-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3f9d-106">语法</span><span class="sxs-lookup"><span data-stu-id="b3f9d-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3f9d-107">参数</span><span class="sxs-lookup"><span data-stu-id="b3f9d-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="b3f9d-108">[in]映射的程序集清单的内存地址。</span><span class="sxs-lookup"><span data-stu-id="b3f9d-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="b3f9d-109">[in]大小 （字节） 的图像`pbBase`。</span><span class="sxs-lookup"><span data-stu-id="b3f9d-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="b3f9d-110">[in]用于包含图像的二进制表示形式的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="b3f9d-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="b3f9d-111">[in、 out]请求的最大大小，以字节为单位， `pbBlob`。</span><span class="sxs-lookup"><span data-stu-id="b3f9d-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="b3f9d-112">在返回时，实际大小，以字节为单位的`pbBlob`。</span><span class="sxs-lookup"><span data-stu-id="b3f9d-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3f9d-113">返回值</span><span class="sxs-lookup"><span data-stu-id="b3f9d-113">Return Value</span></span>  
 <span data-ttu-id="b3f9d-114">`true` 在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="b3f9d-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3f9d-115">备注</span><span class="sxs-lookup"><span data-stu-id="b3f9d-115">Remarks</span></span>  
 <span data-ttu-id="b3f9d-116">如果`StrongNameGetBlobFromImage`函数不成功完成，则调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数检索最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="b3f9d-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3f9d-117">要求</span><span class="sxs-lookup"><span data-stu-id="b3f9d-117">Requirements</span></span>  
 <span data-ttu-id="b3f9d-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b3f9d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3f9d-119">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="b3f9d-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b3f9d-120">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b3f9d-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b3f9d-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3f9d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3f9d-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="b3f9d-122">See also</span></span>
- [<span data-ttu-id="b3f9d-123">StrongNameGetBlobFromImage 方法</span><span class="sxs-lookup"><span data-stu-id="b3f9d-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="b3f9d-124">StrongNameGetBlob 方法</span><span class="sxs-lookup"><span data-stu-id="b3f9d-124">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="b3f9d-125">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="b3f9d-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
