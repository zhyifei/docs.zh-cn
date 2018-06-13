---
title: 如何：在 .NET Framework 4 环境下运行的 IIS 中承载使用 .NET Framework 3.5 编写的 WCF 服务
ms.date: 03/30/2017
ms.assetid: 9aabc785-068d-4d32-8841-3ef39308d8d6
ms.openlocfilehash: 83343cef119f6c8b97fd8f1be50c229c64b10227
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499123"
---
# <a name="how-to-host-a-wcf-service-written-with-net-framework-35-in-iis-running-under-net-framework-4"></a><span data-ttu-id="f4277-102">如何：在 .NET Framework 4 环境下运行的 IIS 中承载使用 .NET Framework 3.5 编写的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="f4277-102">How to: Host a WCF Service Written with .NET Framework 3.5 in IIS Running Under .NET Framework 4</span></span>
<span data-ttu-id="f4277-103">承载 Windows Communication Foundation (WCF) 服务使用编写时[!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)]上机运行[!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)]，可能会收到<xref:System.ServiceModel.ProtocolException>包含以下文本。</span><span class="sxs-lookup"><span data-stu-id="f4277-103">When hosting a Windows Communication Foundation (WCF) service written with [!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)] on a machine running [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], you may get a <xref:System.ServiceModel.ProtocolException> with the following text.</span></span>  
  
```Output  
Unhandled Exception: System.ServiceModel.ProtocolException: The content type text/html; charset=utf-8 of the response message does not match the content type of the binding (application/soap+xml; charset=utf-8). If using a custom encoder, be sure that the IsContentTypeSupported method is implemented properly. The first 1024 bytes of the response were: '<html>    <head>        <title>The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.</title>...  
```  
  
 <span data-ttu-id="f4277-104">或者，如果尝试浏览服务的 .svc 文件，您可能会看到包含以下文本的错误页面。</span><span class="sxs-lookup"><span data-stu-id="f4277-104">Or if you try to browse to the service's .svc file you may see an error page with the following text.</span></span>  
  
```Output  
The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required 'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.  
```  
  
 <span data-ttu-id="f4277-105">出现上述错误的原因是，运行 IIS 的应用程序域正在运行 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]，WCF 服务应在 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 下运行。</span><span class="sxs-lookup"><span data-stu-id="f4277-105">These errors occur because the application domain IIS is running within is running [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] and the WCF service is expecting to run under [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].</span></span> <span data-ttu-id="f4277-106">本主题说明运行服务所需进行的修改。</span><span class="sxs-lookup"><span data-stu-id="f4277-106">This topic explains the modifications required to get the service to run.</span></span>  
  
 <span data-ttu-id="f4277-107">接下来查找 <`compilers`> 元素，然后更改具有值为 4.0 的 CompilerVersion 提供程序选项。</span><span class="sxs-lookup"><span data-stu-id="f4277-107">Next find the <`compilers`> element and change the CompilerVersion provider option to have a value of 4.0.</span></span> <span data-ttu-id="f4277-108">默认情况下，有两个 <`compiler`> 下的元素 <`compilers`> 元素。</span><span class="sxs-lookup"><span data-stu-id="f4277-108">By default, there are two <`compiler`> elements under the <`compilers`> element.</span></span> <span data-ttu-id="f4277-109">您必须同时更新这两个元素的 CompilerVersion 提供程序选项，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="f4277-109">You must update the CompilerVersion provider option for both as shown in the following example.</span></span>  
  
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
  
### <a name="add-the-required-targetframework-attribute"></a><span data-ttu-id="f4277-110">添加所需的 targetFramework 特性</span><span class="sxs-lookup"><span data-stu-id="f4277-110">Add the required targetFramework attribute</span></span>  
  
1.  <span data-ttu-id="f4277-111">打开服务的 Web.config 文件并查找 <`compilation`> 元素。</span><span class="sxs-lookup"><span data-stu-id="f4277-111">Open the service's Web.config file and look for the <`compilation`> element.</span></span>  
  
2.  <span data-ttu-id="f4277-112">添加`targetFramework`属性设为 <`compilation`> 元素，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="f4277-112">Add the `targetFramework` attribute to the <`compilation`> element as shown in the following example.</span></span>  
  
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
  
3.  <span data-ttu-id="f4277-113">找到 <`compilers`> 元素，然后更改具有值为 4.0 的 CompilerVersion 提供程序选项。</span><span class="sxs-lookup"><span data-stu-id="f4277-113">Find the <`compilers`> element and change the CompilerVersion provider option to have a value of 4.0.</span></span> <span data-ttu-id="f4277-114">默认情况下，有两个 <`compiler`> 下的元素 <`compilers`> 元素。</span><span class="sxs-lookup"><span data-stu-id="f4277-114">By default, there are two <`compiler`> elements under the <`compilers`> element.</span></span> <span data-ttu-id="f4277-115">您必须同时更新这两个元素的 CompilerVersion 提供程序选项，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="f4277-115">You must update the CompilerVersion provider option for both as shown in the following example.</span></span>  
  
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
