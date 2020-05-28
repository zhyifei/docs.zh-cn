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
ms.openlocfilehash: f4d1c2f105abb64bf196d0dd8371c2788c97336e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005903"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="cfc30-102">COINITIEE 枚举</span><span class="sxs-lookup"><span data-stu-id="cfc30-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="cfc30-103">指定初始化公共语言运行时[CoInitializeEE](../hosting/coinitializeee-function.md)使用的常量。</span><span class="sxs-lookup"><span data-stu-id="cfc30-103">Specifies constants used by [CoInitializeEE](../hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfc30-104">语法</span><span class="sxs-lookup"><span data-stu-id="cfc30-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="cfc30-105">成员</span><span class="sxs-lookup"><span data-stu-id="cfc30-105">Members</span></span>  
  
|<span data-ttu-id="cfc30-106">成员</span><span class="sxs-lookup"><span data-stu-id="cfc30-106">Member</span></span>|<span data-ttu-id="cfc30-107">描述</span><span class="sxs-lookup"><span data-stu-id="cfc30-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="cfc30-108">默认初始化模式。</span><span class="sxs-lookup"><span data-stu-id="cfc30-108">Default initialization mode.</span></span> <span data-ttu-id="cfc30-109">这将初始化运行时并创建默认值 <xref:System.AppDomain> 。</span><span class="sxs-lookup"><span data-stu-id="cfc30-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="cfc30-110">初始化以运行托管 DLL。</span><span class="sxs-lookup"><span data-stu-id="cfc30-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="cfc30-111">初始化以运行托管 EXE。</span><span class="sxs-lookup"><span data-stu-id="cfc30-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="cfc30-112">这将初始化运行时，但不会创建默认值 <xref:System.AppDomain> ，该默认值是在输入 EXE 的主例程之后创建的。</span><span class="sxs-lookup"><span data-stu-id="cfc30-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cfc30-113">要求</span><span class="sxs-lookup"><span data-stu-id="cfc30-113">Requirements</span></span>  
 <span data-ttu-id="cfc30-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cfc30-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfc30-115">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="cfc30-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cfc30-116">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="cfc30-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cfc30-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfc30-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfc30-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cfc30-118">See also</span></span>

- [<span data-ttu-id="cfc30-119">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="cfc30-119">Metadata Enumerations</span></span>](metadata-enumerations.md)
