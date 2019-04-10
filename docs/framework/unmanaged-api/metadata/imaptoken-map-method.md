---
title: IMapToken::Map 方法
ms.date: 03/30/2017
api_name:
- IMapToken.Map
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a85dc586b0c08fabdd34c018e82314c9003eeded
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171002"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="fb67c-102">IMapToken::Map 方法</span><span class="sxs-lookup"><span data-stu-id="fb67c-102">IMapToken::Map Method</span></span>
<span data-ttu-id="fb67c-103">映射使用元数据签名的程序集之间的关系。</span><span class="sxs-lookup"><span data-stu-id="fb67c-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb67c-104">语法</span><span class="sxs-lookup"><span data-stu-id="fb67c-104">Syntax</span></span>  
  
```  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb67c-105">参数</span><span class="sxs-lookup"><span data-stu-id="fb67c-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="fb67c-106">[in]表示导入的代码对象的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="fb67c-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="fb67c-107">[in]表示发出的代码对象的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="fb67c-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb67c-108">备注</span><span class="sxs-lookup"><span data-stu-id="fb67c-108">Remarks</span></span>  
 <span data-ttu-id="fb67c-109">标记重新映射发生在合并期间时, 原始令牌的作用域导入 （源） 元数据范围内，新的令牌的范围限定在发出 （目标） 的元数据范围内。</span><span class="sxs-lookup"><span data-stu-id="fb67c-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb67c-110">要求</span><span class="sxs-lookup"><span data-stu-id="fb67c-110">Requirements</span></span>  
 <span data-ttu-id="fb67c-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fb67c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb67c-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fb67c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fb67c-113">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fb67c-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="fb67c-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="fb67c-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fb67c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb67c-115">See also</span></span>

- [<span data-ttu-id="fb67c-116">IMapToken 接口</span><span class="sxs-lookup"><span data-stu-id="fb67c-116">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
