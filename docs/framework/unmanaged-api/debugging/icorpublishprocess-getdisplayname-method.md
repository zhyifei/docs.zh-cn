---
title: ICorPublishProcess::GetDisplayName 方法
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetDisplayName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetDisplayName
helpviewer_keywords:
- ICorPublishProcess::GetDisplayName method [.NET Framework debugging]
- GetDisplayName method, ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 7c0af9e9-a73f-41aa-a685-b21c439e059d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6e7aa845f104ef734f039d46e1eeaba5fd01c73
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221764"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="0b1e6-102">ICorPublishProcess::GetDisplayName 方法</span><span class="sxs-lookup"><span data-stu-id="0b1e6-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="0b1e6-103">获取引用此进程可执行文件的完整路径[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="0b1e6-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b1e6-104">语法</span><span class="sxs-lookup"><span data-stu-id="0b1e6-104">Syntax</span></span>  
  
```  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,   
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b1e6-105">参数</span><span class="sxs-lookup"><span data-stu-id="0b1e6-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="0b1e6-106">[in] `szName` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="0b1e6-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="0b1e6-107">[out]在中返回的宽字符数`szName`数组。</span><span class="sxs-lookup"><span data-stu-id="0b1e6-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="0b1e6-108">[out]用于存储的名称，包括可执行文件的完整路径的数组。</span><span class="sxs-lookup"><span data-stu-id="0b1e6-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="0b1e6-109">名称是以 null 结尾。</span><span class="sxs-lookup"><span data-stu-id="0b1e6-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b1e6-110">要求</span><span class="sxs-lookup"><span data-stu-id="0b1e6-110">Requirements</span></span>  
 <span data-ttu-id="0b1e6-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0b1e6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b1e6-112">**标头：** CorPub.idl CorPub.h</span><span class="sxs-lookup"><span data-stu-id="0b1e6-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="0b1e6-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b1e6-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0b1e6-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="0b1e6-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0b1e6-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b1e6-115">See also</span></span>

- [<span data-ttu-id="0b1e6-116">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="0b1e6-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
