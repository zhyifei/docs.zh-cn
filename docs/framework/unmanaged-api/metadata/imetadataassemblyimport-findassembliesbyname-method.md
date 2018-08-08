---
title: IMetaDataAssemblyImport::FindAssembliesByName 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindAssembliesByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindAssembliesByName
helpviewer_keywords:
- FindAssembliesByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindAssembliesByName method [.NET Framework metadata]
ms.assetid: 4db97cf9-e4c1-4233-8efa-cbdc0e14a8e4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a6c7bf332d829a440fe216756f7a23ec1277e6c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449281"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>IMetaDataAssemblyImport::FindAssembliesByName 方法
获取与指定的程序集的数组`szAssemblyName`参数，并使用由公共语言运行时 (CLR) 来解析引用的标准规则。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,   
    [in]  LPCWSTR     szPrivateBin,   
    [in]  LPCWSTR     szAssemblyName,   
    [out] IUnknown    *ppIUnk[],   
    [in]  ULONG       cMax,   
    [out] ULONG       *pcAssemblies  
);  
```  
  
#### <a name="parameters"></a>参数  
 `szAppBase`  
 [in]要在其中搜索给定的程序集的根目录。 如果此值设置为`null`，`FindAssembliesByName`将仅在全局程序集缓存中查找程序集。  
  
 `szPrivateBin`  
 [in]以分号分隔 （例如，"bin; bin2"），目录下的子目录根，在其中搜索程序集的列表。 除了默认探测规则中指定探测这些目录。  
  
 `szAssemblyName`  
 [in]要查找的程序集的名称。 此字符串的格式定义中的类引用页<xref:System.Reflection.AssemblyName>。  
  
 `ppIUnk`  
 [in]类型的数组 <<!--zzxref:IUnknown --> `IUnknown`> 在其中放入`IMetadataAssemblyImport`接口指针。  
  
 `cMax`  
 [out]最大数量的接口指针，可以放置在`ppIUnk`。  
  
 `pcAssemblies`  
 [out]返回接口指针的数目。 数量的接口指针，即实际放入`ppIUnk`。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName` 已成功返回。|  
|`S_FALSE`|没有程序集。|  
  
## <a name="remarks"></a>备注  
 给定程序集名称，`FindAssembliesByName`方法找到按照标准规则以解析程序集引用的程序集。 (有关详细信息，请参阅[运行时如何定位程序集](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)。)`FindAssembliesByName`允许调用方的程序集冲突解决程序上下文中，如应用程序基和专用搜索路径的各个方面进行配置。  
  
 `FindAssembliesByName`方法需要 CLR 初始化过程中，因此，为了调用程序集的解析逻辑。 因此，必须调用[CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) （在传递 COINITEE_DEFAULT） 之前调用`FindAssembliesByName`，然后通过调用按照[CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)。  
  
 `FindAssembliesByName` 返回[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)指向包含程序集名称的程序集清单中传递的文件。 如果给定的程序集名称未完全指定 （例如，如果它不包含版本），则可能会返回多个程序集。  
  
 `FindAssembliesByName` 通常由尝试查找在编译时引用的程序集的编译器使用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [运行时如何定位程序集](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
