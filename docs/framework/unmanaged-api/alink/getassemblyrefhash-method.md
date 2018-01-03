---
title: "GetAssemblyRefHash 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetAssemblyRefHash
api_location: alink.dll
api_type: COM
f1_keywords: GetAssemblyRefHash
helpviewer_keywords: GetAssemblyRefHash method
ms.assetid: 091a18bd-e901-46f6-b999-74d71c8a7c41
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 99ae38025f223d669a428738783676ebc0687554
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="4e013-102">GetAssemblyRefHash 方法</span><span class="sxs-lookup"><span data-stu-id="4e013-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="4e013-103">检索给定的程序集哈希 blob。</span><span class="sxs-lookup"><span data-stu-id="4e013-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e013-104">语法</span><span class="sxs-lookup"><span data-stu-id="4e013-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e013-105">参数</span><span class="sxs-lookup"><span data-stu-id="4e013-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="4e013-106">哈希将引用的程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="4e013-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="4e013-107">接收生成的哈希 blob。</span><span class="sxs-lookup"><span data-stu-id="4e013-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="4e013-108">接收大小，以字节为单位的哈希 blob。</span><span class="sxs-lookup"><span data-stu-id="4e013-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e013-109">返回值</span><span class="sxs-lookup"><span data-stu-id="4e013-109">Return Value</span></span>  
 <span data-ttu-id="4e013-110">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="4e013-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e013-111">惠?</span><span class="sxs-lookup"><span data-stu-id="4e013-111">Requirements</span></span>  
 <span data-ttu-id="4e013-112">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="4e013-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e013-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e013-113">See Also</span></span>  
 [<span data-ttu-id="4e013-114">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="4e013-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="4e013-115">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="4e013-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="4e013-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="4e013-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
