---
title: ICeeGen::GetIlSection 方法
ms.date: 03/30/2017
api_name:
- ICeeGen.GetIlSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetIlSection
helpviewer_keywords:
- GetIlSection method [.NET Framework metadata]
- ICeeGen::GetIlSection method [.NET Framework metadata]
ms.assetid: 6f2db2ca-203f-4ac3-9530-208642ca385e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e75f46d73e068c6bdaac6ae01740ecf589c97d42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54635905"
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="d0582-102">ICeeGen::GetIlSection 方法</span><span class="sxs-lookup"><span data-stu-id="d0582-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="d0582-103">获取由指定句柄引用的基的中间语言代码的节。</span><span class="sxs-lookup"><span data-stu-id="d0582-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="d0582-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="d0582-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0582-105">语法</span><span class="sxs-lookup"><span data-stu-id="d0582-105">Syntax</span></span>  
  
```  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d0582-106">参数</span><span class="sxs-lookup"><span data-stu-id="d0582-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="d0582-107">[in]部分以获取句柄。</span><span class="sxs-lookup"><span data-stu-id="d0582-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0582-108">要求</span><span class="sxs-lookup"><span data-stu-id="d0582-108">Requirements</span></span>  
 <span data-ttu-id="d0582-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d0582-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0582-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d0582-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d0582-111">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d0582-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d0582-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0582-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0582-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0582-113">See also</span></span>
- [<span data-ttu-id="d0582-114">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="d0582-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
