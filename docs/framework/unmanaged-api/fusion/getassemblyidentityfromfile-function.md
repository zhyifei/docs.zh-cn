---
title: GetAssemblyIdentityFromFile 函数
ms.date: 03/30/2017
api_name:
- GetAssemblyIdentityFromFile
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyIdentityFromFile
helpviewer_keywords:
- GetAssemblyIdentityFromFile function [.NET Framework fusion]
ms.assetid: 2c32da53-76c7-4048-84d0-d05207333004
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5ea151417a1cb53104ec29fff1e76e21f82ec9bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431638"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="bbf9a-102">GetAssemblyIdentityFromFile 函数</span><span class="sxs-lookup"><span data-stu-id="bbf9a-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="bbf9a-103">获取一个指向`IUnknown`使用指定的对象`IID`中处指定的文件路径的程序集。</span><span class="sxs-lookup"><span data-stu-id="bbf9a-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbf9a-104">语法</span><span class="sxs-lookup"><span data-stu-id="bbf9a-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bbf9a-105">参数</span><span class="sxs-lookup"><span data-stu-id="bbf9a-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="bbf9a-106">[in]请求的程序集的有效路径。</span><span class="sxs-lookup"><span data-stu-id="bbf9a-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="bbf9a-107">[in]`IID`要返回的接口。</span><span class="sxs-lookup"><span data-stu-id="bbf9a-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="bbf9a-108">[out]返回的接口指针。</span><span class="sxs-lookup"><span data-stu-id="bbf9a-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbf9a-109">要求</span><span class="sxs-lookup"><span data-stu-id="bbf9a-109">Requirements</span></span>  
 <span data-ttu-id="bbf9a-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bbf9a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbf9a-111">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="bbf9a-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="bbf9a-112">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbf9a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbf9a-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="bbf9a-113">See Also</span></span>  
 <span data-ttu-id="bbf9a-114"><<!--zzxref:IUnknown --> `IUnknown`></span><span class="sxs-lookup"><span data-stu-id="bbf9a-114"><<!--zzxref:IUnknown --> `IUnknown`></span></span>  
 [<span data-ttu-id="bbf9a-115">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="bbf9a-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
