---
title: "StrongNameGetBlob 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameGetBlob
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameGetBlob
helpviewer_keywords: StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0a88131e4a764c963d24a698935ebb12e0daa96c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamegetblob-function"></a><span data-ttu-id="70950-102">StrongNameGetBlob 函数</span><span class="sxs-lookup"><span data-stu-id="70950-102">StrongNameGetBlob Function</span></span>
<span data-ttu-id="70950-103">用的二进制表示形式指定地址处的可执行文件填充指定的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="70950-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
 <span data-ttu-id="70950-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="70950-104">This function has been deprecated.</span></span> <span data-ttu-id="70950-105">使用[iclrstrongname:: Strongnamegetblob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="70950-105">Use the [ICLRStrongName::StrongNameGetBLob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70950-106">语法</span><span class="sxs-lookup"><span data-stu-id="70950-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="70950-107">参数</span><span class="sxs-lookup"><span data-stu-id="70950-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="70950-108">[in]要加载的可执行文件的有效路径。</span><span class="sxs-lookup"><span data-stu-id="70950-108">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="70950-109">[in]到用来加载可执行文件的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="70950-109">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="70950-110">[在中，out]请求的最大大小，以字节为单位， `pbBlob`。</span><span class="sxs-lookup"><span data-stu-id="70950-110">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="70950-111">返回时，实际大小，以字节为单位的`pbBlob`。</span><span class="sxs-lookup"><span data-stu-id="70950-111">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70950-112">返回值</span><span class="sxs-lookup"><span data-stu-id="70950-112">Return Value</span></span>  
 <span data-ttu-id="70950-113">`true`在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="70950-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70950-114">备注</span><span class="sxs-lookup"><span data-stu-id="70950-114">Remarks</span></span>  
 <span data-ttu-id="70950-115">如果`StrongNameGetBlob`函数未成功完成，请调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数可检索的最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="70950-115">If the `StrongNameGetBlob` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70950-116">要求</span><span class="sxs-lookup"><span data-stu-id="70950-116">Requirements</span></span>  
 <span data-ttu-id="70950-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="70950-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70950-118">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="70950-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="70950-119">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="70950-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="70950-120">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70950-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70950-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70950-121">See Also</span></span>  
 [<span data-ttu-id="70950-122">StrongNameGetBlob 方法</span><span class="sxs-lookup"><span data-stu-id="70950-122">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [<span data-ttu-id="70950-123">StrongNameGetBlobFromImage 方法</span><span class="sxs-lookup"><span data-stu-id="70950-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [<span data-ttu-id="70950-124">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="70950-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
