---
title: WCF 配置架构
ms.date: 03/30/2017
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
ms.openlocfilehash: bcbc12d35dae59fcd43d5fbf2d4c936c8e4a4423
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357023"
---
# <a name="wcf-configuration-schema"></a><span data-ttu-id="b6f91-102">WCF 配置架构</span><span class="sxs-lookup"><span data-stu-id="b6f91-102">WCF Configuration Schema</span></span>
<span data-ttu-id="b6f91-103">Windows Communication Foundation (WCF) 配置元素，可以配置 WCF 服务和客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="b6f91-103">Windows Communication Foundation (WCF) configuration elements enable you to configure WCF service and client applications.</span></span> <span data-ttu-id="b6f91-104">可以使用[配置编辑器工具 (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) 创建和修改客户端和服务的配置文件。</span><span class="sxs-lookup"><span data-stu-id="b6f91-104">You can use the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) to create and modify configuration files for clients and services.</span></span> <span data-ttu-id="b6f91-105">由于配置文件的格式都是以 XML 形式设置的，因此，如果要使用文本编辑器手动编辑这些文件，则您必须熟悉 XML。</span><span class="sxs-lookup"><span data-stu-id="b6f91-105">Since the configuration files are formatted as XML, you must be familiar with XML if you want to manually edit them using a text editor.</span></span> <span data-ttu-id="b6f91-106">否则，您可能会遇到一些问题，如找不到某个 XML 元素标记或特性。</span><span class="sxs-lookup"><span data-stu-id="b6f91-106">Otherwise, you may run into issues such as an unfound XML element tag or attribute.</span></span> <span data-ttu-id="b6f91-107">这是因为 XML 元素标记和特性是区分大小写的。</span><span class="sxs-lookup"><span data-stu-id="b6f91-107">This is because XML element tags and attributes are case-sensitive.</span></span>  
  
 <span data-ttu-id="b6f91-108">WCF 配置系统基于<xref:System.Configuration>命名空间。</span><span class="sxs-lookup"><span data-stu-id="b6f91-108">The WCF configuration system is based on the <xref:System.Configuration> namespace.</span></span> <span data-ttu-id="b6f91-109">因此，您可以使用 <xref:System.Configuration> 命名空间提供的所有标准功能（如配置锁定、加密和合并）以提高应用程序及其配置的安全性。</span><span class="sxs-lookup"><span data-stu-id="b6f91-109">Therefore, you can use all the standard features provided by the <xref:System.Configuration> namespace, such as configuration locking, encryption and merging to increase the security of your application and its configuration.</span></span> <span data-ttu-id="b6f91-110">有关这些概念的更多信息，请参见下列主题。</span><span class="sxs-lookup"><span data-stu-id="b6f91-110">For more information on these concepts, see the following topics.</span></span>  
  
 [<span data-ttu-id="b6f91-111">加密配置信息</span><span class="sxs-lookup"><span data-stu-id="b6f91-111">Encrypting Configuration Information</span></span>](http://go.microsoft.com/fwlink/?LinkId=95337)  
  
 [<span data-ttu-id="b6f91-112">锁定配置设置</span><span class="sxs-lookup"><span data-stu-id="b6f91-112">Locking Configuration Settings</span></span>](http://go.microsoft.com/fwlink/?LinkId=95338)  
  
 <span data-ttu-id="b6f91-113">本节描述每个配置项的所有可能的值，以及它如何与其他 WCF 配置元素进行交互。</span><span class="sxs-lookup"><span data-stu-id="b6f91-113">This section describes all possible values of each configuration item, and how it interacts with other WCF configuration elements.</span></span> <span data-ttu-id="b6f91-114">下面的映射演示了 WCF 配置架构。</span><span class="sxs-lookup"><span data-stu-id="b6f91-114">The following map illustrates the WCF configuration schema.</span></span>  
  
 <span data-ttu-id="b6f91-115">![WCF 配置架构](../../../../../docs/framework/configure-apps/file-schema/wcf/media/orcasconfigschema.gif "OrcasConfigSchema")</span><span class="sxs-lookup"><span data-stu-id="b6f91-115">![WCF Configuration Schema](../../../../../docs/framework/configure-apps/file-schema/wcf/media/orcasconfigschema.gif "OrcasConfigSchema")</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="b6f91-116">你应保护应用程序配置文件 (app.config) 与相应访问控制列表 (ACL) 以防止任何潜在的安全威胁中的 WCF 配置节。</span><span class="sxs-lookup"><span data-stu-id="b6f91-116">You should protect WCF configuration sections in your application configuration files (app.config) with appropriate Access Control Lists (ACL) to prevent any potential security threats.</span></span>  <span data-ttu-id="b6f91-117">例如，你应确保仅有适当的人员可以访问或修改有关应用程序绑定的安全设置或服务的配置文件的服务模型节。</span><span class="sxs-lookup"><span data-stu-id="b6f91-117">For example, you should make sure that only the appropriate people can access or modify the security settings on application bindings, or the service model section of the configuration file for a service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b6f91-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="b6f91-118">In This Section</span></span>  
 [<span data-ttu-id="b6f91-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b6f91-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
 <span data-ttu-id="b6f91-120">描述 `ServiceModel` 元素。</span><span class="sxs-lookup"><span data-stu-id="b6f91-120">Describes the `ServiceModel` element.</span></span>  
  
 [<span data-ttu-id="b6f91-121">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="b6f91-121">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)  
 <span data-ttu-id="b6f91-122">配置 SMSvcHost.exe 工具。</span><span class="sxs-lookup"><span data-stu-id="b6f91-122">Configures the SMSvcHost.exe tool.</span></span>  
  
 [<span data-ttu-id="b6f91-123">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="b6f91-123">\<system.runtime.serialization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
 <span data-ttu-id="b6f91-124">当使用序列化程序（如 <xref:System.Runtime.Serialization.DataContractSerializer>）时，用于设置选项的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="b6f91-124">The top-level element for setting options when using serializers such as the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b6f91-125">相关章节</span><span class="sxs-lookup"><span data-stu-id="b6f91-125">Related Sections</span></span>  
 [<span data-ttu-id="b6f91-126">配置 Windows Communication Foundation 应用程序</span><span class="sxs-lookup"><span data-stu-id="b6f91-126">Configuring Windows Communication Foundation Applications</span></span>](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a)  
 <span data-ttu-id="b6f91-127">描述如何配置 WCF 服务和客户端。</span><span class="sxs-lookup"><span data-stu-id="b6f91-127">Describes how to configure WCF services and clients.</span></span>
