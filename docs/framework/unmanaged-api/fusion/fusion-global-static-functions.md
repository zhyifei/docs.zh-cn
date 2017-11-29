---
title: "合成全局静态函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged global static functions [.NET Framework], fusion
- fusion global static functions [.NET Framework]
- global static functions [.NET Framework fusion]
ms.assetid: 229b2188-9168-4b44-a987-e1f515494688
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 38462833e3b0ccd56265b02d9a1bc9f37ac12f5f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="fusion-global-static-functions"></a>合成全局静态函数
本部分描述合成 API 使用的非托管全局静态函数。  
  
## <a name="in-this-section"></a>本节内容  
 [ClearDownloadCache 函数](../../../../docs/framework/unmanaged-api/fusion/cleardownloadcache-function.md)  
 清除下载的程序集的全局程序集缓存。  
  
 [CompareAssemblyIdentity 函数](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)  
 比较两个程序集标识，以确定它们是否等效。  
  
 [CreateApplicationContext 函数](../../../../docs/framework/unmanaged-api/fusion/createapplicationcontext-function.md)  
 仅限内部使用。 （此函数支持的.NET Framework 基础结构，不宜在代码中直接使用。）  
  
 [CreateAssemblyCache 函数](../../../../docs/framework/unmanaged-api/fusion/createassemblycache-function.md)  
 获取一个指针，到新[IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)表示全局程序集缓存的实例。  
  
 [CreateAssemblyEnum 函数](../../../../docs/framework/unmanaged-api/fusion/createassemblyenum-function.md)  
 获取一个指向[IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)实例表示的指定程序集中存在的对象的列表。  
  
 [CreateAssemblyNameObject 函数](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)  
 获取一个指向[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)表示具有指定名称的程序集的唯一标识的实例。  
  
 [CreateHistoryReader 函数](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 创建指定的文件历史记录读取器。  
  
 [CreateInstallReferenceEnum 函数](../../../../docs/framework/unmanaged-api/fusion/createinstallreferenceenum-function.md)  
 获取一个指向[IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)表示的指定程序集的应用程序的引用列表的实例。  
  
 [GetAppIdAuthority 函数](../../../../docs/framework/unmanaged-api/fusion/getappidauthority-function.md)  
 获取一个指向[IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)管理密钥的应用程序标识和引用的实例。  
  
 [GetAssemblyIdentityFromFile 函数](../../../../docs/framework/unmanaged-api/fusion/getassemblyidentityfromfile-function.md)  
 获取一个指向`IUnknown`使用指定的对象`IID`中处指定的文件路径的程序集。  
  
 [GetCachePath 函数](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)  
 获取使用指定的标志的缓存程序集的路径。  
  
 [GetHistoryFileDirectory 函数](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 检索应用程序历史记录目录的路径。  
  
 [GetIdentityAuthority 函数](../../../../docs/framework/unmanaged-api/fusion/getidentityauthority-function.md)  
 获取一个指向[IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)管理代码对象的键的实例。  
  
 [IsFrameworkAssembly 函数](../../../../docs/framework/unmanaged-api/fusion/isframeworkassembly-function.md)  
 获取一个值，该值指示指定的程序集是否为托管对象。  
  
 [NukeDownloadedCache 函数](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)  
 删除公共语言运行时下载缓存。  
  
 [PreBindAssemblyEx 函数](../../../../docs/framework/unmanaged-api/fusion/prebindassemblyex-function.md)  
 获取程序集的策略后的显示名称。  
  
## <a name="related-sections"></a>相关章节  
 [合成接口](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
  
 [合成枚举](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)  
  
 [合成结构](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
  
 [全局程序集缓存](../../../../docs/framework/app-domains/gac.md)
