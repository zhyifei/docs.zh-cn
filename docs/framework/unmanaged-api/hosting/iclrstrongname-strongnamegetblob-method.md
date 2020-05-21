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
ms.openlocfilehash: f93d3f0322de89b2e9ce596329c06b58db9fdcdc
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760298"
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="ae551-102">ICLRStrongName::StrongNameGetBlob 方法</span><span class="sxs-lookup"><span data-stu-id="ae551-102">ICLRStrongName::StrongNameGetBlob Method</span></span>
<span data-ttu-id="ae551-103">使用指定地址处可执行文件的二进制表示形式填充指定的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="ae551-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae551-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae551-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae551-105">参数</span><span class="sxs-lookup"><span data-stu-id="ae551-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="ae551-106">中要加载的可执行文件的有效路径。</span><span class="sxs-lookup"><span data-stu-id="ae551-106">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="ae551-107">中要在其中加载可执行文件的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="ae551-107">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="ae551-108">[in，out]请求的最大大小（以字节为单位） `pbBlob` 。</span><span class="sxs-lookup"><span data-stu-id="ae551-108">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="ae551-109">返回时，的实际大小（以字节为单位） `pbBlob` 。</span><span class="sxs-lookup"><span data-stu-id="ae551-109">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae551-110">返回值</span><span class="sxs-lookup"><span data-stu-id="ae551-110">Return Value</span></span>  
 <span data-ttu-id="ae551-111">`S_OK`如果该方法已成功完成，则为;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。</span><span class="sxs-lookup"><span data-stu-id="ae551-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae551-112">要求</span><span class="sxs-lookup"><span data-stu-id="ae551-112">Requirements</span></span>  
 <span data-ttu-id="ae551-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae551-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae551-114">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="ae551-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ae551-115">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="ae551-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ae551-116">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae551-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae551-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae551-117">See also</span></span>

- [<span data-ttu-id="ae551-118">StrongNameGetBlobFromImage 方法</span><span class="sxs-lookup"><span data-stu-id="ae551-118">StrongNameGetBlobFromImage Method</span></span>](iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="ae551-119">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="ae551-119">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
