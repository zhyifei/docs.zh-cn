---
title: "IMapToken::Map 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMapToken.Map
api_location: mscoree.dll
api_type: COM
f1_keywords: IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fe034d2bc6d70e820fa3ad5de8140afa9a19a6bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="92961-102">IMapToken::Map 方法</span><span class="sxs-lookup"><span data-stu-id="92961-102">IMapToken::Map Method</span></span>
<span data-ttu-id="92961-103">映射使用元数据签名的程序集之间的关系。</span><span class="sxs-lookup"><span data-stu-id="92961-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92961-104">语法</span><span class="sxs-lookup"><span data-stu-id="92961-104">Syntax</span></span>  
  
```  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92961-105">参数</span><span class="sxs-lookup"><span data-stu-id="92961-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="92961-106">[in]表示导入的代码对象的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="92961-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="92961-107">[in]表示发出的代码对象的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="92961-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92961-108">备注</span><span class="sxs-lookup"><span data-stu-id="92961-108">Remarks</span></span>  
 <span data-ttu-id="92961-109">当令牌重新映射发生在合并过程时，原始令牌的作用范围导入 （源） 元数据范围内，而且新令牌范围发出 （目标） 元数据范围内。</span><span class="sxs-lookup"><span data-stu-id="92961-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92961-110">惠?</span><span class="sxs-lookup"><span data-stu-id="92961-110">Requirements</span></span>  
 <span data-ttu-id="92961-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="92961-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92961-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="92961-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="92961-113">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="92961-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="92961-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92961-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92961-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="92961-115">See Also</span></span>  
 [<span data-ttu-id="92961-116">IMapToken 接口</span><span class="sxs-lookup"><span data-stu-id="92961-116">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
