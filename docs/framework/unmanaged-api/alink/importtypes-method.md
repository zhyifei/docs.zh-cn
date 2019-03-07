---
title: ImportTypes 方法
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 92dfc2bec33501a5cd9ca6b4ec4c3629b6d89946
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487949"
---
# <a name="importtypes-method"></a><span data-ttu-id="30038-102">ImportTypes 方法</span><span class="sxs-lookup"><span data-stu-id="30038-102">ImportTypes Method</span></span>
<span data-ttu-id="30038-103">启动导入的类型从通过导入每个作用域[ImportFile 方法](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)。</span><span class="sxs-lookup"><span data-stu-id="30038-103">Initiates the importing of types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30038-104">语法</span><span class="sxs-lookup"><span data-stu-id="30038-104">Syntax</span></span>  
  
```  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="30038-105">参数</span><span class="sxs-lookup"><span data-stu-id="30038-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="30038-106">要导入到的程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="30038-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="30038-107">若要从导入的文件的 ID。</span><span class="sxs-lookup"><span data-stu-id="30038-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="30038-108">要导入的从零开始范围。</span><span class="sxs-lookup"><span data-stu-id="30038-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="30038-109">在此作用域中接收的类型的枚举器句柄。</span><span class="sxs-lookup"><span data-stu-id="30038-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="30038-110">可选择性地接收[IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="30038-110">Optionally receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="30038-111">可选择性地指示作用域中接收的类型的计数。</span><span class="sxs-lookup"><span data-stu-id="30038-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30038-112">返回值</span><span class="sxs-lookup"><span data-stu-id="30038-112">Return Value</span></span>  
 <span data-ttu-id="30038-113">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="30038-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30038-114">要求</span><span class="sxs-lookup"><span data-stu-id="30038-114">Requirements</span></span>  
 <span data-ttu-id="30038-115">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="30038-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30038-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="30038-116">See also</span></span>
- [<span data-ttu-id="30038-117">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="30038-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="30038-118">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="30038-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="30038-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="30038-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
