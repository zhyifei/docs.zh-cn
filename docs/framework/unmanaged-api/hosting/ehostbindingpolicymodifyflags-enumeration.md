---
title: EHostBindingPolicyModifyFlags 枚举
ms.date: 03/30/2017
api_name:
- EHostBindingPolicyModifyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EHostBindingPolicyModifyFlags
helpviewer_keywords:
- EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type:
- apiref
ms.openlocfilehash: 256c362ae0aea51fea16ce799db243b105dee81a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616237"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="935db-102">EHostBindingPolicyModifyFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="935db-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="935db-103">允许主机指定公共语言运行时（CLR）在将策略修改从源程序集应用到目标程序集时应执行的重定向的类型。</span><span class="sxs-lookup"><span data-stu-id="935db-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="935db-104">语法</span><span class="sxs-lookup"><span data-stu-id="935db-104">Syntax</span></span>  
  
```cpp  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="935db-105">成员</span><span class="sxs-lookup"><span data-stu-id="935db-105">Members</span></span>  
  
|<span data-ttu-id="935db-106">成员</span><span class="sxs-lookup"><span data-stu-id="935db-106">Member</span></span>|<span data-ttu-id="935db-107">描述</span><span class="sxs-lookup"><span data-stu-id="935db-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="935db-108">指定 CLR 将源程序集的策略值链接到目标程序集的策略值。</span><span class="sxs-lookup"><span data-stu-id="935db-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="935db-109">指定 CLR 将执行默认操作。</span><span class="sxs-lookup"><span data-stu-id="935db-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="935db-110">指定 CLR 将目标程序集的策略值设置为最大值。</span><span class="sxs-lookup"><span data-stu-id="935db-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="935db-111">指定 CLR 将目标程序集的策略值替换为源程序集的策略值。</span><span class="sxs-lookup"><span data-stu-id="935db-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="935db-112">备注</span><span class="sxs-lookup"><span data-stu-id="935db-112">Remarks</span></span>  
 <span data-ttu-id="935db-113">[ICLRHostBindingPolicyManager：： ModifyApplicationPolicy](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)方法采用类型的参数 `EHostBindingPolicyModifyFlags` 。</span><span class="sxs-lookup"><span data-stu-id="935db-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="935db-114">要求</span><span class="sxs-lookup"><span data-stu-id="935db-114">Requirements</span></span>  
 <span data-ttu-id="935db-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="935db-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="935db-116">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="935db-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="935db-117">**库：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="935db-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="935db-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="935db-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="935db-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="935db-119">See also</span></span>

- [<span data-ttu-id="935db-120">ICLRHostBindingPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="935db-120">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="935db-121">承载枚举</span><span class="sxs-lookup"><span data-stu-id="935db-121">Hosting Enumerations</span></span>](hosting-enumerations.md)
