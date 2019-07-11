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
ms.openlocfilehash: 09ccf731f0494b6eda49f6a15d04970a723c473b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742060"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="0f240-102">EnumCustomAttributes 方法</span><span class="sxs-lookup"><span data-stu-id="0f240-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="0f240-103">检索程序集级别自定义属性。</span><span class="sxs-lookup"><span data-stu-id="0f240-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f240-104">语法</span><span class="sxs-lookup"><span data-stu-id="0f240-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f240-105">参数</span><span class="sxs-lookup"><span data-stu-id="0f240-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="0f240-106">枚举器的句柄。</span><span class="sxs-lookup"><span data-stu-id="0f240-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="0f240-107">要枚举的属性的类型。</span><span class="sxs-lookup"><span data-stu-id="0f240-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="0f240-108">使用`mdTokenNill`的所有属性。</span><span class="sxs-lookup"><span data-stu-id="0f240-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="0f240-109">接收自定义特性标记。</span><span class="sxs-lookup"><span data-stu-id="0f240-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0f240-110">指定的大小`rCustomValues`数组。</span><span class="sxs-lookup"><span data-stu-id="0f240-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="0f240-111">可选择性地接收的令牌值的计数。</span><span class="sxs-lookup"><span data-stu-id="0f240-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f240-112">返回值</span><span class="sxs-lookup"><span data-stu-id="0f240-112">Return Value</span></span>  
 <span data-ttu-id="0f240-113">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="0f240-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f240-114">要求</span><span class="sxs-lookup"><span data-stu-id="0f240-114">Requirements</span></span>  
 <span data-ttu-id="0f240-115">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="0f240-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f240-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f240-116">See also</span></span>

- [<span data-ttu-id="0f240-117">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="0f240-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="0f240-118">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="0f240-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="0f240-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="0f240-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
