---
title: 扩展元数据系统
ms.date: 03/30/2017
helpviewer_keywords:
- extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
ms.openlocfilehash: 7ccef0c2b908a8f78249742decd6c46a862e541e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991297"
---
# <a name="extending-the-metadata-system"></a><span data-ttu-id="56a47-102">扩展元数据系统</span><span class="sxs-lookup"><span data-stu-id="56a47-102">Extending the Metadata System</span></span>
<span data-ttu-id="56a47-103">Windows Communication Foundation (WCF) 元数据系统是一组类和接口，它表示实现基于服务的应用程序所需的元数据。</span><span class="sxs-lookup"><span data-stu-id="56a47-103">The Windows Communication Foundation (WCF) metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="56a47-104">修改或扩展这些类，或者实现和配置这些接口，以便导出和导入自定义元数据（如 Web 服务描述语言 (WSDL) 扩展或自定义的 WS-PolicyAttachments 断言）。</span><span class="sxs-lookup"><span data-stu-id="56a47-104">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="56a47-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="56a47-105">In This Section</span></span>  
 [<span data-ttu-id="56a47-106">导出 WCF 扩展的自定义元数据</span><span class="sxs-lookup"><span data-stu-id="56a47-106">Exporting Custom Metadata for a WCF Extension</span></span>](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="56a47-107">描述如何实现 <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> 接口以及如何使用该接口来在 WSDL 文档中嵌入自定义策略断言。</span><span class="sxs-lookup"><span data-stu-id="56a47-107">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface to embed custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="56a47-108">导入 WCF 扩展的自定义元数据</span><span class="sxs-lookup"><span data-stu-id="56a47-108">Importing Custom Metadata for a WCF Extension</span></span>](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="56a47-109">描述如何实现 <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> 接口以及如何使用该接口来读取和响应 WSDL 文档中的自定义策略断言。</span><span class="sxs-lookup"><span data-stu-id="56a47-109">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface to read and respond to custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="56a47-110">通过自定义绑定发布和检索元数据</span><span class="sxs-lookup"><span data-stu-id="56a47-110">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 <span data-ttu-id="56a47-111">描述如何通过自定义绑定来交换元数据。</span><span class="sxs-lookup"><span data-stu-id="56a47-111">Describes how to exchange metadata over custom bindings.</span></span>
