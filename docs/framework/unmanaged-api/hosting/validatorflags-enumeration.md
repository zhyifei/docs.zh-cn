---
title: ValidatorFlags 枚举
ms.date: 03/30/2017
api_name:
- ValidatorFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ValidatorFlags
helpviewer_keywords:
- ValidatorFlags enumeration [.NET Framework hosting]
ms.assetid: a3f5c266-3fcc-4ad1-aaf5-4cdbe26304ad
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa10ae1cf67339a6719210f3162f19ac648e8ee5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127408"
---
# <a name="validatorflags-enumeration"></a><span data-ttu-id="5b9ac-102">ValidatorFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="5b9ac-102">ValidatorFlags Enumeration</span></span>
<span data-ttu-id="5b9ac-103">包含指示应在调用中执行的验证类型的值[iclrvalidator:: Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5b9ac-103">Contains values that indicate the type of validation that should be performed in a call to the [ICLRValidator::Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b9ac-104">语法</span><span class="sxs-lookup"><span data-stu-id="5b9ac-104">Syntax</span></span>  
  
```  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a><span data-ttu-id="5b9ac-105">成员</span><span class="sxs-lookup"><span data-stu-id="5b9ac-105">Members</span></span>  
  
|<span data-ttu-id="5b9ac-106">成员</span><span class="sxs-lookup"><span data-stu-id="5b9ac-106">Member</span></span>|<span data-ttu-id="5b9ac-107">描述</span><span class="sxs-lookup"><span data-stu-id="5b9ac-107">Description</span></span>|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|<span data-ttu-id="5b9ac-108">指定应验证仅 Microsoft 中间语言 (MSIL) 中的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="5b9ac-108">Specifies that only the Microsoft intermediate language (MSIL) in the executable file should be validated.</span></span>|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|<span data-ttu-id="5b9ac-109">指定应验证仅可执行文件的格式。</span><span class="sxs-lookup"><span data-stu-id="5b9ac-109">Specifies that only the format of the executable file should be validated.</span></span>|  
|`VALIDATOR_EXTRA_VERBOSE`|<span data-ttu-id="5b9ac-110">指定应执行和报告所有类型的验证。</span><span class="sxs-lookup"><span data-stu-id="5b9ac-110">Specifies that all types of validation should be performed and reported on.</span></span>|  
|`VALIDATOR_NOCHECK_PEFORMAT`|<span data-ttu-id="5b9ac-111">指定不应验证可执行文件的格式。</span><span class="sxs-lookup"><span data-stu-id="5b9ac-111">Specifies that the format of the executable file should not be validated.</span></span>|  
|`VALIDATOR_SHOW_SOURCE_LINES`|<span data-ttu-id="5b9ac-112">指定验证错误消息应包含引发验证错误的源代码行。</span><span class="sxs-lookup"><span data-stu-id="5b9ac-112">Specifies that validation error messages should include the lines of source code that raise validation errors.</span></span> <span data-ttu-id="5b9ac-113">此字段值不是在.NET Framework 2.0 版中有效。</span><span class="sxs-lookup"><span data-stu-id="5b9ac-113">This field value is not valid in the .NET Framework version 2.0.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5b9ac-114">要求</span><span class="sxs-lookup"><span data-stu-id="5b9ac-114">Requirements</span></span>  
 <span data-ttu-id="5b9ac-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5b9ac-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b9ac-116">**标头：** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="5b9ac-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="5b9ac-117">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5b9ac-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b9ac-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b9ac-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b9ac-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b9ac-119">See also</span></span>

- [<span data-ttu-id="5b9ac-120">ICLRErrorReportingManager 接口</span><span class="sxs-lookup"><span data-stu-id="5b9ac-120">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="5b9ac-121">承载枚举</span><span class="sxs-lookup"><span data-stu-id="5b9ac-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
