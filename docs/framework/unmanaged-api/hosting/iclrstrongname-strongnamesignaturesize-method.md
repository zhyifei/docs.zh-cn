---
title: ICLRStrongName::StrongNameSignatureSize 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureSize
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureSize method [.NET Framework hosting]
- StrongNameSignatureSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 76d4f93a-5e25-4399-abcc-a1389549481d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6641490908b1f384bf8192fd46b7dadb4ff5e23
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431937"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="c81fc-102">ICLRStrongName::StrongNameSignatureSize 方法</span><span class="sxs-lookup"><span data-stu-id="c81fc-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="c81fc-103">返回强名称签名的大小。</span><span class="sxs-lookup"><span data-stu-id="c81fc-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="c81fc-104">编译器通常使用此方法用于确定要创建延迟签名的程序集时，在文件中保留多少空间。</span><span class="sxs-lookup"><span data-stu-id="c81fc-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c81fc-105">语法</span><span class="sxs-lookup"><span data-stu-id="c81fc-105">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="c81fc-106">参数</span><span class="sxs-lookup"><span data-stu-id="c81fc-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="c81fc-107">[in]类型的结构[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)包含用于生成强名称签名的密钥对的公共部分。</span><span class="sxs-lookup"><span data-stu-id="c81fc-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="c81fc-108">[in]大小，以字节为单位的`pbPublicKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="c81fc-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="c81fc-109">[in]存储的强名称签名所需的字节数。</span><span class="sxs-lookup"><span data-stu-id="c81fc-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c81fc-110">返回值</span><span class="sxs-lookup"><span data-stu-id="c81fc-110">Return Value</span></span>  
 <span data-ttu-id="c81fc-111">`S_OK` 如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="c81fc-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c81fc-112">要求</span><span class="sxs-lookup"><span data-stu-id="c81fc-112">Requirements</span></span>  
 <span data-ttu-id="c81fc-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c81fc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c81fc-114">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c81fc-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c81fc-115">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c81fc-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c81fc-116">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c81fc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c81fc-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="c81fc-117">See Also</span></span>  
 [<span data-ttu-id="c81fc-118">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="c81fc-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
