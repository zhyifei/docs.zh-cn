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
ms.openlocfilehash: 7f6865c3d6dffa3b551d4e5e0636b1e386be8baa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134983"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="dd435-102">ICLRStrongName::StrongNameSignatureSize 方法</span><span class="sxs-lookup"><span data-stu-id="dd435-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="dd435-103">返回强名称签名的大小。</span><span class="sxs-lookup"><span data-stu-id="dd435-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="dd435-104">此方法通常由编译器用来确定在创建延迟签名程序集时要在文件中保留多少空间。</span><span class="sxs-lookup"><span data-stu-id="dd435-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd435-105">语法</span><span class="sxs-lookup"><span data-stu-id="dd435-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="dd435-106">参数</span><span class="sxs-lookup"><span data-stu-id="dd435-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="dd435-107">中[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)类型的结构，它包含用于生成强名称签名的密钥对的公共部分。</span><span class="sxs-lookup"><span data-stu-id="dd435-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="dd435-108">中`pbPublicKeyBlob`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="dd435-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="dd435-109">中存储强名称签名所需的字节数。</span><span class="sxs-lookup"><span data-stu-id="dd435-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd435-110">返回值</span><span class="sxs-lookup"><span data-stu-id="dd435-110">Return Value</span></span>  
 <span data-ttu-id="dd435-111">如果方法已成功完成，则 `S_OK`;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)）。</span><span class="sxs-lookup"><span data-stu-id="dd435-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd435-112">要求</span><span class="sxs-lookup"><span data-stu-id="dd435-112">Requirements</span></span>  
 <span data-ttu-id="dd435-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dd435-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd435-114">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="dd435-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="dd435-115">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="dd435-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd435-116">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd435-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd435-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd435-117">See also</span></span>

- [<span data-ttu-id="dd435-118">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="dd435-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
