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
ms.openlocfilehash: a5b080443be94d5a298cc67591914d87470e6f48
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447183"
---
# <a name="getscope2-method"></a><span data-ttu-id="15c96-102">GetScope2 方法</span><span class="sxs-lookup"><span data-stu-id="15c96-102">GetScope2 Method</span></span>
<span data-ttu-id="15c96-103">获取导入范围。</span><span class="sxs-lookup"><span data-stu-id="15c96-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15c96-104">语法</span><span class="sxs-lookup"><span data-stu-id="15c96-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="15c96-105">参数</span><span class="sxs-lookup"><span data-stu-id="15c96-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="15c96-106">目标程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="15c96-106">ID of target assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="15c96-107">要从中导入的文件的 ID。</span><span class="sxs-lookup"><span data-stu-id="15c96-107">ID of file from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="15c96-108">要导入的从零开始的范围。</span><span class="sxs-lookup"><span data-stu-id="15c96-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="15c96-109">接收指向指定范围的[IMetaDataImport2 接口](../metadata/imetadataimport2-interface.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="15c96-109">Receives pointer to [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface for indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15c96-110">返回值</span><span class="sxs-lookup"><span data-stu-id="15c96-110">Return Value</span></span>  
 <span data-ttu-id="15c96-111">如果方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="15c96-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15c96-112">要求</span><span class="sxs-lookup"><span data-stu-id="15c96-112">Requirements</span></span>  
 <span data-ttu-id="15c96-113">需要 alink。</span><span class="sxs-lookup"><span data-stu-id="15c96-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15c96-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15c96-114">See also</span></span>

- [<span data-ttu-id="15c96-115">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="15c96-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="15c96-116">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="15c96-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="15c96-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="15c96-117">ALink API</span></span>](index.md)
