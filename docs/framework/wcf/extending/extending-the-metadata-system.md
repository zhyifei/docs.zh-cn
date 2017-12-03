---
title: "扩展元数据系统"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d0c729850e25e9fe4bec37dc366053de8c56f210
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="extending-the-metadata-system"></a>扩展元数据系统
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 元数据系统由一组类和接口组成，这些表示元数据的类和接口是实现基于服务的应用程序所必需的。 修改或扩展这些类，或者实现和配置这些接口，以便导出和导入自定义元数据（如 Web 服务描述语言 (WSDL) 扩展或自定义的 WS-PolicyAttachments 断言）。  
  
## <a name="in-this-section"></a>本节内容  
 [导出 WCF 扩展的自定义元数据](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md)  
 描述如何实现 <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> 接口以及如何使用该接口来在 WSDL 文档中嵌入自定义策略断言。  
  
 [WCF 扩展的导入自定义的元数据](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)  
 描述如何实现 <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> 接口以及如何使用该接口来读取和响应 WSDL 文档中的自定义策略断言。  
  
 [发布和检索元数据通过自定义绑定](../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 描述如何通过自定义绑定来交换元数据。
