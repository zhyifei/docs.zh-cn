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
ms.openlocfilehash: 78a7dab69e716e1662a277a69c008474d97f9bc4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619644"
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="20420-102">SetNonAssemblyFlags 方法</span><span class="sxs-lookup"><span data-stu-id="20420-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="20420-103">设置不是特定于程序集的标志。</span><span class="sxs-lookup"><span data-stu-id="20420-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20420-104">语法</span><span class="sxs-lookup"><span data-stu-id="20420-104">Syntax</span></span>  
  
```  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="20420-105">参数</span><span class="sxs-lookup"><span data-stu-id="20420-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="20420-106">ALink 标志。</span><span class="sxs-lookup"><span data-stu-id="20420-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20420-107">返回值</span><span class="sxs-lookup"><span data-stu-id="20420-107">Return Value</span></span>  
 <span data-ttu-id="20420-108">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="20420-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20420-109">要求</span><span class="sxs-lookup"><span data-stu-id="20420-109">Requirements</span></span>  
 <span data-ttu-id="20420-110">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="20420-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20420-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="20420-111">See also</span></span>
- [<span data-ttu-id="20420-112">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="20420-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="20420-113">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="20420-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="20420-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="20420-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
