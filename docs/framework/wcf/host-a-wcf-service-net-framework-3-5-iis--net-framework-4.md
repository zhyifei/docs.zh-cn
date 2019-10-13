---
title: 如何：在 .NET Framework 4 环境下运行的 IIS 中承载使用 .NET Framework 3.5 编写的 WCF 服务
ms.date: 03/30/2017
ms.assetid: 9aabc785-068d-4d32-8841-3ef39308d8d6
ms.openlocfilehash: 6a87fd5e3997e9d15810a5efb079da629908f854
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291534"
---
# <a name="how-to-host-a-wcf-service-written-with-net-framework-35-in-iis-running-under-net-framework-4"></a>如何：在 .NET Framework 4 环境下运行的 IIS 中承载使用 .NET Framework 3.5 编写的 WCF 服务
在运行 [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)] 的计算机上承载使用 [!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)] 编写的 Windows Communication Foundation （WCF）服务时，你可能会收到包含以下文本的 <xref:System.ServiceModel.ProtocolException>。  
  
```output  
Unhandled Exception: System.ServiceModel.ProtocolException: The content type text/html; charset=utf-8 of the response message does not match the content type of the binding (application/soap+xml; charset=utf-8). If using a custom encoder, be sure that the IsContentTypeSupported method is implemented properly. The first 1024 bytes of the response were: '<html>    <head>        <title>The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required 'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.</title>...  
```  
  
 或者，如果尝试浏览服务的 .svc 文件，您可能会看到包含以下文本的错误页面。  
  
```output  
The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required 'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.  
```  
  
 出现上述错误的原因是，运行 IIS 的应用程序域正在运行 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]，WCF 服务应在 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 下运行。 本主题说明运行服务所需进行的修改。  
  
 接下来，查找 < @no__t > 元素，并将 CompilerVersion 提供程序选项更改为值4.0。 默认情况下，< `compilers` > 元素下有两个 < @no__t 的 > 元素。 您必须同时更新这两个元素的 CompilerVersion 提供程序选项，如下面的示例所示。  
  
```xml  
<system.codedom>  
      <compilers>  
        <compiler language="c#;cs;csharp" extension=".cs" warningLevel="4"  
                  type="Microsoft.CSharp.CSharpCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
          <providerOption name="CompilerVersion" value="v3.5"/>  
          <providerOption name="WarnAsError" value="false"/>  
        </compiler>  
        <compiler language="vb;vbs;visualbasic;vbscript" extension=".vb" warningLevel="4"  
                  type="Microsoft.VisualBasic.VBCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
          <providerOption name="CompilerVersion" value="v3.5"/>  
          <providerOption name="OptionInfer" value="true"/>  
          <providerOption name="WarnAsError" value="false"/>  
        </compiler>  
      </compilers>  
    </system.codedom>  
```  
  
### <a name="add-the-required-targetframework-attribute"></a>添加所需的 targetFramework 特性  
  
1. 打开服务的 Web.config 文件，查找 < @no__t > 元素。  
  
2. 将 `targetFramework` 特性添加到 < `compilation` > 元素，如下面的示例中所示。  
  
    ```xml  
    <compilation debug="false"  
            targetFramework="4.0">  
  
            <assemblies>  
              <add assembly="System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
              <add assembly="System.Xml.Linq, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
              <add assembly="System.Web.Extensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=31BF3856AD364E35"/>  
              <add assembly="System.Data.DataSetExtensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
            </assemblies>  
  
          </compilation>  
    ```  
  
3. 查找 < @no__t > 元素，并将 CompilerVersion 提供程序选项更改为值4.0。 默认情况下，< `compilers` > 元素下有两个 < @no__t 的 > 元素。 您必须同时更新这两个元素的 CompilerVersion 提供程序选项，如下面的示例所示。  
  
    ```xml  
    <system.codedom>  
          <compilers>  
            <compiler language="c#;cs;csharp" extension=".cs" warningLevel="4"  
                      type="Microsoft.CSharp.CSharpCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
              <providerOption name="CompilerVersion" value="v3.5"/>  
              <providerOption name="WarnAsError" value="false"/>  
            </compiler>  
            <compiler language="vb;vbs;visualbasic;vbscript" extension=".vb" warningLevel="4"  
                      type="Microsoft.VisualBasic.VBCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
              <providerOption name="CompilerVersion" value="v3.5"/>  
              <providerOption name="OptionInfer" value="true"/>  
              <providerOption name="WarnAsError" value="false"/>  
            </compiler>  
          </compilers>  
        </system.codedom>  
    ```
