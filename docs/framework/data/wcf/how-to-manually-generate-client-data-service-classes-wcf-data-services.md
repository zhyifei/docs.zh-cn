---
title: 如何：手动生成客户端数据服务类（WCF 数据服务）
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: 24d19f10e025b765cfc7df73ba80d223fbfa8074
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a>如何：手动生成客户端数据服务类（WCF 数据服务）
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 与 Visual Studio 使你能够使用时自动生成客户端数据服务类集成**添加服务引用**对话框以将对数据服务的引用添加到 Visual Studio 项目中。 有关详细信息，请参阅[如何： 添加数据服务引用](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)。 此外，您也可以使用代码生成工具 `DataSvcUtil.exe` 手动生成相同的客户端数据服务类。 此工具随 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 提供，可根据数据服务定义生成 .NET Framework 类。 还可以使用此工具根据概念模型 (.csdl) 文件和表示 Visual Studio 项目中的实体框架模型的 .edmx 文件生成数据服务类。  
  
 本主题中的示例基于 Northwind 示例数据服务创建客户端数据服务类。 在完成时创建此服务[WCF 数据服务快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)。 本主题中的某些示例需要 Northwind 模型的概念模型文件。 有关详细信息，请参阅[如何： 使用 EdmGen.exe 生成模型和映射文件](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)。 本主题中的某些示例需要 Northwind 模型的 .edmx 文件。 有关详细信息，请参阅[.edmx 文件概述](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)。  
  
### <a name="to-generate-c-classes-that-support-data-binding"></a>生成支持数据绑定的 C# 类  
  
-   在命令提示符下执行以下命令（无换行符）：  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  必须用 Northwind 示例数据服务实例的 URI 替换向 `/uri:` 参数提供的值。  
  
### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a>生成支持数据绑定的 Visual Basic 类  
  
-   在命令提示符下执行以下命令（无换行符）：  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  必须用 Northwind 示例数据服务实例的 URI 替换向 `/uri:` 参数提供的值。  
  
### <a name="to-generate-c-classes-based-on-the-service-uri"></a>基于服务 URI 生成 C# 类  
  
-   在命令提示符下执行以下命令（无换行符）：  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  必须用 Northwind 示例数据服务实例的 URI 替换向 `/uri:` 参数提供的值。  
  
### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a>基于服务 URI 生成 Visual Basic 类  
  
-   在命令提示符下执行以下命令（无换行符）：  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  必须用 Northwind 示例数据服务实例的 URI 替换向 `/uri:` 参数提供的值。  
  
### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a>基于概念模型文件 (CSDL) 生成 C# 类  
  
-   在命令提示符下执行以下命令（无换行符）：  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs  
    ```  
  
### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a>基于概念模型文件 (CSDL) 生成 Visual Basic 类  
  
-   在命令提示符下执行以下命令（无换行符）：  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb  
    ```  
  
### <a name="to-generate-c-classes-based-on-the-edmx-file"></a>基于 .edmx 文件生成 C# 类  
  
-   在命令提示符下执行以下命令（无换行符）：  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs   
    ```  
  
### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a>基于 .edmx 文件生成 Visual Basic 类  
  
-   在命令提示符下执行以下命令（无换行符）：  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb   
    ```  
  
## <a name="see-also"></a>请参阅  
 [生成数据服务客户端库](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
 [如何：添加数据服务引用](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)  
 [WCF 诗句服务客户端实用工具 (DataSvcUtil.exe)](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)
