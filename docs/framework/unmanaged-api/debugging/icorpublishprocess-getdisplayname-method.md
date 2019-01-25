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
ms.openlocfilehash: f2d3624d130c005f9ed9109863b052e3272797ea
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496814"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="cc9db-102">ICorPublishProcess::GetDisplayName 方法</span><span class="sxs-lookup"><span data-stu-id="cc9db-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="cc9db-103">获取引用此进程可执行文件的完整路径[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="cc9db-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc9db-104">语法</span><span class="sxs-lookup"><span data-stu-id="cc9db-104">Syntax</span></span>  
  
```  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,   
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR                        *szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cc9db-105">参数</span><span class="sxs-lookup"><span data-stu-id="cc9db-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="cc9db-106">[in] `szName` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="cc9db-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="cc9db-107">[out]在中返回的宽字符数`szName`数组。</span><span class="sxs-lookup"><span data-stu-id="cc9db-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="cc9db-108">[out]用于存储的名称，包括可执行文件的完整路径的数组。</span><span class="sxs-lookup"><span data-stu-id="cc9db-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="cc9db-109">名称是以 null 结尾。</span><span class="sxs-lookup"><span data-stu-id="cc9db-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc9db-110">要求</span><span class="sxs-lookup"><span data-stu-id="cc9db-110">Requirements</span></span>  
 <span data-ttu-id="cc9db-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cc9db-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc9db-112">**标头：** CorPub.idl CorPub.h</span><span class="sxs-lookup"><span data-stu-id="cc9db-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="cc9db-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc9db-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc9db-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc9db-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc9db-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc9db-115">See also</span></span>
- [<span data-ttu-id="cc9db-116">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="cc9db-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
