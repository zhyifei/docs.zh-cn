---
title: "CreateInstallReferenceEnum 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: CreateInstallReference
helpviewer_keywords: CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a0c902cf5d9d8b6295cab95552aae6775c5bf889
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="b067d-102">CreateInstallReferenceEnum 函数</span><span class="sxs-lookup"><span data-stu-id="b067d-102">CreateInstallReferenceEnum Function</span></span>
<span data-ttu-id="b067d-103">获取一个指向[IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)表示的指定程序集的应用程序的引用列表的实例。</span><span class="sxs-lookup"><span data-stu-id="b067d-103">Gets a pointer to an [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b067d-104">语法</span><span class="sxs-lookup"><span data-stu-id="b067d-104">Syntax</span></span>  
  
```  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b067d-105">参数</span><span class="sxs-lookup"><span data-stu-id="b067d-105">Parameters</span></span>  
 `ppRefEnum`  
 <span data-ttu-id="b067d-106">[out]返回`IInstallReferenceEnum`指针。</span><span class="sxs-lookup"><span data-stu-id="b067d-106">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="b067d-107">[in][IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) ，它标识要枚举引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="b067d-107">[in] The [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b067d-108">[in]影响枚举器的行为的标志。</span><span class="sxs-lookup"><span data-stu-id="b067d-108">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="b067d-109">[in]留待将来扩展。</span><span class="sxs-lookup"><span data-stu-id="b067d-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="b067d-110">`pvReserved`必须是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="b067d-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b067d-111">惠?</span><span class="sxs-lookup"><span data-stu-id="b067d-111">Requirements</span></span>  
 <span data-ttu-id="b067d-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b067d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b067d-113">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="b067d-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b067d-114">**库：**为 Fusion.dll 和 Mscorwks.dll。</span><span class="sxs-lookup"><span data-stu-id="b067d-114">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="b067d-115">使用而不是 Mscorwks.dll 为 Fusion.dll 来确保面向.NET Framework 的正确版本。</span><span class="sxs-lookup"><span data-stu-id="b067d-115">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="b067d-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b067d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b067d-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="b067d-117">See Also</span></span>  
 [<span data-ttu-id="b067d-118">IInstallReferenceEnum 接口</span><span class="sxs-lookup"><span data-stu-id="b067d-118">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)  
 [<span data-ttu-id="b067d-119">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="b067d-119">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="b067d-120">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="b067d-120">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
