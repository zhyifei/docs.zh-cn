---
title: 扩展元数据系统
ms.date: 03/30/2017
helpviewer_keywords:
- extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
ms.openlocfilehash: 7ccef0c2b908a8f78249742decd6c46a862e541e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488951"
---
# <a name="extending-the-metadata-system"></a>扩展元数据系统
Windows Communication Foundation (WCF) 元数据系统是一组类和表示实现基于服务的应用程序所需的元数据的接口。 修改或扩展这些类，或者实现和配置这些接口，以便导出和导入自定义元数据（如 Web 服务描述语言 (WSDL) 扩展或自定义的 WS-PolicyAttachments 断言）。  
  
## <a name="in-this-section"></a>本节内容  
 [导出 WCF 扩展的自定义元数据](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md)  
 描述如何实现 <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> 接口以及如何使用该接口来在 WSDL 文档中嵌入自定义策略断言。  
  
 [导入 WCF 扩展的自定义元数据](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)  
 描述如何实现 <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> 接口以及如何使用该接口来读取和响应 WSDL 文档中的自定义策略断言。  
  
 [通过自定义绑定发布和检索元数据](../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 描述如何通过自定义绑定来交换元数据。
