---
title: "扩展元数据系统"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aca7a7aba7ef4a40100e9858561d197916b71544
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="extending-the-metadata-system"></a><span data-ttu-id="e1adc-102">扩展元数据系统</span><span class="sxs-lookup"><span data-stu-id="e1adc-102">Extending the Metadata System</span></span>
<span data-ttu-id="e1adc-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 元数据系统由一组类和接口组成，这些表示元数据的类和接口是实现基于服务的应用程序所必需的。</span><span class="sxs-lookup"><span data-stu-id="e1adc-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="e1adc-104">修改或扩展这些类，或者实现和配置这些接口，以便导出和导入自定义元数据（如 Web 服务描述语言 (WSDL) 扩展或自定义的 WS-PolicyAttachments 断言）。</span><span class="sxs-lookup"><span data-stu-id="e1adc-104">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1adc-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="e1adc-105">In This Section</span></span>  
 [<span data-ttu-id="e1adc-106">导出 WCF 扩展的自定义元数据</span><span class="sxs-lookup"><span data-stu-id="e1adc-106">Exporting Custom Metadata for a WCF Extension</span></span>](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="e1adc-107">描述如何实现 <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> 接口以及如何使用该接口来在 WSDL 文档中嵌入自定义策略断言。</span><span class="sxs-lookup"><span data-stu-id="e1adc-107">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface to embed custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="e1adc-108">导入 WCF 扩展的自定义元数据</span><span class="sxs-lookup"><span data-stu-id="e1adc-108">Importing Custom Metadata for a WCF Extension</span></span>](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="e1adc-109">描述如何实现 <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> 接口以及如何使用该接口来读取和响应 WSDL 文档中的自定义策略断言。</span><span class="sxs-lookup"><span data-stu-id="e1adc-109">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface to read and respond to custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="e1adc-110">通过自定义绑定发布和检索元数据</span><span class="sxs-lookup"><span data-stu-id="e1adc-110">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 <span data-ttu-id="e1adc-111">描述如何通过自定义绑定来交换元数据。</span><span class="sxs-lookup"><span data-stu-id="e1adc-111">Describes how to exchange metadata over custom bindings.</span></span>
