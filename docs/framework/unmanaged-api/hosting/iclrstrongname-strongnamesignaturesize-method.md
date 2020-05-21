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
ms.openlocfilehash: edce771b3c36f2c56637aa2a21fe524be0ae12c8
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763015"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="6b40d-102">ICLRStrongName::StrongNameSignatureSize 方法</span><span class="sxs-lookup"><span data-stu-id="6b40d-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="6b40d-103">返回强名称签名的大小。</span><span class="sxs-lookup"><span data-stu-id="6b40d-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="6b40d-104">此方法通常由编译器用来确定在创建延迟签名程序集时要在文件中保留多少空间。</span><span class="sxs-lookup"><span data-stu-id="6b40d-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b40d-105">语法</span><span class="sxs-lookup"><span data-stu-id="6b40d-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="6b40d-106">参数</span><span class="sxs-lookup"><span data-stu-id="6b40d-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="6b40d-107">中[PublicKeyBlob](../strong-naming/publickeyblob-structure.md)类型的结构，它包含用于生成强名称签名的密钥对的公共部分。</span><span class="sxs-lookup"><span data-stu-id="6b40d-107">[in] A structure of type [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="6b40d-108">中的大小（以字节为单位） `pbPublicKeyBlob` 。</span><span class="sxs-lookup"><span data-stu-id="6b40d-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="6b40d-109">中存储强名称签名所需的字节数。</span><span class="sxs-lookup"><span data-stu-id="6b40d-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b40d-110">返回值</span><span class="sxs-lookup"><span data-stu-id="6b40d-110">Return Value</span></span>  
 <span data-ttu-id="6b40d-111">`S_OK`如果该方法已成功完成，则为;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。</span><span class="sxs-lookup"><span data-stu-id="6b40d-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b40d-112">要求</span><span class="sxs-lookup"><span data-stu-id="6b40d-112">Requirements</span></span>  
 <span data-ttu-id="6b40d-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6b40d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b40d-114">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="6b40d-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6b40d-115">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="6b40d-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b40d-116">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b40d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b40d-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b40d-117">See also</span></span>

- [<span data-ttu-id="6b40d-118">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="6b40d-118">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
