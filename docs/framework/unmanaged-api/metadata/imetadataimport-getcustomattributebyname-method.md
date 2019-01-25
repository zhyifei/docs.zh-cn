---
title: IMetaDataImport::GetCustomAttributeByName 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 68cac76a83164e24c0810c9d19fa845c8580b1d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637225"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="aecd0-102">IMetaDataImport::GetCustomAttributeByName 方法</span><span class="sxs-lookup"><span data-stu-id="aecd0-102">IMetaDataImport::GetCustomAttributeByName Method</span></span>
<span data-ttu-id="aecd0-103">获取自定义特性，在给定其名称和所有者。</span><span class="sxs-lookup"><span data-stu-id="aecd0-103">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aecd0-104">语法</span><span class="sxs-lookup"><span data-stu-id="aecd0-104">Syntax</span></span>  
  
```  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aecd0-105">参数</span><span class="sxs-lookup"><span data-stu-id="aecd0-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="aecd0-106">[in]表示拥有该自定义属性的对象的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="aecd0-106">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="aecd0-107">[in]自定义特性的名称。</span><span class="sxs-lookup"><span data-stu-id="aecd0-107">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="aecd0-108">[out]指向的是自定义特性的值的数据数组的指针。</span><span class="sxs-lookup"><span data-stu-id="aecd0-108">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="aecd0-109">[out]以字节为单位的中返回的数据大小 \*`ppData`。</span><span class="sxs-lookup"><span data-stu-id="aecd0-109">[out] The size in bytes of the data returned in \*`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aecd0-110">备注</span><span class="sxs-lookup"><span data-stu-id="aecd0-110">Remarks</span></span>  
 <span data-ttu-id="aecd0-111">它是合法的相同的所有者; 定义多个自定义属性它们甚至可能具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="aecd0-111">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="aecd0-112">但是，`GetCustomAttributeByName`只返回一个实例。</span><span class="sxs-lookup"><span data-stu-id="aecd0-112">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="aecd0-113">(`GetCustomAttributeByName`返回它所遇到的第一个实例。)若要查找的自定义属性的所有实例，请调用[imetadataimport:: Enumcustomattributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="aecd0-113">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aecd0-114">要求</span><span class="sxs-lookup"><span data-stu-id="aecd0-114">Requirements</span></span>  
 <span data-ttu-id="aecd0-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aecd0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aecd0-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="aecd0-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aecd0-117">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="aecd0-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aecd0-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aecd0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aecd0-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="aecd0-119">See also</span></span>
- [<span data-ttu-id="aecd0-120">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="aecd0-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="aecd0-121">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="aecd0-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
