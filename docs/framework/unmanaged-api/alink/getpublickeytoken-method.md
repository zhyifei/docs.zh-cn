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
ms.openlocfilehash: 2e7ed4e1529104db30b0b06665f74342d9ca9a01
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447241"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="11de1-102">GetPublicKeyToken 方法</span><span class="sxs-lookup"><span data-stu-id="11de1-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="11de1-103">检索给定 keyfile 或 key 容器的公钥标记。</span><span class="sxs-lookup"><span data-stu-id="11de1-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11de1-104">语法</span><span class="sxs-lookup"><span data-stu-id="11de1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="11de1-105">参数</span><span class="sxs-lookup"><span data-stu-id="11de1-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="11de1-106">密钥的文件名。</span><span class="sxs-lookup"><span data-stu-id="11de1-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="11de1-107">密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="11de1-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="11de1-108">要存储密钥标记的地址。</span><span class="sxs-lookup"><span data-stu-id="11de1-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="11de1-109">指定 `pvPublicKeyToken`指示的缓冲区的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="11de1-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="11de1-110">返回时，包含所使用的实际字节数。</span><span class="sxs-lookup"><span data-stu-id="11de1-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11de1-111">返回值</span><span class="sxs-lookup"><span data-stu-id="11de1-111">Return Value</span></span>  
 <span data-ttu-id="11de1-112">如果方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="11de1-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11de1-113">要求</span><span class="sxs-lookup"><span data-stu-id="11de1-113">Requirements</span></span>  
 <span data-ttu-id="11de1-114">需要 alink。</span><span class="sxs-lookup"><span data-stu-id="11de1-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11de1-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11de1-115">See also</span></span>

- [<span data-ttu-id="11de1-116">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="11de1-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="11de1-117">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="11de1-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="11de1-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="11de1-118">ALink API</span></span>](index.md)
