---
title: PreCloseAssembly 方法
ms.date: 03/30/2017
api_name:
- IALink.PreCloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- PreCloseAssembly
helpviewer_keywords:
- PreCloseAssembly method
ms.assetid: 6d23ac54-15ea-4027-a172-9ebef43e8f56
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e1aeffbd5d5b22bea87dd7a49a3268822ce84d38
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481166"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="5c243-102">PreCloseAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="5c243-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="5c243-103">关闭该程序集文件。</span><span class="sxs-lookup"><span data-stu-id="5c243-103">Closes the assembly file.</span></span> <span data-ttu-id="5c243-104">在关闭所有其他文件，但在关闭的程序集文件之前，请调用此方法。</span><span class="sxs-lookup"><span data-stu-id="5c243-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="5c243-105">请勿对未绑定模块调用此方法。</span><span class="sxs-lookup"><span data-stu-id="5c243-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c243-106">语法</span><span class="sxs-lookup"><span data-stu-id="5c243-106">Syntax</span></span>  
  
```  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c243-107">参数</span><span class="sxs-lookup"><span data-stu-id="5c243-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="5c243-108">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="5c243-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5c243-109">返回值</span><span class="sxs-lookup"><span data-stu-id="5c243-109">Return Value</span></span>  
 <span data-ttu-id="5c243-110">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="5c243-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c243-111">要求</span><span class="sxs-lookup"><span data-stu-id="5c243-111">Requirements</span></span>  
 <span data-ttu-id="5c243-112">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="5c243-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c243-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c243-113">See also</span></span>
- [<span data-ttu-id="5c243-114">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="5c243-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="5c243-115">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="5c243-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="5c243-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="5c243-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
