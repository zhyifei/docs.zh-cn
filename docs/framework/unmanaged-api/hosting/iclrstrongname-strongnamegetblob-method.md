---
title: ICLRStrongName::StrongNameGetBlob 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlob
- ICLRStrongName.StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlob
helpviewer_keywords:
- ICLRStrongName::StrongNameGetBlob method [.NET Framework hosting]
- StrongNameGetBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: a24218f8-7196-44be-b7a2-ee9cdd7a85c4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4621a7d143d401d4cb620ac17c31e4ee5f13837
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45692893"
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="f569e-102">ICLRStrongName::StrongNameGetBlob 方法</span><span class="sxs-lookup"><span data-stu-id="f569e-102">ICLRStrongName::StrongNameGetBlob Method</span></span>
<span data-ttu-id="f569e-103">使用指定地址处可执行文件的二进制表示形式填充指定的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="f569e-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f569e-104">语法</span><span class="sxs-lookup"><span data-stu-id="f569e-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f569e-105">参数</span><span class="sxs-lookup"><span data-stu-id="f569e-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="f569e-106">[in]要加载的可执行文件是有效路径。</span><span class="sxs-lookup"><span data-stu-id="f569e-106">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="f569e-107">[in]若要加载的可执行文件读入的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="f569e-107">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="f569e-108">[in、 out]请求的最大大小，以字节为单位， `pbBlob`。</span><span class="sxs-lookup"><span data-stu-id="f569e-108">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="f569e-109">在返回时，实际大小，以字节为单位的`pbBlob`。</span><span class="sxs-lookup"><span data-stu-id="f569e-109">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f569e-110">返回值</span><span class="sxs-lookup"><span data-stu-id="f569e-110">Return Value</span></span>  
 <span data-ttu-id="f569e-111">`S_OK` 如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="f569e-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f569e-112">要求</span><span class="sxs-lookup"><span data-stu-id="f569e-112">Requirements</span></span>  
 <span data-ttu-id="f569e-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f569e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f569e-114">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f569e-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f569e-115">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f569e-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f569e-116">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f569e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f569e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="f569e-117">See Also</span></span>  
 [<span data-ttu-id="f569e-118">StrongNameGetBlobFromImage 方法</span><span class="sxs-lookup"><span data-stu-id="f569e-118">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [<span data-ttu-id="f569e-119">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="f569e-119">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
