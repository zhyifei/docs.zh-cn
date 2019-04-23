---
title: ICorRuntimeHost::MapFile 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.MapFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::MapFile
helpviewer_keywords:
- ICorRuntimeHost::MapFile method [.NET Framework hosting]
- MapFile method [.NET Framework hosting]
ms.assetid: 45ae0502-0a31-4342-b7e3-f36e1cf738f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8a979e86dbe52577d0b58089015338e4a87750d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59193871"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="a56ae-102">ICorRuntimeHost::MapFile 方法</span><span class="sxs-lookup"><span data-stu-id="a56ae-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="a56ae-103">将指定的文件映射到内存中。</span><span class="sxs-lookup"><span data-stu-id="a56ae-103">Maps the specified file into memory.</span></span> <span data-ttu-id="a56ae-104">此方法已过时。</span><span class="sxs-lookup"><span data-stu-id="a56ae-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a56ae-105">语法</span><span class="sxs-lookup"><span data-stu-id="a56ae-105">Syntax</span></span>  
  
```  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a56ae-106">参数</span><span class="sxs-lookup"><span data-stu-id="a56ae-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="a56ae-107">[in]要映射的文件句柄。</span><span class="sxs-lookup"><span data-stu-id="a56ae-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="a56ae-108">[out]开始将文件映射的起始内存地址。</span><span class="sxs-lookup"><span data-stu-id="a56ae-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a56ae-109">要求</span><span class="sxs-lookup"><span data-stu-id="a56ae-109">Requirements</span></span>  
 <span data-ttu-id="a56ae-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a56ae-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a56ae-111">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a56ae-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a56ae-112">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a56ae-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a56ae-113">**.NET framework 版本：** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="a56ae-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a56ae-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="a56ae-114">See also</span></span>

- [<span data-ttu-id="a56ae-115">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="a56ae-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
