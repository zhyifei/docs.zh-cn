---
title: IValidator 接口
ms.date: 03/30/2017
api_name:
- IValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IValidator
helpviewer_keywords:
- IValidator interface [.NET Framework hosting]
ms.assetid: b297e3b0-20f9-478f-b707-5e2eecb2b5b2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e79a69bf71aee035fb1f9a0178879d7c19e62b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448916"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="664e5-102">IValidator 接口</span><span class="sxs-lookup"><span data-stu-id="664e5-102">IValidator Interface</span></span>
<span data-ttu-id="664e5-103">提供用于验证可移植可执行 (PE) 映像和报告验证错误的方法。</span><span class="sxs-lookup"><span data-stu-id="664e5-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="664e5-104">方法</span><span class="sxs-lookup"><span data-stu-id="664e5-104">Methods</span></span>  
  
|<span data-ttu-id="664e5-105">方法</span><span class="sxs-lookup"><span data-stu-id="664e5-105">Method</span></span>|<span data-ttu-id="664e5-106">描述</span><span class="sxs-lookup"><span data-stu-id="664e5-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="664e5-107">Validate</span><span class="sxs-lookup"><span data-stu-id="664e5-107">Validate</span></span>|<span data-ttu-id="664e5-108">验证指定的 PE 或 Microsoft 中间语言 (MSIL) 文件。</span><span class="sxs-lookup"><span data-stu-id="664e5-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="664e5-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="664e5-109">FormatEventInfo</span></span>|<span data-ttu-id="664e5-110">获取对应于指定的验证错误的错误消息。</span><span class="sxs-lookup"><span data-stu-id="664e5-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="664e5-111">要求</span><span class="sxs-lookup"><span data-stu-id="664e5-111">Requirements</span></span>  
 <span data-ttu-id="664e5-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="664e5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="664e5-113">**标头：** IValidator.idl、 IValidator.h</span><span class="sxs-lookup"><span data-stu-id="664e5-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="664e5-114">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="664e5-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="664e5-115">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="664e5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="664e5-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="664e5-116">See Also</span></span>  
 [<span data-ttu-id="664e5-117">承载接口</span><span class="sxs-lookup"><span data-stu-id="664e5-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="664e5-118">CorRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="664e5-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
