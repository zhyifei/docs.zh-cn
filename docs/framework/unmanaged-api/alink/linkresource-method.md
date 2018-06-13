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
ms.openlocfilehash: 4f75ebc3a40bddbaf2347b9ef559139888f83900
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401103"
---
# <a name="linkresource-method"></a><span data-ttu-id="97677-102">LinkResource 方法</span><span class="sxs-lookup"><span data-stu-id="97677-102">LinkResource Method</span></span>
<span data-ttu-id="97677-103">在资源中的链接。</span><span class="sxs-lookup"><span data-stu-id="97677-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97677-104">语法</span><span class="sxs-lookup"><span data-stu-id="97677-104">Syntax</span></span>  
  
```  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97677-105">参数</span><span class="sxs-lookup"><span data-stu-id="97677-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="97677-106">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="97677-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="97677-107">文件的名称。</span><span class="sxs-lookup"><span data-stu-id="97677-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="97677-108">可选的新文件名称。</span><span class="sxs-lookup"><span data-stu-id="97677-108">Optional new file name.</span></span> <span data-ttu-id="97677-109">如果非 NULL`pszFileName`将复制到 pszNewLocation。</span><span class="sxs-lookup"><span data-stu-id="97677-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="97677-110">资源的名称。</span><span class="sxs-lookup"><span data-stu-id="97677-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="97677-111">可访问性标志，如`mrPublic`和`mrPrivate`。</span><span class="sxs-lookup"><span data-stu-id="97677-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="97677-112">此参数可能传递给[DefineManifestResource 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)。</span><span class="sxs-lookup"><span data-stu-id="97677-112">This parameter may be passed to [DefineManifestResource Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97677-113">返回值</span><span class="sxs-lookup"><span data-stu-id="97677-113">Return Value</span></span>  
 <span data-ttu-id="97677-114">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="97677-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97677-115">要求</span><span class="sxs-lookup"><span data-stu-id="97677-115">Requirements</span></span>  
 <span data-ttu-id="97677-116">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="97677-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97677-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="97677-117">See Also</span></span>  
 [<span data-ttu-id="97677-118">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="97677-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="97677-119">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="97677-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="97677-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="97677-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
