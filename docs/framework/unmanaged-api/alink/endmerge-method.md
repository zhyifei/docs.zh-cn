---
title: EndMerge 方法
ms.date: 03/30/2017
api_name:
- IALink.EndMerge
- EndMerge
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EndMerge
helpviewer_keywords:
- EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 020cc56126249b27a52387e6efa3aa10c83d9126
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226841"
---
# <a name="endmerge-method"></a><span data-ttu-id="c1075-102">EndMerge 方法</span><span class="sxs-lookup"><span data-stu-id="c1075-102">EndMerge Method</span></span>
<span data-ttu-id="c1075-103">指示到发出范围合并所有自定义属性。</span><span class="sxs-lookup"><span data-stu-id="c1075-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1075-104">语法</span><span class="sxs-lookup"><span data-stu-id="c1075-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1075-105">参数</span><span class="sxs-lookup"><span data-stu-id="c1075-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c1075-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="c1075-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1075-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c1075-107">Return Value</span></span>  
 <span data-ttu-id="c1075-108">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="c1075-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1075-109">要求</span><span class="sxs-lookup"><span data-stu-id="c1075-109">Requirements</span></span>  
 <span data-ttu-id="c1075-110">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="c1075-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1075-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1075-111">See also</span></span>

- [<span data-ttu-id="c1075-112">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="c1075-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="c1075-113">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="c1075-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="c1075-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="c1075-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
