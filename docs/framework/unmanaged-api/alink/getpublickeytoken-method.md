---
title: GetPublicKeyToken 方法
ms.date: 03/30/2017
api_name:
- IALink2.GetPublicKeyToken
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetPublicKeyToken
helpviewer_keywords:
- GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d1b28eadc9f09abff799f99d1d6012c98b1d3dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215763"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="0b66d-102">GetPublicKeyToken 方法</span><span class="sxs-lookup"><span data-stu-id="0b66d-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="0b66d-103">检索给定的密钥文件或密钥容器的公钥标记。</span><span class="sxs-lookup"><span data-stu-id="0b66d-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b66d-104">语法</span><span class="sxs-lookup"><span data-stu-id="0b66d-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b66d-105">参数</span><span class="sxs-lookup"><span data-stu-id="0b66d-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="0b66d-106">密钥的文件名。</span><span class="sxs-lookup"><span data-stu-id="0b66d-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="0b66d-107">密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="0b66d-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="0b66d-108">标记的存储位置的地址。</span><span class="sxs-lookup"><span data-stu-id="0b66d-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="0b66d-109">指定的大小，以字节为单位的缓冲区所指示的`pvPublicKeyToken`。</span><span class="sxs-lookup"><span data-stu-id="0b66d-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="0b66d-110">在返回时，包含实际使用的字节数。</span><span class="sxs-lookup"><span data-stu-id="0b66d-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b66d-111">返回值</span><span class="sxs-lookup"><span data-stu-id="0b66d-111">Return Value</span></span>  
 <span data-ttu-id="0b66d-112">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="0b66d-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b66d-113">要求</span><span class="sxs-lookup"><span data-stu-id="0b66d-113">Requirements</span></span>  
 <span data-ttu-id="0b66d-114">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="0b66d-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b66d-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b66d-115">See also</span></span>

- [<span data-ttu-id="0b66d-116">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="0b66d-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="0b66d-117">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="0b66d-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="0b66d-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="0b66d-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
