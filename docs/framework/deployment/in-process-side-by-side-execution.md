---
title: 进程内并行执行
ms.date: 03/30/2017
helpviewer_keywords:
- in-process side-by-side execution
- side-by-side execution, in-process
ms.assetid: 18019342-a810-4986-8ec2-b933a17c2267
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 89dfe697f49e8144d15586cc9c1075f69d1f3a07
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816054"
---
# <a name="in-process-side-by-side-execution"></a><span data-ttu-id="873ae-102">进程内并行执行</span><span class="sxs-lookup"><span data-stu-id="873ae-102">In-Process Side-by-Side Execution</span></span>
<span data-ttu-id="873ae-103">从.NET Framework 4 开始，可以使用进程内的并行承载在单个进程中运行公共语言运行时 (CLR) 的多个版本。</span><span class="sxs-lookup"><span data-stu-id="873ae-103">Starting with the .NET Framework 4, you can use in-process side-by-side hosting to run multiple versions of the common language runtime (CLR) in a single process.</span></span> <span data-ttu-id="873ae-104">默认情况下，托管 COM 组件使用其生成所用的 .NET Framework 版本运行，而不考虑为进程加载的 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="873ae-104">By default, managed COM components run with the .NET Framework version they were built with, regardless of the .NET Framework version that is loaded for the process.</span></span>  
  
## <a name="background"></a><span data-ttu-id="873ae-105">背景</span><span class="sxs-lookup"><span data-stu-id="873ae-105">Background</span></span>  
 <span data-ttu-id="873ae-106">.NET Framework 现在始终为托管代码应用程序提供并行承载，但在 .NET Framework 4 之前，它并不为托管 COM 组件提供此功能。</span><span class="sxs-lookup"><span data-stu-id="873ae-106">The .NET Framework has always provided side-by-side hosting for managed code applications, but before the .NET Framework 4, it did not provide that functionality for managed COM components.</span></span> <span data-ttu-id="873ae-107">过去，加载到进程中的托管 COM 组件使用已加载的运行时版本运行或使用已安装的 .NET Framework 最新版本运行。</span><span class="sxs-lookup"><span data-stu-id="873ae-107">In the past, managed COM components that were loaded into a process ran either with the version of the runtime that was already loaded or with the latest installed version of the .NET Framework.</span></span> <span data-ttu-id="873ae-108">如果此版本不与 COM 组件兼容，则该组件会出现故障。</span><span class="sxs-lookup"><span data-stu-id="873ae-108">If this version was not compatible with the COM component, the component would fail.</span></span>  
  
 <span data-ttu-id="873ae-109">.NET Framework 4 提供了一种并行承载的新方法来确保以下内容：</span><span class="sxs-lookup"><span data-stu-id="873ae-109">The .NET Framework 4 provides a new approach to side-by-side hosting that ensures the following:</span></span>  
  
- <span data-ttu-id="873ae-110">安装新版 .NET Framework 不会影响现有的应用程序。</span><span class="sxs-lookup"><span data-stu-id="873ae-110">Installing a new version of the .NET Framework has no effect on existing applications.</span></span>  
  
- <span data-ttu-id="873ae-111">应用程序在生成它们所用的 .NET Framework 版本上运行。</span><span class="sxs-lookup"><span data-stu-id="873ae-111">Applications run against the version of the .NET Framework that they were built with.</span></span> <span data-ttu-id="873ae-112">应用程序不使用新版 .NET Framework，除非明确指示其使用新版本。</span><span class="sxs-lookup"><span data-stu-id="873ae-112">They do not use the new version of the .NET Framework unless expressly directed to do so.</span></span> <span data-ttu-id="873ae-113">但是，对应用程序来说，转为使用新版 .NET Framework 更加容易。</span><span class="sxs-lookup"><span data-stu-id="873ae-113">However, it is easier for applications to transition to using a new version of the .NET Framework.</span></span>  
  
## <a name="effects-on-users-and-developers"></a><span data-ttu-id="873ae-114">对用户和开发人员的影响</span><span class="sxs-lookup"><span data-stu-id="873ae-114">Effects on Users and Developers</span></span>  
  
- <span data-ttu-id="873ae-115">最终用户和系统管理员  。</span><span class="sxs-lookup"><span data-stu-id="873ae-115">**End users and system administrators**.</span></span> <span data-ttu-id="873ae-116">现在这些用户可以更加放心，因为安装运行时的新版本（独立安装或与应用程序一起安装）时，不会对他们的计算机产生任何影响。</span><span class="sxs-lookup"><span data-stu-id="873ae-116">These users can now have greater confidence that when they install a new version of the runtime, either independently or with an application, it will have no impact on their computers.</span></span> <span data-ttu-id="873ae-117">现有应用程序如以前一样继续运行。</span><span class="sxs-lookup"><span data-stu-id="873ae-117">Existing applications will continue to run as they did before.</span></span>  
  
