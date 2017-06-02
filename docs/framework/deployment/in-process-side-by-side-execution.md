---
title: "进程内并行执行 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "进程内并行执行"
  - "并行执行, 进程内"
ms.assetid: 18019342-a810-4986-8ec2-b933a17c2267
caps.latest.revision: 25
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 25
---
# 进程内并行执行
以 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]开始，可使用进程内并行承载来在单独的进程中运行多个公共语言运行时 \(CLR\) 版本。  默认情况下，托管 COM 组件使用生成它们所用的 .NET Framework 版本运行，而不论为进程加载的是哪个 .NET Framework 版本。  
  
## 背景  
 .NET Framework 现在始终为托管代码应用程序提供并行承载，但是在 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 之前，它并不为托管 COM 组件提供此功能。  过去，加载到进程中的托管 COM 组件使用已加载的运行时版本运行或使用已安装的 .NET Framework 最新版本运行。  如果此版本不与 COM 组件兼容，则该组件会出现故障。  
  
 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 提供了一种并行承载的新方法来确保以下内容：  
  
-   安装新的 .NET Framework 版本不会影响现有的应用程序。  
  
-   应用程序在生成它们所用的 .NET Framework 版本上运行。  它们不使用新的 .NET Framework 版本，除非明确指示它们使用新版本。  但是，对于应用程序来说，转换到使用新的 .NET Framework 版本更加容易。  
  
## 对用户和开发人员的影响  
  
-   **最终用户和系统管理员**。  现在这些用户可以更加放心，当他们安装运行时的新版本（独立安装或与应用程序一起安装）时，不会对他们的计算机有任何影响。  现有的应用程序将如以前一样继续运行。  
  
-   **应用程序开发人员**。  并行承载对应用程序开发人员几乎没有影响。  默认情况下，应用程序总是在生成它们所用的 .NET Framework 版本上运行；这一点没有变化。  但是，开发人员可重写此行为，并指示应用程序在新的 .NET Framework 版本上运行（请参见[方案 2](#scenarios)）。  
  
-   **库开发人员和使用者**。  并行承载不能解决库开发人员面临的兼容性问题。  应用程序直接加载的库（通过直接引用或通过 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 调用）会继续使用其所加载到的 <xref:System.AppDomain> 的运行时。  应针对您想要支持的 .NET Framework 所有版本对您的库进行测试。  如果使用 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 运行时编译应用程序，但包括一个使用较早的运行时生成的库，则该库也将使用 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 运行时。  但是，如果您具有一个使用较早的运行时生成的应用程序和一个使用 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 生成的库，则必须强制应用程序也使用 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]（请参见[方案 3](#scenarios)）。  
  
-   **托管 COM 组件开发人员**。  过去，托管 COM 组件会自动使用计算机上安装的运行时的最新版本运行。  现在您可以在生成 COM 组件所用的运行时版本上执行这些组件。  
  
     如下表所示，使用 .NET Framework 版本 1.1 所生成的组件可以与版本 4 的组件并行运行，但是不能与版本 2.0、3.0 或 3.5 的组件一起运行，因为并行承载不可用于这些版本。  
  
    |.NET Framework 版本|1.1|2.0 \- 3.5|4|  
    |-----------------------|---------|----------------|-------|  
    |1.1|不适用|否|是|  
    |2.0 \- 3.5|否|不适用|是|  
    |4|是|是|不适用|  
  
> [!NOTE]
>  .NET Framework 版本 3.0 和 3.5 是以递增方式构建于版本 2.0 之上的，不需要并行运行。  这些版本本来就是同一版本。  
  
<a name="scenarios"></a>   
## 常见的并行承载方案  
  
-   **方案 1：**使用由较早版本的 .NET Framework 生成的 COM 组件的本机应用程序。  
  
     已安装的 .NET Framework 版本：[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 以及 COM 组件所使用的所有其他的 .NET Framework 版本。  
  
     要执行的操作：此方案中，不执行任何操作。  COM 组件将在其注册的 .NET Framework 版本上运行。  
  
-   **方案 2**：使用 [!INCLUDE[net_v20SP1_short](../../../includes/net-v20sp1-short-md.md)] 生成的托管应用程序，您希望将其与 [!INCLUDE[dnprdnext](../../../includes/dnprdnext-md.md)]一起运行，但如果没有 2.0 版本，则愿意让其在 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 上运行。  
  
     已安装的 .NET Framework 版本：.NET Framework 的早期版本和 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]。  
  
     要执行的操作：在应用程序目录中的[应用程序配置文件](../../../docs/framework/configure-apps/index.md)中，使用[\<startup\> element](../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)和 [\<supportedRuntime\> element](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)并进行如下设置：  
  
    ```  
    <configuration>  
      <startup >  
        <supportedRuntime version="v2.0.50727" />  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
-   **方案 3：**使用由较早版本的 .NET Framework 生成的 COM 组件的本机应用程序，您想要将其与 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 一起运行。  
  
     已安装的 .NET Framework 版本：[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]。  
  
     要执行的操作：在应用程序目录中的应用程序配置文件中，使用 `<startup>` 元素并将其 `useLegacyV2RuntimeActivationPolicy` 特性设置为 `true`，另外还使用 `<supportedRuntime>` 元素并进行如下设置：  
  
    ```  
    <configuration>  
      <startup useLegacyV2RuntimeActivationPolicy="true">  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
## 示例  
 下面的示例演示一个运行托管 COM 组件的非托管 COM 主机（通过使用编译的组件要使用的 .NET Framework 版本）。  
  
 使用 [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)]，请运行以下示例，请编译和注册以下托管 COM 组件。  若要注册该组件，请在 **项目** 菜单上，单击 **属性**，单击 **生成** 选项卡，然后选择 **为 COM 互操作注册** 复选框。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Runtime.InteropServices;  
  
