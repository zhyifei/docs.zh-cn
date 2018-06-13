---
title: CoInitializeEE 函数
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bbd25909e70826f8cd29076c1eb62a4da6779cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435396"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="b06ef-102">CoInitializeEE 函数</span><span class="sxs-lookup"><span data-stu-id="b06ef-102">CoInitializeEE Function</span></span>
<span data-ttu-id="b06ef-103">确保公共语言运行时执行引擎已加载到进程。</span><span class="sxs-lookup"><span data-stu-id="b06ef-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="b06ef-104">此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b06ef-104">This function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="b06ef-105">使用[iclrruntimehost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="b06ef-105">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b06ef-106">语法</span><span class="sxs-lookup"><span data-stu-id="b06ef-106">Syntax</span></span>  
  
```  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b06ef-107">参数</span><span class="sxs-lookup"><span data-stu-id="b06ef-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="b06ef-108">[in]之一[COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md)枚举常量。</span><span class="sxs-lookup"><span data-stu-id="b06ef-108">[in] One of the [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b06ef-109">返回值</span><span class="sxs-lookup"><span data-stu-id="b06ef-109">Return Value</span></span>  
 <span data-ttu-id="b06ef-110">Winerror.h 和下表中的值中定义，此方法将返回标准的 COM 错误代码。</span><span class="sxs-lookup"><span data-stu-id="b06ef-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="b06ef-111">返回代码</span><span class="sxs-lookup"><span data-stu-id="b06ef-111">Return code</span></span>|<span data-ttu-id="b06ef-112">描述</span><span class="sxs-lookup"><span data-stu-id="b06ef-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="b06ef-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b06ef-113">S_OK</span></span>|<span data-ttu-id="b06ef-114">执行引擎已成功加载。</span><span class="sxs-lookup"><span data-stu-id="b06ef-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="b06ef-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b06ef-115">S_FALSE</span></span>|<span data-ttu-id="b06ef-116">执行引擎已加载。</span><span class="sxs-lookup"><span data-stu-id="b06ef-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="b06ef-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b06ef-117">E_FAIL</span></span>|<span data-ttu-id="b06ef-118">无法加载执行引擎。</span><span class="sxs-lookup"><span data-stu-id="b06ef-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b06ef-119">备注</span><span class="sxs-lookup"><span data-stu-id="b06ef-119">Remarks</span></span>  
 <span data-ttu-id="b06ef-120">如果它尚未以前加载，则此方法将加载的执行引擎。</span><span class="sxs-lookup"><span data-stu-id="b06ef-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b06ef-121">要求</span><span class="sxs-lookup"><span data-stu-id="b06ef-121">Requirements</span></span>  
 <span data-ttu-id="b06ef-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b06ef-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b06ef-123">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b06ef-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b06ef-124">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b06ef-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b06ef-125">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b06ef-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b06ef-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="b06ef-126">See Also</span></span>  
 [<span data-ttu-id="b06ef-127">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="b06ef-127">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
