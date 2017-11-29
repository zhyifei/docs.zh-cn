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
ms.openlocfilehash: febaba5155753e9d60a3708582f4f58bd7861ec7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="15ae5-102">EnumCustomAttributes 方法</span><span class="sxs-lookup"><span data-stu-id="15ae5-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="15ae5-103">检索程序集级别的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="15ae5-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15ae5-104">语法</span><span class="sxs-lookup"><span data-stu-id="15ae5-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15ae5-105">参数</span><span class="sxs-lookup"><span data-stu-id="15ae5-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="15ae5-106">句柄的枚举器。</span><span class="sxs-lookup"><span data-stu-id="15ae5-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="15ae5-107">要枚举的特性的类型。</span><span class="sxs-lookup"><span data-stu-id="15ae5-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="15ae5-108">使用`mdTokenNill`所有特性。</span><span class="sxs-lookup"><span data-stu-id="15ae5-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="15ae5-109">接收自定义特性标记。</span><span class="sxs-lookup"><span data-stu-id="15ae5-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="15ae5-110">指定的大小`rCustomValues`数组。</span><span class="sxs-lookup"><span data-stu-id="15ae5-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="15ae5-111">（可选） 接收的令牌值的计数。</span><span class="sxs-lookup"><span data-stu-id="15ae5-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15ae5-112">返回值</span><span class="sxs-lookup"><span data-stu-id="15ae5-112">Return Value</span></span>  
 <span data-ttu-id="15ae5-113">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="15ae5-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15ae5-114">要求</span><span class="sxs-lookup"><span data-stu-id="15ae5-114">Requirements</span></span>  
 <span data-ttu-id="15ae5-115">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="15ae5-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15ae5-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15ae5-116">See Also</span></span>  
 [<span data-ttu-id="15ae5-117">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="15ae5-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="15ae5-118">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="15ae5-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="15ae5-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="15ae5-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
