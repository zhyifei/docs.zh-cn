---
title: IMetaDataImport::GetNameFromToken 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNameFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type:
- apiref
ms.openlocfilehash: 6ed30f07fcec9c730e1514350c594399f0aa16e5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437273"
---
# <a name="imetadataimportgetnamefromtoken-method"></a><span data-ttu-id="8e766-102">IMetaDataImport::GetNameFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="8e766-102">IMetaDataImport::GetNameFromToken Method</span></span>
<span data-ttu-id="8e766-103">获取指定的元数据标记所引用的对象的 UTF-8 名称。</span><span class="sxs-lookup"><span data-stu-id="8e766-103">Gets the UTF-8 name of the object referenced by the specified metadata token.</span></span> <span data-ttu-id="8e766-104">此方法已过时。</span><span class="sxs-lookup"><span data-stu-id="8e766-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e766-105">语法</span><span class="sxs-lookup"><span data-stu-id="8e766-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e766-106">参数</span><span class="sxs-lookup"><span data-stu-id="8e766-106">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="8e766-107">中表示要为其返回名称的对象的标记。</span><span class="sxs-lookup"><span data-stu-id="8e766-107">[in] The token representing the object to return the name for.</span></span>  
  
 `pszUtf8NamePtr`  
 <span data-ttu-id="8e766-108">弄指向堆中 UTF-8 对象名称的指针。</span><span class="sxs-lookup"><span data-stu-id="8e766-108">[out] A pointer to the UTF-8 object name in the heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e766-109">备注</span><span class="sxs-lookup"><span data-stu-id="8e766-109">Remarks</span></span>  
 <span data-ttu-id="8e766-110">`GetNameFromToken` 已过时。</span><span class="sxs-lookup"><span data-stu-id="8e766-110">`GetNameFromToken` is obsolete.</span></span> <span data-ttu-id="8e766-111">作为替代方法，可以调用方法来获取所需的特定类型的标记的属性，例如 `GetFieldProps` 用于某个方法的字段或 `GetMethodProps`。</span><span class="sxs-lookup"><span data-stu-id="8e766-111">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e766-112">要求</span><span class="sxs-lookup"><span data-stu-id="8e766-112">Requirements</span></span>  
 <span data-ttu-id="8e766-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8e766-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e766-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="8e766-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8e766-115">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="8e766-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8e766-116">**.NET Framework 版本：** 1.0</span><span class="sxs-lookup"><span data-stu-id="8e766-116">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e766-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e766-117">See also</span></span>

- [<span data-ttu-id="8e766-118">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="8e766-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8e766-119">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="8e766-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
