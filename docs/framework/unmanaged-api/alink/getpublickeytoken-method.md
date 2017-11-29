---
title: "GetPublicKeyToken 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.GetPublicKeyToken
api_location: alink.dll
api_type: COM
f1_keywords: GetPublicKeyToken
helpviewer_keywords: GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5f41c8088f095802cf35239afab279d6324adb55
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="278a4-102">GetPublicKeyToken 方法</span><span class="sxs-lookup"><span data-stu-id="278a4-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="278a4-103">检索给定的密钥文件或密钥容器的公钥令牌。</span><span class="sxs-lookup"><span data-stu-id="278a4-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="278a4-104">语法</span><span class="sxs-lookup"><span data-stu-id="278a4-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="278a4-105">参数</span><span class="sxs-lookup"><span data-stu-id="278a4-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="278a4-106">密钥的文件名。</span><span class="sxs-lookup"><span data-stu-id="278a4-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="278a4-107">密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="278a4-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="278a4-108">密钥令牌其中是要存储的地址。</span><span class="sxs-lookup"><span data-stu-id="278a4-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="278a4-109">指定的大小，以字节为单位的所指示的缓冲区`pvPublicKeyToken`。</span><span class="sxs-lookup"><span data-stu-id="278a4-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="278a4-110">返回时，包含实际使用的字节数。</span><span class="sxs-lookup"><span data-stu-id="278a4-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="278a4-111">返回值</span><span class="sxs-lookup"><span data-stu-id="278a4-111">Return Value</span></span>  
 <span data-ttu-id="278a4-112">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="278a4-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="278a4-113">要求</span><span class="sxs-lookup"><span data-stu-id="278a4-113">Requirements</span></span>  
 <span data-ttu-id="278a4-114">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="278a4-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="278a4-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="278a4-115">See Also</span></span>  
 [<span data-ttu-id="278a4-116">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="278a4-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="278a4-117">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="278a4-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="278a4-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="278a4-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
