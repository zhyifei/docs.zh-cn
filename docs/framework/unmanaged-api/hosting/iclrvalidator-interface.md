---
title: ICLRValidator 接口
ms.date: 03/30/2017
api_name:
- ICLRValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator
helpviewer_keywords:
- ICLRValidator interface [.NET Framework hosting]
ms.assetid: 2edd0a10-77fb-4173-91eb-f2970cc364d0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0cefd47d3c7298f9cc4b15eb2946f3d95aeae759
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437994"
---
# <a name="iclrvalidator-interface"></a><span data-ttu-id="28d05-102">ICLRValidator 接口</span><span class="sxs-lookup"><span data-stu-id="28d05-102">ICLRValidator Interface</span></span>
<span data-ttu-id="28d05-103">提供用于验证可移植可执行 (PE) 映像和报告验证错误的方法。</span><span class="sxs-lookup"><span data-stu-id="28d05-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="28d05-104">方法</span><span class="sxs-lookup"><span data-stu-id="28d05-104">Methods</span></span>  
  
|<span data-ttu-id="28d05-105">方法</span><span class="sxs-lookup"><span data-stu-id="28d05-105">Method</span></span>|<span data-ttu-id="28d05-106">描述</span><span class="sxs-lookup"><span data-stu-id="28d05-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="28d05-107">FormatEventInfo 方法</span><span class="sxs-lookup"><span data-stu-id="28d05-107">FormatEventInfo Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-formateventinfo-method.md)|<span data-ttu-id="28d05-108">获取有关指定的验证错误的详细的消息。</span><span class="sxs-lookup"><span data-stu-id="28d05-108">Gets a detailed message about the specified validation error.</span></span>|  
|[<span data-ttu-id="28d05-109">Validate 方法</span><span class="sxs-lookup"><span data-stu-id="28d05-109">Validate Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md)|<span data-ttu-id="28d05-110">验证的可移植可执行文件或指定文件中的 Microsoft 中间语言 (MSIL)。</span><span class="sxs-lookup"><span data-stu-id="28d05-110">Validates the portable executable or Microsoft intermediate language (MSIL) in the specified file.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="28d05-111">要求</span><span class="sxs-lookup"><span data-stu-id="28d05-111">Requirements</span></span>  
 <span data-ttu-id="28d05-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="28d05-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28d05-113">**标头：** IValidator.idl、 IValidator.h</span><span class="sxs-lookup"><span data-stu-id="28d05-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="28d05-114">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="28d05-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28d05-115">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28d05-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28d05-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="28d05-116">See Also</span></span>  
 [<span data-ttu-id="28d05-117">ICLRErrorReportingManager 接口</span><span class="sxs-lookup"><span data-stu-id="28d05-117">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [<span data-ttu-id="28d05-118">承载接口</span><span class="sxs-lookup"><span data-stu-id="28d05-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="28d05-119">CLRRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="28d05-119">CLRRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
