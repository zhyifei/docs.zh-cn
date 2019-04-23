---
title: GetScope2 方法
ms.date: 03/30/2017
api_name:
- IALink2.GetScope2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope2
helpviewer_keywords:
- GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a3c6b9e1239dc1baed9428d4fe967eb8274a9304
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206026"
---
# <a name="getscope2-method"></a><span data-ttu-id="bb8d0-102">GetScope2 方法</span><span class="sxs-lookup"><span data-stu-id="bb8d0-102">GetScope2 Method</span></span>
<span data-ttu-id="bb8d0-103">获取导入范围。</span><span class="sxs-lookup"><span data-stu-id="bb8d0-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb8d0-104">语法</span><span class="sxs-lookup"><span data-stu-id="bb8d0-104">Syntax</span></span>  
  
```  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="bb8d0-105">参数</span><span class="sxs-lookup"><span data-stu-id="bb8d0-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="bb8d0-106">目标程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="bb8d0-106">ID of target assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="bb8d0-107">要从中导入的文件的 ID。</span><span class="sxs-lookup"><span data-stu-id="bb8d0-107">ID of file from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="bb8d0-108">要导入的从零开始范围。</span><span class="sxs-lookup"><span data-stu-id="bb8d0-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="bb8d0-109">接收指向[IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)指示的范围的接口。</span><span class="sxs-lookup"><span data-stu-id="bb8d0-109">Receives pointer to [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface for indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb8d0-110">返回值</span><span class="sxs-lookup"><span data-stu-id="bb8d0-110">Return Value</span></span>  
 <span data-ttu-id="bb8d0-111">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="bb8d0-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb8d0-112">要求</span><span class="sxs-lookup"><span data-stu-id="bb8d0-112">Requirements</span></span>  
 <span data-ttu-id="bb8d0-113">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="bb8d0-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb8d0-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb8d0-114">See also</span></span>

- [<span data-ttu-id="bb8d0-115">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="bb8d0-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="bb8d0-116">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="bb8d0-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="bb8d0-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="bb8d0-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
