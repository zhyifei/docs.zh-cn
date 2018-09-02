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
ms.openlocfilehash: dc5a40a0e26f116ce1700973a5000e8d6bbbd890
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43423826"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="7e6d1-102">ICLRStrongName::StrongNameSignatureSize 方法</span><span class="sxs-lookup"><span data-stu-id="7e6d1-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="7e6d1-103">返回的强名称签名的大小。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="7e6d1-104">编译器通常使用此方法用于确定要创建延迟签名程序集时，在文件中保留多少空间。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e6d1-105">语法</span><span class="sxs-lookup"><span data-stu-id="7e6d1-105">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e6d1-106">参数</span><span class="sxs-lookup"><span data-stu-id="7e6d1-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="7e6d1-107">[in]类型的结构[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) ，其中包含用于生成强名称签名的密钥对的公共部分。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="7e6d1-108">[in]大小，以字节为单位的`pbPublicKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="7e6d1-109">[in]存储的强名称签名所需的字节数。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e6d1-110">返回值</span><span class="sxs-lookup"><span data-stu-id="7e6d1-110">Return Value</span></span>  
 <span data-ttu-id="7e6d1-111">`S_OK` 如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e6d1-112">要求</span><span class="sxs-lookup"><span data-stu-id="7e6d1-112">Requirements</span></span>  
 <span data-ttu-id="7e6d1-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7e6d1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e6d1-114">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7e6d1-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7e6d1-115">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7e6d1-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e6d1-116">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e6d1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e6d1-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e6d1-117">See Also</span></span>  
 [<span data-ttu-id="7e6d1-118">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="7e6d1-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
