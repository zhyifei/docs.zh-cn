---
title: "如何：手动生成客户端数据服务类（WCF 数据服务）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f72f898b2a80d7d88a74deabe013e2eecc298bdd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a><span data-ttu-id="41100-102">如何：手动生成客户端数据服务类（WCF 数据服务）</span><span class="sxs-lookup"><span data-stu-id="41100-102">How to: Manually Generate Client Data Service Classes (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="41100-103">与 Visual Studio 使你能够使用时自动生成客户端数据服务类集成**添加服务引用**对话框以将对数据服务的引用添加到 Visual Studio 项目中。</span><span class="sxs-lookup"><span data-stu-id="41100-103"> integrates with Visual Studio to enable you to automatically generate client data service classes when you use the **Add Service Reference** dialog box to add a reference to a data service in a Visual Studio project.</span></span> <span data-ttu-id="41100-104">有关详细信息，请参阅[如何： 添加数据服务引用](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="41100-104">For more information, see [How to: Add a Data Service Reference](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span></span> <span data-ttu-id="41100-105">此外，您也可以使用代码生成工具 `DataSvcUtil.exe` 手动生成相同的客户端数据服务类。</span><span class="sxs-lookup"><span data-stu-id="41100-105">You can also manually generate the same client data service classes by using the code-generation tool, `DataSvcUtil.exe`.</span></span> <span data-ttu-id="41100-106">此工具随 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 提供，可根据数据服务定义生成 .NET Framework 类。</span><span class="sxs-lookup"><span data-stu-id="41100-106">This tool, which is included with [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], generates .NET Framework classes from the data service definition.</span></span> <span data-ttu-id="41100-107">还可以使用此工具根据概念模型 (.csdl) 文件和表示 Visual Studio 项目中的实体框架模型的 .edmx 文件生成数据服务类。</span><span class="sxs-lookup"><span data-stu-id="41100-107">It can also be used to generate data service classes from the conceptual model (.csdl) file and from the .edmx file that represents an Entity Framework model in a Visual Studio project.</span></span>  
  
 <span data-ttu-id="41100-108">本主题中的示例基于 Northwind 示例数据服务创建客户端数据服务类。</span><span class="sxs-lookup"><span data-stu-id="41100-108">The example in this topic creates client data service classes based on the Northwind sample data service.</span></span> <span data-ttu-id="41100-109">在完成时创建此服务[WCF 数据服务快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="41100-109">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="41100-110">本主题中的某些示例需要 Northwind 模型的概念模型文件。</span><span class="sxs-lookup"><span data-stu-id="41100-110">Some examples in this topic require the conceptual model file for the Northwind model.</span></span> <span data-ttu-id="41100-111">有关详细信息，请参阅[如何： 使用 EdmGen.exe 生成模型和映射文件](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)。</span><span class="sxs-lookup"><span data-stu-id="41100-111">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span> <span data-ttu-id="41100-112">本主题中的某些示例需要 Northwind 模型的 .edmx 文件。</span><span class="sxs-lookup"><span data-stu-id="41100-112">Some examples in this topic require the .edmx file for the Northwind model.</span></span> <span data-ttu-id="41100-113">有关详细信息，请参阅[.edmx 文件概述](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)。</span><span class="sxs-lookup"><span data-stu-id="41100-113">For more information, see [.edmx File Overview](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4).</span></span>  
  
### <a name="to-generate-c-classes-that-support-data-binding"></a><span data-ttu-id="41100-114">生成支持数据绑定的 C# 类</span><span class="sxs-lookup"><span data-stu-id="41100-114">To generate C# classes that support data binding</span></span>  
  
-   <span data-ttu-id="41100-115">在命令提示符下执行以下命令（无换行符）：</span><span class="sxs-lookup"><span data-stu-id="41100-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="41100-116">必须用 Northwind 示例数据服务实例的 URI 替换向 `/uri:` 参数提供的值。</span><span class="sxs-lookup"><span data-stu-id="41100-116">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>  
  
### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a><span data-ttu-id="41100-117">生成支持数据绑定的 Visual Basic 类</span><span class="sxs-lookup"><span data-stu-id="41100-117">To generate Visual Basic classes that support data binding</span></span>  
  
-   <span data-ttu-id="41100-118">在命令提示符下执行以下命令（无换行符）：</span><span class="sxs-lookup"><span data-stu-id="41100-118">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="41100-119">必须用 Northwind 示例数据服务实例的 URI 替换向 `/uri:` 参数提供的值。</span><span class="sxs-lookup"><span data-stu-id="41100-119">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>  
  
### <a name="to-generate-c-classes-based-on-the-service-uri"></a><span data-ttu-id="41100-120">基于服务 URI 生成 C# 类</span><span class="sxs-lookup"><span data-stu-id="41100-120">To generate C# classes based on the service URI</span></span>  
  
-   <span data-ttu-id="41100-121">在命令提示符下执行以下命令（无换行符）：</span><span class="sxs-lookup"><span data-stu-id="41100-121">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="41100-122">必须用 Northwind 示例数据服务实例的 URI 替换向 `/uri:` 参数提供的值。</span><span class="sxs-lookup"><span data-stu-id="41100-122">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>  
  
### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a><span data-ttu-id="41100-123">基于服务 URI 生成 Visual Basic 类</span><span class="sxs-lookup"><span data-stu-id="41100-123">To generate Visual Basic classes based on the service URI</span></span>  
  
-   <span data-ttu-id="41100-124">在命令提示符下执行以下命令（无换行符）：</span><span class="sxs-lookup"><span data-stu-id="41100-124">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="41100-125">必须用 Northwind 示例数据服务实例的 URI 替换向 `/uri:` 参数提供的值。</span><span class="sxs-lookup"><span data-stu-id="41100-125">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>  
  
### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="41100-126">基于概念模型文件 (CSDL) 生成 C# 类</span><span class="sxs-lookup"><span data-stu-id="41100-126">To generate C# classes based on the conceptual model file (CSDL)</span></span>  
  
-   <span data-ttu-id="41100-127">在命令提示符下执行以下命令（无换行符）：</span><span class="sxs-lookup"><span data-stu-id="41100-127">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs  
    ```  
  
### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="41100-128">基于概念模型文件 (CSDL) 生成 Visual Basic 类</span><span class="sxs-lookup"><span data-stu-id="41100-128">To generate Visual Basic classes based on the conceptual model file (CSDL)</span></span>  
  
-   <span data-ttu-id="41100-129">在命令提示符下执行以下命令（无换行符）：</span><span class="sxs-lookup"><span data-stu-id="41100-129">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb  
    ```  
  
### <a name="to-generate-c-classes-based-on-the-edmx-file"></a><span data-ttu-id="41100-130">基于 .edmx 文件生成 C# 类</span><span class="sxs-lookup"><span data-stu-id="41100-130">To generate C# classes based on the .edmx file</span></span>  
  
-   <span data-ttu-id="41100-131">在命令提示符下执行以下命令（无换行符）：</span><span class="sxs-lookup"><span data-stu-id="41100-131">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs   
    ```  
  
### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a><span data-ttu-id="41100-132">基于 .edmx 文件生成 Visual Basic 类</span><span class="sxs-lookup"><span data-stu-id="41100-132">To generate Visual Basic classes based on the .edmx file</span></span>  
  
-   <span data-ttu-id="41100-133">在命令提示符下执行以下命令（无换行符）：</span><span class="sxs-lookup"><span data-stu-id="41100-133">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="41100-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="41100-134">See Also</span></span>  
 [<span data-ttu-id="41100-135">生成数据服务客户端库</span><span class="sxs-lookup"><span data-stu-id="41100-135">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
 [<span data-ttu-id="41100-136">如何：添加数据服务引用</span><span class="sxs-lookup"><span data-stu-id="41100-136">How to: Add a Data Service Reference</span></span>](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)  
 [<span data-ttu-id="41100-137">WCF 诗句服务客户端实用工具 (DataSvcUtil.exe)</span><span class="sxs-lookup"><span data-stu-id="41100-137">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)
