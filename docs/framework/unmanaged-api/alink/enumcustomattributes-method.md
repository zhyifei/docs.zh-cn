---
title: EnumCustomAttributes 方法
ms.date: 03/30/2017
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b419962982fc80591ed565cceb28afb88a39495e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199136"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="7dc33-102">EnumCustomAttributes 方法</span><span class="sxs-lookup"><span data-stu-id="7dc33-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="7dc33-103">检索程序集级别自定义属性。</span><span class="sxs-lookup"><span data-stu-id="7dc33-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dc33-104">语法</span><span class="sxs-lookup"><span data-stu-id="7dc33-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7dc33-105">参数</span><span class="sxs-lookup"><span data-stu-id="7dc33-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="7dc33-106">枚举器的句柄。</span><span class="sxs-lookup"><span data-stu-id="7dc33-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="7dc33-107">要枚举的属性的类型。</span><span class="sxs-lookup"><span data-stu-id="7dc33-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="7dc33-108">使用`mdTokenNill`的所有属性。</span><span class="sxs-lookup"><span data-stu-id="7dc33-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="7dc33-109">接收自定义特性标记。</span><span class="sxs-lookup"><span data-stu-id="7dc33-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7dc33-110">指定的大小`rCustomValues`数组。</span><span class="sxs-lookup"><span data-stu-id="7dc33-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="7dc33-111">可选择性地接收的令牌值的计数。</span><span class="sxs-lookup"><span data-stu-id="7dc33-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7dc33-112">返回值</span><span class="sxs-lookup"><span data-stu-id="7dc33-112">Return Value</span></span>  
 <span data-ttu-id="7dc33-113">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="7dc33-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7dc33-114">要求</span><span class="sxs-lookup"><span data-stu-id="7dc33-114">Requirements</span></span>  
 <span data-ttu-id="7dc33-115">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="7dc33-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dc33-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="7dc33-116">See also</span></span>

- [<span data-ttu-id="7dc33-117">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="7dc33-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="7dc33-118">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="7dc33-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="7dc33-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="7dc33-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
