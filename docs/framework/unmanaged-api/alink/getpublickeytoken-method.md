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
ms.openlocfilehash: ec2c357cd56670f4f2deed8023bed7842a7f4ed7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741884"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="5cb99-102">GetPublicKeyToken 方法</span><span class="sxs-lookup"><span data-stu-id="5cb99-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="5cb99-103">检索给定的密钥文件或密钥容器的公钥标记。</span><span class="sxs-lookup"><span data-stu-id="5cb99-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cb99-104">语法</span><span class="sxs-lookup"><span data-stu-id="5cb99-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cb99-105">参数</span><span class="sxs-lookup"><span data-stu-id="5cb99-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="5cb99-106">密钥的文件名。</span><span class="sxs-lookup"><span data-stu-id="5cb99-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="5cb99-107">密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="5cb99-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="5cb99-108">标记的存储位置的地址。</span><span class="sxs-lookup"><span data-stu-id="5cb99-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="5cb99-109">指定的大小，以字节为单位的缓冲区所指示的`pvPublicKeyToken`。</span><span class="sxs-lookup"><span data-stu-id="5cb99-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="5cb99-110">在返回时，包含实际使用的字节数。</span><span class="sxs-lookup"><span data-stu-id="5cb99-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5cb99-111">返回值</span><span class="sxs-lookup"><span data-stu-id="5cb99-111">Return Value</span></span>  
 <span data-ttu-id="5cb99-112">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="5cb99-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cb99-113">要求</span><span class="sxs-lookup"><span data-stu-id="5cb99-113">Requirements</span></span>  
 <span data-ttu-id="5cb99-114">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="5cb99-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cb99-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="5cb99-115">See also</span></span>

- [<span data-ttu-id="5cb99-116">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="5cb99-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="5cb99-117">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="5cb99-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="5cb99-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="5cb99-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
