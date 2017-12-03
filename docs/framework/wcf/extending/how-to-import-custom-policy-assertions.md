---
title: "如何：导入自定义策略断言"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1f41d787-accb-4a10-bfc6-a807671d1581
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3cc7eecbef66c3e4a80759912260b973d441a8a3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-import-custom-policy-assertions"></a><span data-ttu-id="23762-102">如何：导入自定义策略断言</span><span class="sxs-lookup"><span data-stu-id="23762-102">How to: Import Custom Policy Assertions</span></span>
<span data-ttu-id="23762-103">策略断言说明服务终结点的功能和需求。</span><span class="sxs-lookup"><span data-stu-id="23762-103">Policy assertions describe the capabilities and requirements of a service endpoint.</span></span>  <span data-ttu-id="23762-104">客户端应用程序可以在服务元数据中使用策略断言来配置客户端绑定或自定义服务终结点的服务协定。</span><span class="sxs-lookup"><span data-stu-id="23762-104">Client applications can use policy assertions in service metadata to configure the client binding or to customize the service contract for a service endpoint.</span></span>  
  
 <span data-ttu-id="23762-105">自定义策略断言可通过实现 <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> 接口并将该对象传递给元数据系统或通过在应用程序配置文件中注册实现类型来导入。</span><span class="sxs-lookup"><span data-stu-id="23762-105">Custom policy assertions are imported by implementing the <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface and passing that object to the metadata system or by registering the implementation type in your application configuration file.</span></span>  <span data-ttu-id="23762-106"><xref:System.ServiceModel.Description.IPolicyImportExtension> 接口的实现必须提供默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="23762-106">Implementations of the <xref:System.ServiceModel.Description.IPolicyImportExtension> interface must provide a default constructor.</span></span>  
  
### <a name="to-import-custom-policy-assertions"></a><span data-ttu-id="23762-107">导入自定义策略断言</span><span class="sxs-lookup"><span data-stu-id="23762-107">To import custom policy assertions</span></span>  
  
1.  <span data-ttu-id="23762-108">在类上实现 <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> 接口。</span><span class="sxs-lookup"><span data-stu-id="23762-108">Implement the <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface on a class.</span></span> <span data-ttu-id="23762-109">请参见下面的过程。</span><span class="sxs-lookup"><span data-stu-id="23762-109">See the following procedures.</span></span>  
  
2.  <span data-ttu-id="23762-110">通过以下方式之一插入自定义策略导入程序：</span><span class="sxs-lookup"><span data-stu-id="23762-110">Insert the custom policy importer either by:</span></span>  
  
3.  <span data-ttu-id="23762-111">使用配置文件。</span><span class="sxs-lookup"><span data-stu-id="23762-111">Using a configuration file.</span></span> <span data-ttu-id="23762-112">请参见下面的过程。</span><span class="sxs-lookup"><span data-stu-id="23762-112">See the following procedures.</span></span>  
  
