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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4a84fdfdba96c58671302c723b8a56848b70eb60
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984121"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="d050e-102">COINITIEE 枚举</span><span class="sxs-lookup"><span data-stu-id="d050e-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="d050e-103">指定使用的常量[CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)初始化公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="d050e-103">Specifies constants used by [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d050e-104">语法</span><span class="sxs-lookup"><span data-stu-id="d050e-104">Syntax</span></span>  
  
```  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="d050e-105">成员</span><span class="sxs-lookup"><span data-stu-id="d050e-105">Members</span></span>  
  
|<span data-ttu-id="d050e-106">成员</span><span class="sxs-lookup"><span data-stu-id="d050e-106">Member</span></span>|<span data-ttu-id="d050e-107">描述</span><span class="sxs-lookup"><span data-stu-id="d050e-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="d050e-108">默认初始化模式。</span><span class="sxs-lookup"><span data-stu-id="d050e-108">Default initialization mode.</span></span> <span data-ttu-id="d050e-109">此初始化运行时和创建默认<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="d050e-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="d050e-110">若要运行的托管的 DLL 的初始化。</span><span class="sxs-lookup"><span data-stu-id="d050e-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="d050e-111">初始化运行托管可执行程序。</span><span class="sxs-lookup"><span data-stu-id="d050e-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="d050e-112">此初始化运行时，但不会创建默认<xref:System.AppDomain>，其中输入主例程中的 EXE 后创建的。</span><span class="sxs-lookup"><span data-stu-id="d050e-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d050e-113">要求</span><span class="sxs-lookup"><span data-stu-id="d050e-113">Requirements</span></span>  
 <span data-ttu-id="d050e-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d050e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d050e-115">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d050e-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d050e-116">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d050e-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d050e-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d050e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d050e-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d050e-118">See also</span></span>

- [<span data-ttu-id="d050e-119">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="d050e-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
