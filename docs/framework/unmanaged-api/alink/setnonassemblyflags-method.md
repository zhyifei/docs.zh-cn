---
title: SetNonAssemblyFlags 方法
ms.date: 03/30/2017
api_name:
- IALink.SetNonAssemblyFlags
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetNonAssemblyFlags
helpviewer_keywords:
- SetNonAssemblyFlags method
ms.assetid: f8ba6fc8-f5aa-4066-ac96-56332758f5ec
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d6c07a6679326548535985e4c938c3fddbb2a0cf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500208"
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="27ab7-102">SetNonAssemblyFlags 方法</span><span class="sxs-lookup"><span data-stu-id="27ab7-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="27ab7-103">设置不是特定于程序集的标志。</span><span class="sxs-lookup"><span data-stu-id="27ab7-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27ab7-104">语法</span><span class="sxs-lookup"><span data-stu-id="27ab7-104">Syntax</span></span>  
  
```  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="27ab7-105">参数</span><span class="sxs-lookup"><span data-stu-id="27ab7-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="27ab7-106">ALink 标志。</span><span class="sxs-lookup"><span data-stu-id="27ab7-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27ab7-107">返回值</span><span class="sxs-lookup"><span data-stu-id="27ab7-107">Return Value</span></span>  
 <span data-ttu-id="27ab7-108">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="27ab7-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27ab7-109">要求</span><span class="sxs-lookup"><span data-stu-id="27ab7-109">Requirements</span></span>  
 <span data-ttu-id="27ab7-110">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="27ab7-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27ab7-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="27ab7-111">See also</span></span>
- [<span data-ttu-id="27ab7-112">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="27ab7-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="27ab7-113">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="27ab7-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="27ab7-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="27ab7-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
