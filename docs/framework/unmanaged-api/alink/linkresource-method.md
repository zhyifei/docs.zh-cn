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
ms.openlocfilehash: 6e851c1bd56c0e9ece02fb06c0dcd9975a5b02ff
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079430"
---
# <a name="linkresource-method"></a><span data-ttu-id="30f8c-102">LinkResource 方法</span><span class="sxs-lookup"><span data-stu-id="30f8c-102">LinkResource Method</span></span>
<span data-ttu-id="30f8c-103">在资源中的链接。</span><span class="sxs-lookup"><span data-stu-id="30f8c-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30f8c-104">语法</span><span class="sxs-lookup"><span data-stu-id="30f8c-104">Syntax</span></span>  
  
```  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="30f8c-105">参数</span><span class="sxs-lookup"><span data-stu-id="30f8c-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="30f8c-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="30f8c-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="30f8c-107">文件的名称。</span><span class="sxs-lookup"><span data-stu-id="30f8c-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="30f8c-108">可选的新文件名称。</span><span class="sxs-lookup"><span data-stu-id="30f8c-108">Optional new file name.</span></span> <span data-ttu-id="30f8c-109">如果非 NULL`pszFileName`将复制到 pszNewLocation。</span><span class="sxs-lookup"><span data-stu-id="30f8c-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="30f8c-110">资源的名称。</span><span class="sxs-lookup"><span data-stu-id="30f8c-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="30f8c-111">可访问性标志，如`mrPublic`和`mrPrivate`。</span><span class="sxs-lookup"><span data-stu-id="30f8c-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="30f8c-112">此参数可能会传递到[DefineManifestResource 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)。</span><span class="sxs-lookup"><span data-stu-id="30f8c-112">This parameter may be passed to [DefineManifestResource Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30f8c-113">返回值</span><span class="sxs-lookup"><span data-stu-id="30f8c-113">Return Value</span></span>  
 <span data-ttu-id="30f8c-114">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="30f8c-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30f8c-115">要求</span><span class="sxs-lookup"><span data-stu-id="30f8c-115">Requirements</span></span>  
 <span data-ttu-id="30f8c-116">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="30f8c-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30f8c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="30f8c-117">See also</span></span>

- [<span data-ttu-id="30f8c-118">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="30f8c-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="30f8c-119">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="30f8c-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="30f8c-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="30f8c-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
