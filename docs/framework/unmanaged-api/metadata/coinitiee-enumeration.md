---
title: COINITIEE 枚举
ms.date: 03/30/2017
api_name:
- COINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COINITIEE
helpviewer_keywords:
- COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type:
- apiref
ms.openlocfilehash: 2ccc038b4420040779dae70f15e3a8827ba94180
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444106"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="6b6f6-102">COINITIEE 枚举</span><span class="sxs-lookup"><span data-stu-id="6b6f6-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="6b6f6-103">Specifies constants used by [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) when initializing the common language runtime.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-103">Specifies constants used by [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b6f6-104">语法</span><span class="sxs-lookup"><span data-stu-id="6b6f6-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="6b6f6-105">Members</span><span class="sxs-lookup"><span data-stu-id="6b6f6-105">Members</span></span>  
  
|<span data-ttu-id="6b6f6-106">成员</span><span class="sxs-lookup"><span data-stu-id="6b6f6-106">Member</span></span>|<span data-ttu-id="6b6f6-107">描述</span><span class="sxs-lookup"><span data-stu-id="6b6f6-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="6b6f6-108">Default initialization mode.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-108">Default initialization mode.</span></span> <span data-ttu-id="6b6f6-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="6b6f6-110">Initializes to run a managed DLL.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="6b6f6-111">Initializes to run a managed EXE.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="6b6f6-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span><span class="sxs-lookup"><span data-stu-id="6b6f6-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6b6f6-113">要求</span><span class="sxs-lookup"><span data-stu-id="6b6f6-113">Requirements</span></span>  
 <span data-ttu-id="6b6f6-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6b6f6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b6f6-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6b6f6-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6b6f6-116">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6b6f6-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6b6f6-117">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b6f6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b6f6-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b6f6-118">See also</span></span>

- [<span data-ttu-id="6b6f6-119">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="6b6f6-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
