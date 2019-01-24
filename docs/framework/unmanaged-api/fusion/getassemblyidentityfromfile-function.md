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
ms.openlocfilehash: feb8e5c56ee6ea766cd5f1d10af42699777db453
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654877"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="d3b0f-102">GetAssemblyIdentityFromFile 函数</span><span class="sxs-lookup"><span data-stu-id="d3b0f-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="d3b0f-103">获取一个指向`IUnknown`对象具有指定`IID`中程序集在指定的文件路径。</span><span class="sxs-lookup"><span data-stu-id="d3b0f-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3b0f-104">语法</span><span class="sxs-lookup"><span data-stu-id="d3b0f-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d3b0f-105">参数</span><span class="sxs-lookup"><span data-stu-id="d3b0f-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="d3b0f-106">[in]为请求的程序集是有效路径。</span><span class="sxs-lookup"><span data-stu-id="d3b0f-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="d3b0f-107">[in]`IID`要返回的接口。</span><span class="sxs-lookup"><span data-stu-id="d3b0f-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="d3b0f-108">[out]返回的接口指针。</span><span class="sxs-lookup"><span data-stu-id="d3b0f-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3b0f-109">要求</span><span class="sxs-lookup"><span data-stu-id="d3b0f-109">Requirements</span></span>  
 <span data-ttu-id="d3b0f-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d3b0f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3b0f-111">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="d3b0f-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d3b0f-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3b0f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3b0f-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3b0f-113">See also</span></span>
- [<span data-ttu-id="d3b0f-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="d3b0f-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="d3b0f-115">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="d3b0f-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
