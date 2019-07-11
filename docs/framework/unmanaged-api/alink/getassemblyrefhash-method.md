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
ms.openlocfilehash: 49ea7fbe9f491028a85fae543d126fd9d4f2d940
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741903"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="364b2-102">GetAssemblyRefHash 方法</span><span class="sxs-lookup"><span data-stu-id="364b2-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="364b2-103">检索给定程序集哈希 blob。</span><span class="sxs-lookup"><span data-stu-id="364b2-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="364b2-104">语法</span><span class="sxs-lookup"><span data-stu-id="364b2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="364b2-105">参数</span><span class="sxs-lookup"><span data-stu-id="364b2-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="364b2-106">哈希将引用的程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="364b2-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="364b2-107">接收生成的哈希 blob。</span><span class="sxs-lookup"><span data-stu-id="364b2-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="364b2-108">接收大小，以字节为单位的哈希 blob。</span><span class="sxs-lookup"><span data-stu-id="364b2-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="364b2-109">返回值</span><span class="sxs-lookup"><span data-stu-id="364b2-109">Return Value</span></span>  
 <span data-ttu-id="364b2-110">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="364b2-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="364b2-111">要求</span><span class="sxs-lookup"><span data-stu-id="364b2-111">Requirements</span></span>  
 <span data-ttu-id="364b2-112">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="364b2-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="364b2-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="364b2-113">See also</span></span>

- [<span data-ttu-id="364b2-114">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="364b2-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="364b2-115">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="364b2-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="364b2-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="364b2-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