4.  <span data-ttu-id="23762-113">使用配置文件进行[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="23762-113">Using a configuration file with [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="23762-114">请参见下面的过程。</span><span class="sxs-lookup"><span data-stu-id="23762-114">See the following procedures.</span></span>  
  
5.  <span data-ttu-id="23762-115">以编程方式插入策略导入程序。</span><span class="sxs-lookup"><span data-stu-id="23762-115">Programmatically inserting the policy importer.</span></span> <span data-ttu-id="23762-116">请参见下面的过程。</span><span class="sxs-lookup"><span data-stu-id="23762-116">See the following procedures.</span></span>  
  
### <a name="to-implement-the-systemservicemodeldescriptionipolicyimportextension-interface-on-any-class"></a><span data-ttu-id="23762-117">在任何类上实现 System.ServiceModel.Description.IPolicyImportExtension 接口</span><span class="sxs-lookup"><span data-stu-id="23762-117">To implement the System.ServiceModel.Description.IPolicyImportExtension interface on any class</span></span>  
  
1.  <span data-ttu-id="23762-118">在 <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType> 方法中，对于感兴趣的每个策略主题，通过在传递给该方法的 <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=nameWithType> 对象上调用相应方法（具体取决于所需的断言范围），查找要导入的策略断言。</span><span class="sxs-lookup"><span data-stu-id="23762-118">In the <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType> method, for each policy subject that you are interested in, find the policy assertions that you want to import by calling the appropriate method (depending upon the scope of the assertion that you want) on the <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=nameWithType> object passed to the method.</span></span> <span data-ttu-id="23762-119">下面的代码示例演示如何使用 <xref:System.ServiceModel.Description.PolicyAssertionCollection.Remove%2A?displayProperty=nameWithType> 方法定位自定义策略断言并在一个步骤中将该断言从集合中删除。</span><span class="sxs-lookup"><span data-stu-id="23762-119">The following code example shows how to use the <xref:System.ServiceModel.Description.PolicyAssertionCollection.Remove%2A?displayProperty=nameWithType> method to locate the custom policy assertion and remove it from the collection in one step.</span></span> <span data-ttu-id="23762-120">如果使用删除方法定位并删除断言，则不必执行步骤 4。</span><span class="sxs-lookup"><span data-stu-id="23762-120">If you use the remove method to locate and remove the assertion, you do not have to perform step 4.</span></span>  
  
     [!code-csharp[CustomPolicySample#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/policyimporter.cs#9)]
     [!code-vb[CustomPolicySample#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/policyimporter.vb#9)]  
  
2.  <span data-ttu-id="23762-121">处理策略断言。</span><span class="sxs-lookup"><span data-stu-id="23762-121">Process the policy assertions.</span></span> <span data-ttu-id="23762-122">请注意，策略系统不会标准化嵌入的策略和 `wsp:optional`。</span><span class="sxs-lookup"><span data-stu-id="23762-122">Note that the policy system does not normalize nested policies and `wsp:optional`.</span></span> <span data-ttu-id="23762-123">您必须在策略导入扩展实现中处理这些结构。</span><span class="sxs-lookup"><span data-stu-id="23762-123">You must process these constructs in your policy import extension implementation.</span></span>  
  
3.  <span data-ttu-id="23762-124">对支持策略断言指定的功能或要求的绑定或协定执行自定义。</span><span class="sxs-lookup"><span data-stu-id="23762-124">Perform the customization to the binding or contract that supports the capability or requirement specified by the policy assertion.</span></span> <span data-ttu-id="23762-125">断言通常指示绑定需要特定配置或特定绑定元素。</span><span class="sxs-lookup"><span data-stu-id="23762-125">Typically assertions indicate that a binding requires a particular configuration or a specific binding element.</span></span> <span data-ttu-id="23762-126">可以通过访问 <xref:System.ServiceModel.Description.PolicyConversionContext.BindingElements%2A?displayProperty=nameWithType> 属性来进行这些修改。</span><span class="sxs-lookup"><span data-stu-id="23762-126">Make these modifications by accessing the <xref:System.ServiceModel.Description.PolicyConversionContext.BindingElements%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="23762-127">其他断言需要您修改协定。</span><span class="sxs-lookup"><span data-stu-id="23762-127">Other assertions require that you modify the contract.</span></span>  <span data-ttu-id="23762-128">可以使用 <xref:System.ServiceModel.Description.PolicyConversionContext.Contract%2A?displayProperty=nameWithType> 属性来访问并修改该协定。</span><span class="sxs-lookup"><span data-stu-id="23762-128">You can access and modify the contract using the <xref:System.ServiceModel.Description.PolicyConversionContext.Contract%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="23762-129">请注意，对于同一个绑定和协定，可能会多次调用策略导入程序，但导入的是不同的替代策略（如果一个替代策略导入失败）。</span><span class="sxs-lookup"><span data-stu-id="23762-129">Note that your policy importer may get called multiple times for the same binding and contract, but different policy alternatives if importing a policy alternative fails.</span></span> <span data-ttu-id="23762-130">您的代码应该能够处理这一行为。</span><span class="sxs-lookup"><span data-stu-id="23762-130">Your code should be resilient to this behavior.</span></span>  
  
4.  <span data-ttu-id="23762-131">从断言集合中删除自定义策略断言。</span><span class="sxs-lookup"><span data-stu-id="23762-131">Remove the custom policy assertion from the assertion collection.</span></span> <span data-ttu-id="23762-132">如果不删除该断言，[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 将假定策略导入失败，并将不导入相关绑定。</span><span class="sxs-lookup"><span data-stu-id="23762-132">If you do not remove the assertion [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] assumes that the policy import was unsuccessful and does not import the associated binding.</span></span> <span data-ttu-id="23762-133">如果您使用 <xref:System.ServiceModel.Description.PolicyAssertionCollection.Remove%2A?displayProperty=nameWithType> 方法定位自定义策略断言并在一个步骤中将该断言从集合中删除，则不必执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="23762-133">If you used the <xref:System.ServiceModel.Description.PolicyAssertionCollection.Remove%2A?displayProperty=nameWithType> method to locate the custom policy assertion and remove it from the collection in one step you do not have to perform this step.</span></span>  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-using-a-configuration-file"></a><span data-ttu-id="23762-134">使用配置文件将自定义策略导入程序插入到元数据系统</span><span class="sxs-lookup"><span data-stu-id="23762-134">To insert the custom policy importer into the metadata System using a configuration file</span></span>  
  
1.  <span data-ttu-id="23762-135">添加到导入程序类型`<extensions>`内的元素[ \<policyImporters >](../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)客户端配置文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="23762-135">Add the importer type to the `<extensions>` element inside the [\<policyImporters>](../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md) element in the client configuration file.</span></span>  
  
     [!code-xml[CustomPolicySample#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/client.exe.config#7)]   
  
2.  <span data-ttu-id="23762-136">在客户端应用程序中，使用 <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType> 或 <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> 解析元数据，这会自动调用导入程序。</span><span class="sxs-lookup"><span data-stu-id="23762-136">In the client application, use the <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType> or <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> to resolve the metadata and the importer is invoked automatically.</span></span>  
  
     [!code-csharp[CustomPolicySample#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/client.cs#10)]
     [!code-vb[CustomPolicySample#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/client.vb#10)]  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-using-svcutilexe"></a><span data-ttu-id="23762-137">使用 Svcutil.exe 将自定义策略导入程序插入到元数据系统</span><span class="sxs-lookup"><span data-stu-id="23762-137">To insert the custom policy importer into the metadata system using Svcutil.exe</span></span>  
  
1.  <span data-ttu-id="23762-138">添加到导入程序类型`<extensions>`内的元素[ \<policyImporters >](../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md) Svcutil.exe.config 配置文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="23762-138">Add the importer type to the `<extensions>` element inside the [\<policyImporters>](../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md) element in the Svcutil.exe.config configuration file.</span></span> <span data-ttu-id="23762-139">也可以通过使用 `/svcutilConfig` 选项指示 Svcutil.exe 加载在其他配置文件中注册的策略导入程序类型。</span><span class="sxs-lookup"><span data-stu-id="23762-139">You can also point Svcutil.exe to load policy importer types registered in a different configuration file by using the `/svcutilConfig` option.</span></span>  
  
2.  <span data-ttu-id="23762-140">使用[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)导入元数据和导入程序自动调用。</span><span class="sxs-lookup"><span data-stu-id="23762-140">Use [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to import the metadata and the importer is invoked automatically.</span></span>  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-programmatically"></a><span data-ttu-id="23762-141">以编程方式将自定义策略导入程序插入到元数据系统</span><span class="sxs-lookup"><span data-stu-id="23762-141">To insert the custom policy importer into the metadata system programmatically</span></span>  
  
1.  <span data-ttu-id="23762-142">导入元数据之前，将导入程序添加到 <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A?displayProperty=nameWithType> 属性（例如，如果您使用的是 <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>）。</span><span class="sxs-lookup"><span data-stu-id="23762-142">Add the importer to the <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A?displayProperty=nameWithType> property (for example, if you are using the <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>) prior to importing the metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23762-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23762-143">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType>  
 <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>  
 <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType>  
 [<span data-ttu-id="23762-144">扩展元数据系统</span><span class="sxs-lookup"><span data-stu-id="23762-144">Extending the Metadata System</span></span>](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)