- <span data-ttu-id="873ae-118">应用程序开发人员  。</span><span class="sxs-lookup"><span data-stu-id="873ae-118">**Application developers**.</span></span> <span data-ttu-id="873ae-119">并行承载对应用程序开发人员几乎没有影响。</span><span class="sxs-lookup"><span data-stu-id="873ae-119">Side-by-side hosting has almost no effect on application developers.</span></span> <span data-ttu-id="873ae-120">默认情况下，应用程序总是在生成它们所用的 .NET Framework 版本上运行；这一点没有变化。</span><span class="sxs-lookup"><span data-stu-id="873ae-120">By default, applications always run against the version of the .NET Framework they were built on; this has not changed.</span></span> <span data-ttu-id="873ae-121">但是，开发人员可替代此行为，并指示应用程序在新版 .NET Framework 上运行（请参阅[方案 2](#scenarios)）。</span><span class="sxs-lookup"><span data-stu-id="873ae-121">However, developers can override this behavior and direct the application to run under a newer version of the .NET Framework (see [scenario 2](#scenarios)).</span></span>  
  
- <span data-ttu-id="873ae-122">库开发人员和使用者  。</span><span class="sxs-lookup"><span data-stu-id="873ae-122">**Library developers and consumers**.</span></span> <span data-ttu-id="873ae-123">并行承载不能解决库开发人员面临的兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="873ae-123">Side-by-side hosting does not solve the compatibility problems that library developers face.</span></span> <span data-ttu-id="873ae-124">应用程序直接加载的库（通过直接引用或通过 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 调用）会继续使用其加载到的 <xref:System.AppDomain> 运行时。</span><span class="sxs-lookup"><span data-stu-id="873ae-124">A library that is directly loaded by an application -- either through a direct reference or through an <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> call -- continues to use the runtime of the <xref:System.AppDomain> it is loaded into.</span></span> <span data-ttu-id="873ae-125">应针对要支持的 .NET Framework 所有版本对库进行测试。</span><span class="sxs-lookup"><span data-stu-id="873ae-125">You should test your libraries against all versions of the .NET Framework that you want to support.</span></span> <span data-ttu-id="873ae-126">如果使用 .NET Framework 4 运行时编译应用程序，但包括一个使用较早运行时生成的库，则该库也将使用 .NET Framework 4 运行时。</span><span class="sxs-lookup"><span data-stu-id="873ae-126">If an application is compiled using the .NET Framework 4 runtime but includes a library that was built using an earlier runtime, that library will use the .NET Framework 4 runtime as well.</span></span> <span data-ttu-id="873ae-127">但是，如果有一个使用较早运行时生成的应用程序和一个使用 .NET Framework 4 生成的库，则必须强制应用程序也使用 .NET Framework 4（请参阅[方案 3](#scenarios)）。</span><span class="sxs-lookup"><span data-stu-id="873ae-127">However, if you have an application that was built using an earlier runtime and a library that was built using the .NET Framework 4, you must force your application to also use the .NET Framework 4 (see [scenario 3](#scenarios)).</span></span>  
  
- <span data-ttu-id="873ae-128">托管 COM 组件开发人员  。</span><span class="sxs-lookup"><span data-stu-id="873ae-128">**Managed COM component developers**.</span></span> <span data-ttu-id="873ae-129">过去，托管 COM 组件会自动使用计算机上安装的运行时最新版本运行。</span><span class="sxs-lookup"><span data-stu-id="873ae-129">In the past, managed COM components automatically ran using the latest version of the runtime installed on the computer.</span></span> <span data-ttu-id="873ae-130">现在，可在生成 COM 组件所用的运行时版本上执行这些组件。</span><span class="sxs-lookup"><span data-stu-id="873ae-130">You can now execute COM components against the version of the runtime they were built with.</span></span>  
  
     <span data-ttu-id="873ae-131">如下表所示，使用 .NET Framework 版本 1.1 生成的组件可与版本 4 的组件并行运行，但不能与版本 2.0、3.0 或 3.5 的组件一起运行，因为并行承载不可用于这些版本。</span><span class="sxs-lookup"><span data-stu-id="873ae-131">As shown by the following table, components that were built with the .NET Framework version 1.1 can run side by side with version 4 components, but they cannot run with version 2.0, 3.0, or 3.5 components, because side-by-side hosting is not available for those versions.</span></span>  
  
    |<span data-ttu-id="873ae-132">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="873ae-132">.NET Framework version</span></span>|<span data-ttu-id="873ae-133">1.1</span><span class="sxs-lookup"><span data-stu-id="873ae-133">1.1</span></span>|<span data-ttu-id="873ae-134">2.0 - 3.5</span><span class="sxs-lookup"><span data-stu-id="873ae-134">2.0 - 3.5</span></span>|<span data-ttu-id="873ae-135">4</span><span class="sxs-lookup"><span data-stu-id="873ae-135">4</span></span>|  
    |----------------------------|---------|----------------|-------|  
    |<span data-ttu-id="873ae-136">1.1</span><span class="sxs-lookup"><span data-stu-id="873ae-136">1.1</span></span>|<span data-ttu-id="873ae-137">不适用</span><span class="sxs-lookup"><span data-stu-id="873ae-137">Not applicable</span></span>|<span data-ttu-id="873ae-138">No</span><span class="sxs-lookup"><span data-stu-id="873ae-138">No</span></span>|<span data-ttu-id="873ae-139">是</span><span class="sxs-lookup"><span data-stu-id="873ae-139">Yes</span></span>|  
    |<span data-ttu-id="873ae-140">2.0 - 3.5</span><span class="sxs-lookup"><span data-stu-id="873ae-140">2.0 - 3.5</span></span>|<span data-ttu-id="873ae-141">No</span><span class="sxs-lookup"><span data-stu-id="873ae-141">No</span></span>|<span data-ttu-id="873ae-142">不适用</span><span class="sxs-lookup"><span data-stu-id="873ae-142">Not applicable</span></span>|<span data-ttu-id="873ae-143">是</span><span class="sxs-lookup"><span data-stu-id="873ae-143">Yes</span></span>|  
    |<span data-ttu-id="873ae-144">4</span><span class="sxs-lookup"><span data-stu-id="873ae-144">4</span></span>|<span data-ttu-id="873ae-145">是</span><span class="sxs-lookup"><span data-stu-id="873ae-145">Yes</span></span>|<span data-ttu-id="873ae-146">是</span><span class="sxs-lookup"><span data-stu-id="873ae-146">Yes</span></span>|<span data-ttu-id="873ae-147">不适用</span><span class="sxs-lookup"><span data-stu-id="873ae-147">Not applicable</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="873ae-148">.NET Framework 版本 3.0 和 3.5 是以版本 2.0 为基础逐步生成的，不需要并行运行。</span><span class="sxs-lookup"><span data-stu-id="873ae-148">.NET Framework versions 3.0 and 3.5 are built incrementally on version 2.0, and do not need to run side by side.</span></span> <span data-ttu-id="873ae-149">这些版本本来就是同一版本。</span><span class="sxs-lookup"><span data-stu-id="873ae-149">These are inherently the same version.</span></span>  
  
<a name="scenarios"></a>   
## <a name="common-side-by-side-hosting-scenarios"></a><span data-ttu-id="873ae-150">常见的并行承载方案</span><span class="sxs-lookup"><span data-stu-id="873ae-150">Common Side-by-Side Hosting Scenarios</span></span>  
  
- <span data-ttu-id="873ae-151">**方案 1：** 使用由旧版 .NET Framework 生成的 COM 组件的本机应用程序。</span><span class="sxs-lookup"><span data-stu-id="873ae-151">**Scenario 1:** Native application that uses COM components built with earlier versions of the .NET Framework.</span></span>  
  
     <span data-ttu-id="873ae-152">已安装的 .NET Framework 版本：.NET Framework 4 和 COM 组件使用的所有其他 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="873ae-152">.NET Framework versions installed: The .NET Framework 4 and all other versions of the .NET Framework used by the COM components.</span></span>  
  
     <span data-ttu-id="873ae-153">要执行的操作：此方案中，不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="873ae-153">What to do: In this scenario, do nothing.</span></span> <span data-ttu-id="873ae-154">COM 组件将在其注册的 .NET Framework 版本上运行。</span><span class="sxs-lookup"><span data-stu-id="873ae-154">The COM components will run with the version of the .NET Framework they were registered with.</span></span>  
  
- <span data-ttu-id="873ae-155">**方案 2**：托管应用程序使用.NET Framework 2.0 SP1，你想要使用运行生成[!INCLUDE[dnprdnext](../../../includes/dnprdnext-md.md)]，但希望在.NET Framework 4 上运行，如果 2.0 版不存在。</span><span class="sxs-lookup"><span data-stu-id="873ae-155">**Scenario 2**: Managed application built with the .NET Framework 2.0 SP1 that you would prefer to run with the [!INCLUDE[dnprdnext](../../../includes/dnprdnext-md.md)], but are willing to run on the .NET Framework 4 if version 2.0 is not present.</span></span>  
  
     <span data-ttu-id="873ae-156">已安装的 .NET Framework 版本：早期版本的 .NET Framework 和 .NET Framework 4。</span><span class="sxs-lookup"><span data-stu-id="873ae-156">.NET Framework versions installed: An earlier version of the .NET Framework and the .NET Framework 4.</span></span>  
  
     <span data-ttu-id="873ae-157">要执行的操作：在应用程序目录的[应用程序配置文件](../../../docs/framework/configure-apps/index.md)中，使用 [\<startup> 元素](../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)和 [\<supportedRuntime> 元素](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)进行如下设置：</span><span class="sxs-lookup"><span data-stu-id="873ae-157">What to do: In the [application configuration file](../../../docs/framework/configure-apps/index.md) in the application directory, use the [\<startup> element](../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) and the [\<supportedRuntime> element](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) set as follows:</span></span>  
  
    ```xml  
    <configuration>  
      <startup >  
        <supportedRuntime version="v2.0.50727" />  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
- <span data-ttu-id="873ae-158">**方案 3：** 使用由旧版 .NET Framework 生成的 COM 组件的本机应用程序，并将其与 .NET Framework 4 一起运行。</span><span class="sxs-lookup"><span data-stu-id="873ae-158">**Scenario 3:** Native application that uses COM components built with earlier versions of the .NET Framework that you want to run with the .NET Framework 4.</span></span>  
  
     <span data-ttu-id="873ae-159">已安装的 .NET Framework 版本：.NET Framework 4。</span><span class="sxs-lookup"><span data-stu-id="873ae-159">.NET Framework versions installed: The .NET Framework 4.</span></span>  
  
     <span data-ttu-id="873ae-160">要执行的操作：在应用程序目录的应用程序配置文件中，使用 `<startup>` 元素并将其 `useLegacyV2RuntimeActivationPolicy` 属性设置为 `true`，另外还使用 `<supportedRuntime>` 元素进行如下设置：</span><span class="sxs-lookup"><span data-stu-id="873ae-160">What to do: In the application configuration file in the application directory, use the `<startup>` element with the `useLegacyV2RuntimeActivationPolicy` attribute set to `true` and the `<supportedRuntime>` element set as follows:</span></span>  
  
    ```xml  
    <configuration>  
      <startup useLegacyV2RuntimeActivationPolicy="true">  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
## <a name="example"></a><span data-ttu-id="873ae-161">示例</span><span class="sxs-lookup"><span data-stu-id="873ae-161">Example</span></span>  
 <span data-ttu-id="873ae-162">下例演示通过使用编译的组件要使用的 .NET Framework 版本运行托管 COM 组件的非托管 COM 主机。</span><span class="sxs-lookup"><span data-stu-id="873ae-162">The following example demonstrates an unmanaged COM host that is running a managed COM component by using the version of the .NET Framework that the component was compiled to use.</span></span>  
  
 <span data-ttu-id="873ae-163">若要运行下面的示例，请编译并注册以下托管的 COM 组件使用.NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="873ae-163">To run the following example, compile and register the following managed COM component using the .NET Framework 3.5.</span></span> <span data-ttu-id="873ae-164">若要注册该组件，请在“项目”菜单上，依次单击“属性”、“生成”选项卡，然后选中“注册 COM 互操作”复选框     。</span><span class="sxs-lookup"><span data-stu-id="873ae-164">To register the component, on the **Project** menu, click **Properties**, click the **Build** tab, and then select the **Register for COM interop** check box.</span></span>  
  
```csharp
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
  
 <span data-ttu-id="873ae-165">编译以下非托管 C++ 应用程序，这将激活上例创建的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="873ae-165">Compile the following unmanaged C++ application, which activates the COM object that is created by the previous example.</span></span>  
  
```cpp
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
  
## <a name="see-also"></a><span data-ttu-id="873ae-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="873ae-166">See also</span></span>

- [<span data-ttu-id="873ae-167">\<startup> 元素</span><span class="sxs-lookup"><span data-stu-id="873ae-167">\<startup> Element</span></span>](../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
- [<span data-ttu-id="873ae-168">\<supportedRuntime> 元素</span><span class="sxs-lookup"><span data-stu-id="873ae-168">\<supportedRuntime> Element</span></span>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)
