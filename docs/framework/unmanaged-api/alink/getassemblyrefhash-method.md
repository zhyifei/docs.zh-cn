---
title: GetAssemblyRefHash 方法
ms.date: 03/30/2017
api_name:
- IALink.GetAssemblyRefHash
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetAssemblyRefHash
helpviewer_keywords:
- GetAssemblyRefHash method
ms.assetid: 091a18bd-e901-46f6-b999-74d71c8a7c41
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d19eebaa3aa0ebb6f9807f0cf277b7ed6183c148
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777190"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="8bcf5-102">GetAssemblyRefHash 方法</span><span class="sxs-lookup"><span data-stu-id="8bcf5-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="8bcf5-103">检索给定程序集的哈希 blob。</span><span class="sxs-lookup"><span data-stu-id="8bcf5-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bcf5-104">语法</span><span class="sxs-lookup"><span data-stu-id="8bcf5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bcf5-105">参数</span><span class="sxs-lookup"><span data-stu-id="8bcf5-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="8bcf5-106">哈希将引用的程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="8bcf5-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="8bcf5-107">接收生成的哈希 blob。</span><span class="sxs-lookup"><span data-stu-id="8bcf5-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="8bcf5-108">接收哈希 blob 的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="8bcf5-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8bcf5-109">返回值</span><span class="sxs-lookup"><span data-stu-id="8bcf5-109">Return Value</span></span>  
 <span data-ttu-id="8bcf5-110">如果该方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="8bcf5-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bcf5-111">要求</span><span class="sxs-lookup"><span data-stu-id="8bcf5-111">Requirements</span></span>  
 <span data-ttu-id="8bcf5-112">需要 alink</span><span class="sxs-lookup"><span data-stu-id="8bcf5-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bcf5-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="8bcf5-113">See also</span></span>

- [<span data-ttu-id="8bcf5-114">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="8bcf5-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="8bcf5-115">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="8bcf5-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="8bcf5-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="8bcf5-116">ALink API</span></span>](index.md)
