---
title: "EnumCustomAttributes 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location: alink.dll
api_type: COM
f1_keywords: EnumCustomAttributes
helpviewer_keywords: EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d616babb47ac0282ef56d119ab448a94fd24c7c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="ff744-102">EnumCustomAttributes 方法</span><span class="sxs-lookup"><span data-stu-id="ff744-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="ff744-103">检索程序集级别的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="ff744-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff744-104">语法</span><span class="sxs-lookup"><span data-stu-id="ff744-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff744-105">参数</span><span class="sxs-lookup"><span data-stu-id="ff744-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="ff744-106">句柄的枚举器。</span><span class="sxs-lookup"><span data-stu-id="ff744-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="ff744-107">要枚举的特性的类型。</span><span class="sxs-lookup"><span data-stu-id="ff744-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="ff744-108">使用`mdTokenNill`所有特性。</span><span class="sxs-lookup"><span data-stu-id="ff744-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="ff744-109">接收自定义特性标记。</span><span class="sxs-lookup"><span data-stu-id="ff744-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ff744-110">指定的大小`rCustomValues`数组。</span><span class="sxs-lookup"><span data-stu-id="ff744-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="ff744-111">（可选） 接收的令牌值的计数。</span><span class="sxs-lookup"><span data-stu-id="ff744-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff744-112">返回值</span><span class="sxs-lookup"><span data-stu-id="ff744-112">Return Value</span></span>  
 <span data-ttu-id="ff744-113">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="ff744-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff744-114">惠?</span><span class="sxs-lookup"><span data-stu-id="ff744-114">Requirements</span></span>  
 <span data-ttu-id="ff744-115">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="ff744-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff744-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff744-116">See Also</span></span>  
 [<span data-ttu-id="ff744-117">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="ff744-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="ff744-118">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="ff744-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="ff744-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="ff744-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
