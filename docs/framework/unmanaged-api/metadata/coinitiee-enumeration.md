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
ms.openlocfilehash: b4d0ad0c8651fe10bd2a1c72a8a995846cc80a55
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440773"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="6511f-102">COINITIEE 枚举</span><span class="sxs-lookup"><span data-stu-id="6511f-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="6511f-103">指定使用的常量[CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)初始化公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="6511f-103">Specifies constants used by [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6511f-104">语法</span><span class="sxs-lookup"><span data-stu-id="6511f-104">Syntax</span></span>  
  
```  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="6511f-105">成员</span><span class="sxs-lookup"><span data-stu-id="6511f-105">Members</span></span>  
  
|<span data-ttu-id="6511f-106">成员</span><span class="sxs-lookup"><span data-stu-id="6511f-106">Member</span></span>|<span data-ttu-id="6511f-107">描述</span><span class="sxs-lookup"><span data-stu-id="6511f-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="6511f-108">默认值初始化模式。</span><span class="sxs-lookup"><span data-stu-id="6511f-108">Default initialization mode.</span></span> <span data-ttu-id="6511f-109">此初始化运行时并创建默认<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="6511f-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="6511f-110">初始化运行了托管的 DLL。</span><span class="sxs-lookup"><span data-stu-id="6511f-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="6511f-111">初始化运行托管可执行程序。</span><span class="sxs-lookup"><span data-stu-id="6511f-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="6511f-112">此初始化运行时，但不会创建默认值<xref:System.AppDomain>，它在输入该 exe 文件的 main 例程后在创建。</span><span class="sxs-lookup"><span data-stu-id="6511f-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6511f-113">要求</span><span class="sxs-lookup"><span data-stu-id="6511f-113">Requirements</span></span>  
 <span data-ttu-id="6511f-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6511f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6511f-115">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6511f-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6511f-116">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6511f-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6511f-117">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6511f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6511f-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="6511f-118">See Also</span></span>  
 [<span data-ttu-id="6511f-119">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="6511f-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
