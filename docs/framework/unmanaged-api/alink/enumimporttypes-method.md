---
title: EnumImportTypes 方法
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4e437868138d7ae31d233853ecc0f709de3ee39d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512717"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="c36b7-102">EnumImportTypes 方法</span><span class="sxs-lookup"><span data-stu-id="c36b7-102">EnumImportTypes Method</span></span>
<span data-ttu-id="c36b7-103">枚举每个作用域中的每个类型。</span><span class="sxs-lookup"><span data-stu-id="c36b7-103">Enumerates each type in each scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c36b7-104">语法</span><span class="sxs-lookup"><span data-stu-id="c36b7-104">Syntax</span></span>  
  
```  
HRESULT EnumImportTypes(  
    HALINKENUM   hEnum,  
    DWORD        dwMax,  
    mdTypeDef    aTypeDefs[],  
    DWORD*       pdwCount  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c36b7-105">参数</span><span class="sxs-lookup"><span data-stu-id="c36b7-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="c36b7-106">枚举器的句柄。</span><span class="sxs-lookup"><span data-stu-id="c36b7-106">Handle for enumerator.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="c36b7-107">要检索的类型的最大数目。</span><span class="sxs-lookup"><span data-stu-id="c36b7-107">Maximum number of types to retrieve.</span></span>  
  
 `aTypeDefs`  
 <span data-ttu-id="c36b7-108">接收类型标记，不能超过`dwMax`。</span><span class="sxs-lookup"><span data-stu-id="c36b7-108">Recieves type tokens, not to exceed `dwMax`.</span></span>  
  
 `pdwCount`  
 <span data-ttu-id="c36b7-109">接收中的类型的实际数目`aTypeDefs`。</span><span class="sxs-lookup"><span data-stu-id="c36b7-109">Receives actual number of type in `aTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c36b7-110">返回值</span><span class="sxs-lookup"><span data-stu-id="c36b7-110">Return Value</span></span>  
 <span data-ttu-id="c36b7-111">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="c36b7-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c36b7-112">要求</span><span class="sxs-lookup"><span data-stu-id="c36b7-112">Requirements</span></span>  
 <span data-ttu-id="c36b7-113">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="c36b7-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c36b7-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c36b7-114">See also</span></span>
- [<span data-ttu-id="c36b7-115">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="c36b7-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="c36b7-116">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="c36b7-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="c36b7-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="c36b7-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