namespace BasicComObject  
{  
    [ComVisible(true), Guid("9C99C4B5-CA54-4c58-8988-49B6811BA53B")]  
    public class MyObject : SimpleObjectModel.IPrintInfo  
    {  
        public MyObject()  
        {  
        }  
        public void PrintInfo()  
        {  
            Console.WriteLine("MyObject was activated in {0} runtime in:\n\tAppDomain {1}:{2}", System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion(), AppDomain.CurrentDomain.Id, AppDomain.CurrentDomain.FriendlyName);  
        }  
    }  
}  
```  
  
 编译下面的非托管 C\+\+ 应用程序（将激活前面的示例创建的 COM 对象）。  
  
```  
#include "stdafx.h"  
#include <string>  
#include <iostream>  
#include <objbase.h>  
#include <string.h>  
#include <process.h>  
  
using namespace std;  
  
int _tmain(int argc, _TCHAR* argv[])  
{  
    char input;  
    CoInitialize(NULL) ;  
    CLSID clsid;  
    HRESULT hr;  
    HRESULT clsidhr = CLSIDFromString(L"{9C99C4B5-CA54-4c58-8988-49B6811BA53B}",&clsid);  
    hr = -1;  
    if (FAILED(clsidhr))  
    {  
        printf("Failed to construct CLSID from String\n");  
    }  
    UUID id = __uuidof(IUnknown);  
    IUnknown * pUnk = NULL;  
    hr = ::CoCreateInstance(clsid,NULL,CLSCTX_INPROC_SERVER,id,(void **) &pUnk);  
    if (FAILED(hr))  
    {  
        printf("Failed CoCreateInstance\n");  
    }else  
    {  
        pUnk->AddRef();  
        printf("Succeeded\n");  
    }  
  
    DISPID dispid;  
    IDispatch* pPrintInfo;  
    pUnk->QueryInterface(IID_IDispatch, (void**)&pPrintInfo);  
    OLECHAR FAR* szMethod[1];  
    szMethod[0]=OLESTR("PrintInfo");   
    hr = pPrintInfo->GetIDsOfNames(IID_NULL,szMethod, 1, LOCALE_SYSTEM_DEFAULT, &dispid);  
    DISPPARAMS dispparams;  
    dispparams.cNamedArgs = 0;  
    dispparams.cArgs = 0;  
    VARIANTARG* pvarg = NULL;  
    EXCEPINFO * pexcepinfo = NULL;  
    WORD wFlags = DISPATCH_METHOD ;  
;  
    LPVARIANT pvRet = NULL;  
    UINT * pnArgErr = NULL;  
    hr = pPrintInfo->Invoke(dispid,IID_NULL, LOCALE_USER_DEFAULT, wFlags,  
        &dispparams, pvRet, pexcepinfo, pnArgErr);  
    printf("Press Enter to exit");  
    scanf_s("%c",&input);  
    CoUninitialize();  
    return 0;  
}  
  
```  
  
## 请参阅  
 [\<startup\> 元素](../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)   
 [\<supportedRuntime\> 元素](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)