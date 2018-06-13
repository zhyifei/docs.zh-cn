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
ms.openlocfilehash: 9d562aef58c1e3b5bbbe690b54eb08384052c657
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456770"
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="04190-102">StrongNameGetBlobFromImage 函数</span><span class="sxs-lookup"><span data-stu-id="04190-102">StrongNameGetBlobFromImage Function</span></span>
<span data-ttu-id="04190-103">获取位于指定的内存地址处的二进制表示形式的程序集映像。</span><span class="sxs-lookup"><span data-stu-id="04190-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="04190-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="04190-104">This function has been deprecated.</span></span> <span data-ttu-id="04190-105">使用[iclrstrongname:: Strongnamegetblobfromimage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="04190-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04190-106">语法</span><span class="sxs-lookup"><span data-stu-id="04190-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04190-107">参数</span><span class="sxs-lookup"><span data-stu-id="04190-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="04190-108">[in]映射程序集清单内存地址。</span><span class="sxs-lookup"><span data-stu-id="04190-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="04190-109">[in]大小，以字节为单位，在图像的`pbBase`。</span><span class="sxs-lookup"><span data-stu-id="04190-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="04190-110">[in]用于包含图像的二进制表示的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="04190-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="04190-111">[在中，out]请求的最大大小，以字节为单位， `pbBlob`。</span><span class="sxs-lookup"><span data-stu-id="04190-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="04190-112">返回时，实际大小，以字节为单位的`pbBlob`。</span><span class="sxs-lookup"><span data-stu-id="04190-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04190-113">返回值</span><span class="sxs-lookup"><span data-stu-id="04190-113">Return Value</span></span>  
 <span data-ttu-id="04190-114">`true` 在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="04190-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04190-115">备注</span><span class="sxs-lookup"><span data-stu-id="04190-115">Remarks</span></span>  
 <span data-ttu-id="04190-116">如果`StrongNameGetBlobFromImage`函数未成功完成，请调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数可检索的最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="04190-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04190-117">要求</span><span class="sxs-lookup"><span data-stu-id="04190-117">Requirements</span></span>  
 <span data-ttu-id="04190-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="04190-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04190-119">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="04190-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="04190-120">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="04190-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="04190-121">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04190-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04190-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="04190-122">See Also</span></span>  
 [<span data-ttu-id="04190-123">StrongNameGetBlobFromImage 方法</span><span class="sxs-lookup"><span data-stu-id="04190-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [<span data-ttu-id="04190-124">StrongNameGetBlob 方法</span><span class="sxs-lookup"><span data-stu-id="04190-124">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [<span data-ttu-id="04190-125">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="04190-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
