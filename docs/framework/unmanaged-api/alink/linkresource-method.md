---
title: LinkResource 方法
ms.date: 03/30/2017
api_name:
- IALink.LinkResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- LinkResource
helpviewer_keywords:
- LinkResource method
ms.assetid: c404acb3-4c59-4100-9a4c-483cbdb1d736
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 763b7a776007c2ce8dac42c6a5f7f00f6eb58a10
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776955"
---
# <a name="linkresource-method"></a><span data-ttu-id="351e3-102">LinkResource 方法</span><span class="sxs-lookup"><span data-stu-id="351e3-102">LinkResource Method</span></span>
<span data-ttu-id="351e3-103">资源中的链接。</span><span class="sxs-lookup"><span data-stu-id="351e3-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="351e3-104">语法</span><span class="sxs-lookup"><span data-stu-id="351e3-104">Syntax</span></span>  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="351e3-105">参数</span><span class="sxs-lookup"><span data-stu-id="351e3-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="351e3-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="351e3-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="351e3-107">文件的名称。</span><span class="sxs-lookup"><span data-stu-id="351e3-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="351e3-108">可选的新文件名。</span><span class="sxs-lookup"><span data-stu-id="351e3-108">Optional new file name.</span></span> <span data-ttu-id="351e3-109">如果非 NULL， `pszFileName`则将复制到 pszNewLocation。</span><span class="sxs-lookup"><span data-stu-id="351e3-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="351e3-110">资源的名称。</span><span class="sxs-lookup"><span data-stu-id="351e3-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="351e3-111">辅助功能标志`mrPublic` ，例如`mrPrivate`和。</span><span class="sxs-lookup"><span data-stu-id="351e3-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="351e3-112">此参数可传递给[DefineManifestResource 方法](../metadata/imetadataassemblyemit-definemanifestresource-method.md)。</span><span class="sxs-lookup"><span data-stu-id="351e3-112">This parameter may be passed to [DefineManifestResource Method](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="351e3-113">返回值</span><span class="sxs-lookup"><span data-stu-id="351e3-113">Return Value</span></span>  
 <span data-ttu-id="351e3-114">如果该方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="351e3-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="351e3-115">要求</span><span class="sxs-lookup"><span data-stu-id="351e3-115">Requirements</span></span>  
 <span data-ttu-id="351e3-116">需要 alink。</span><span class="sxs-lookup"><span data-stu-id="351e3-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="351e3-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="351e3-117">See also</span></span>

- [<span data-ttu-id="351e3-118">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="351e3-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="351e3-119">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="351e3-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="351e3-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="351e3-120">ALink API</span></span>](index.md)
