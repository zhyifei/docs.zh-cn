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
ms.openlocfilehash: 6f34a9aac31fe50974a6f88416d0a00cd72aca8e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511925"
---
# <a name="iclrvalidator-interface"></a><span data-ttu-id="0b9df-102">ICLRValidator 接口</span><span class="sxs-lookup"><span data-stu-id="0b9df-102">ICLRValidator Interface</span></span>
<span data-ttu-id="0b9df-103">提供用于验证可移植可执行 (PE) 映像和报告验证错误的方法。</span><span class="sxs-lookup"><span data-stu-id="0b9df-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0b9df-104">方法</span><span class="sxs-lookup"><span data-stu-id="0b9df-104">Methods</span></span>  
  
|<span data-ttu-id="0b9df-105">方法</span><span class="sxs-lookup"><span data-stu-id="0b9df-105">Method</span></span>|<span data-ttu-id="0b9df-106">描述</span><span class="sxs-lookup"><span data-stu-id="0b9df-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0b9df-107">FormatEventInfo 方法</span><span class="sxs-lookup"><span data-stu-id="0b9df-107">FormatEventInfo Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-formateventinfo-method.md)|<span data-ttu-id="0b9df-108">获取有关指定的验证错误的详细的消息。</span><span class="sxs-lookup"><span data-stu-id="0b9df-108">Gets a detailed message about the specified validation error.</span></span>|  
|[<span data-ttu-id="0b9df-109">Validate 方法</span><span class="sxs-lookup"><span data-stu-id="0b9df-109">Validate Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md)|<span data-ttu-id="0b9df-110">验证的可移植可执行文件或指定文件中的 Microsoft 中间语言 (MSIL)。</span><span class="sxs-lookup"><span data-stu-id="0b9df-110">Validates the portable executable or Microsoft intermediate language (MSIL) in the specified file.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0b9df-111">要求</span><span class="sxs-lookup"><span data-stu-id="0b9df-111">Requirements</span></span>  
 <span data-ttu-id="0b9df-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0b9df-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b9df-113">**标头：** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="0b9df-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="0b9df-114">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0b9df-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b9df-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b9df-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b9df-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b9df-116">See also</span></span>
- [<span data-ttu-id="0b9df-117">ICLRErrorReportingManager 接口</span><span class="sxs-lookup"><span data-stu-id="0b9df-117">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="0b9df-118">承载接口</span><span class="sxs-lookup"><span data-stu-id="0b9df-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="0b9df-119">CLRRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="0b9df-119">CLRRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
