---
title: CloseAssembly 方法
ms.date: 03/30/2017
api_name:
- IALink.CloseAssembly
- CloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseAssembly
helpviewer_keywords:
- CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c89fd080e61db78ed21c03c2aa63c97337c09585
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497543"
---
# <a name="closeassembly-method"></a><span data-ttu-id="1fedc-102">CloseAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="1fedc-102">CloseAssembly Method</span></span>
<span data-ttu-id="1fedc-103">确定程序集操作。</span><span class="sxs-lookup"><span data-stu-id="1fedc-103">Finalizes assembly operations.</span></span> <span data-ttu-id="1fedc-104">在开始新的程序集或未绑定的模块之前调用此方法。</span><span class="sxs-lookup"><span data-stu-id="1fedc-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fedc-105">语法</span><span class="sxs-lookup"><span data-stu-id="1fedc-105">Syntax</span></span>  
  
```  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fedc-106">参数</span><span class="sxs-lookup"><span data-stu-id="1fedc-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1fedc-107">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="1fedc-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1fedc-108">返回值</span><span class="sxs-lookup"><span data-stu-id="1fedc-108">Return Value</span></span>  
 <span data-ttu-id="1fedc-109">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="1fedc-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fedc-110">要求</span><span class="sxs-lookup"><span data-stu-id="1fedc-110">Requirements</span></span>  
 <span data-ttu-id="1fedc-111">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="1fedc-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fedc-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1fedc-112">See also</span></span>
- [<span data-ttu-id="1fedc-113">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="1fedc-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="1fedc-114">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="1fedc-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="1fedc-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="1fedc-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
