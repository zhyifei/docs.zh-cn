---
title: "COM+ 服务模块配置工具 (ComSvcConfig.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, COM+ integration
- WCF, COM+ integration
ms.assetid: 7717c6c2-85fc-418b-a8ed-bad8e61cec5c
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3f812beea611633fe1fa47ced5db46c462443f28
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="com-service-model-configuration-tool-comsvcconfigexe"></a><span data-ttu-id="48f07-102">COM+ 服务模块配置工具 (ComSvcConfig.exe)</span><span class="sxs-lookup"><span data-stu-id="48f07-102">COM+ Service Model Configuration Tool (ComSvcConfig.exe)</span></span>
<span data-ttu-id="48f07-103">利用 COM+ 服务模块配置命令行工具 (ComSvcConfig.exe)，你可以配置要作为 Web 服务公开的 COM+ 接口。</span><span class="sxs-lookup"><span data-stu-id="48f07-103">The COM+ Service Model Configuration command-line tool (ComSvcConfig.exe) enables you to configure COM+ interfaces to be exposed as Web services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48f07-104">语法</span><span class="sxs-lookup"><span data-stu-id="48f07-104">Syntax</span></span>  
  
```  
ComSvcConfig.exe /install | /uninstall | /list [/application:<ApplicationID | ApplicationName>] [/contract:<ClassID | ProgID | *,InterfaceID | InterfaceName | *>] [/hosting:<complus | was>] [/webSite:<WebsiteName>] [/webDirectory:<WebDirectoryName>] [/mex] [/id] [/nologo] [/verbose] [/help] [/partial]  
```  
  
## <a name="remarks"></a><span data-ttu-id="48f07-105">备注</span><span class="sxs-lookup"><span data-stu-id="48f07-105">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48f07-106">您必须是本地计算机上的管理员才能使用 ComSvcConfig.exe。</span><span class="sxs-lookup"><span data-stu-id="48f07-106">You must be an administrator on the local computer to use ComSvcConfig.exe.</span></span>  
  
 <span data-ttu-id="48f07-107">可在以下位置中找到此工具</span><span class="sxs-lookup"><span data-stu-id="48f07-107">The tool can be found in the following location</span></span>  
  
 <span data-ttu-id="48f07-108">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\\</span><span class="sxs-lookup"><span data-stu-id="48f07-108">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\\</span></span>  
  
 <span data-ttu-id="48f07-109">有关 ComSvcConfig.exe 的详细信息，请参阅[如何： 使用 COM + 服务模型配置工具](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="48f07-109">For more information about ComSvcConfig.exe, see [How to: Use the COM+ Service Model Configuration Tool](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md).</span></span>  
  
 <span data-ttu-id="48f07-110">下表介绍可用于 ComSvcConfig.exe 的模式。</span><span class="sxs-lookup"><span data-stu-id="48f07-110">The following table describes the modes that can be used with ComSvcConfig.exe.</span></span>  
  
|<span data-ttu-id="48f07-111">选项</span><span class="sxs-lookup"><span data-stu-id="48f07-111">Option</span></span>|<span data-ttu-id="48f07-112">描述</span><span class="sxs-lookup"><span data-stu-id="48f07-112">Description</span></span>|  
|------------|-----------------|  
|`install`|<span data-ttu-id="48f07-113">为服务模块集成安装 COM+ 接口配置。</span><span class="sxs-lookup"><span data-stu-id="48f07-113">Installs a configuration for a COM+ interface for Service Model integration.</span></span><br /><br /> <span data-ttu-id="48f07-114">缩写形式：`/i`。</span><span class="sxs-lookup"><span data-stu-id="48f07-114">Short form `/i`.</span></span>|  
|`uninstall`|<span data-ttu-id="48f07-115">从服务模块集成中卸载 COM+ 接口配置。</span><span class="sxs-lookup"><span data-stu-id="48f07-115">Uninstalls a configuration for a COM+ interface from Service Model integration.</span></span><br /><br /> <span data-ttu-id="48f07-116">缩写形式：`/u`。</span><span class="sxs-lookup"><span data-stu-id="48f07-116">Short form `/u`.</span></span>|  
|`list`|<span data-ttu-id="48f07-117">列出有关 COM+ 应用程序和组件的信息，这些应用程序和组件具有为服务模块集成配置的接口。</span><span class="sxs-lookup"><span data-stu-id="48f07-117">Lists information about COM+ applications and components that have interfaces that are configured for Service Model integration.</span></span><br /><br /> <span data-ttu-id="48f07-118">缩写形式：`/l`。</span><span class="sxs-lookup"><span data-stu-id="48f07-118">Short form `/l`.</span></span>|  
  
 <span data-ttu-id="48f07-119">下表介绍可用于 ComSvcConfig.exe 的标志。</span><span class="sxs-lookup"><span data-stu-id="48f07-119">The following table describes the flags that can be used with ComSvcConfig.exe.</span></span>  
  
|<span data-ttu-id="48f07-120">选项</span><span class="sxs-lookup"><span data-stu-id="48f07-120">Option</span></span>|<span data-ttu-id="48f07-121">描述</span><span class="sxs-lookup"><span data-stu-id="48f07-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="48f07-122">`/application:`\< *ApplicationID* &#124;*ApplicationName*\></span><span class="sxs-lookup"><span data-stu-id="48f07-122">`/application:` \<*ApplicationID* &#124; *ApplicationName*\></span></span>|<span data-ttu-id="48f07-123">指定要配置的 COM+ 应用程序。</span><span class="sxs-lookup"><span data-stu-id="48f07-123">Specifies the COM+ application to configure.</span></span><br /><br /> <span data-ttu-id="48f07-124">缩写形式：`/a`。</span><span class="sxs-lookup"><span data-stu-id="48f07-124">Short form `/a`.</span></span>|  
|<span data-ttu-id="48f07-125">`/contract:`\< *ClassID* &#124;*ProgID* &#124;\*，*InterfaceID* &#124;*InterfaceName* &#124;\*\></span><span class="sxs-lookup"><span data-stu-id="48f07-125">`/contract:` \<*ClassID*  &#124; *ProgID*  &#124; \*,*InterfaceID* &#124; *InterfaceName* &#124; \*\></span></span>|<span data-ttu-id="48f07-126">指定将作为服务协定配置的 COM+ 组件和接口。</span><span class="sxs-lookup"><span data-stu-id="48f07-126">Specifies the COM+ component and interface that will be configured as the contract for the service.</span></span><br /><br /> <span data-ttu-id="48f07-127">缩写形式：`/c`。</span><span class="sxs-lookup"><span data-stu-id="48f07-127">Short form `/c`.</span></span><br /><br /> <span data-ttu-id="48f07-128">尽管通配符字符 (\*) 时您指定的组件和接口的名称，可以使用我们建议，你并不使用它，因为可能会公开您不打算到的接口。</span><span class="sxs-lookup"><span data-stu-id="48f07-128">While the wildcard character (\*) can be used when you specify the component and interface names, we recommend that you do not use it, because you might expose interfaces that you did not intend to.</span></span>|  
|<span data-ttu-id="48f07-129">`/hosting:`\< *complus* &#124;*已*\></span><span class="sxs-lookup"><span data-stu-id="48f07-129">`/hosting:` \<*complus*  &#124; *was*\></span></span>|<span data-ttu-id="48f07-130">指定是使用 COM+ 宿主模式还是 Web 宿主模式。</span><span class="sxs-lookup"><span data-stu-id="48f07-130">Specifies whether to use the COM+ hosting mode or the Web hosting mode.</span></span><br /><br /> <span data-ttu-id="48f07-131">缩写形式：`/h`。</span><span class="sxs-lookup"><span data-stu-id="48f07-131">Short form `/h`.</span></span><br /><br /> <span data-ttu-id="48f07-132">如果使用 COM+ 宿主模式，将需要显式激活 COM+ 应用程序。</span><span class="sxs-lookup"><span data-stu-id="48f07-132">Using the COM+ hosting mode requires explicit activation of the COM+ application.</span></span> <span data-ttu-id="48f07-133">如果使用 Web 宿主模式，将能够按照需要自动激活 COM+ 应用程序。</span><span class="sxs-lookup"><span data-stu-id="48f07-133">Using the Web hosting mode allows the COM+ application to be automatically activated as required.</span></span> <span data-ttu-id="48f07-134">如果 COM+ 应用程序是库应用程序，它将在 Internet 信息服务 (IIS) 进程中运行。</span><span class="sxs-lookup"><span data-stu-id="48f07-134">If the COM+ application is a library application, it runs in the Internet Information Services (IIS) process.</span></span> <span data-ttu-id="48f07-135">如果 COM+ 应用程序是服务器应用程序，它将在 Dllhost.exe 进程中运行。</span><span class="sxs-lookup"><span data-stu-id="48f07-135">If the COM+ application is a server application, it runs in the Dllhost.exe process.</span></span>|  
|<span data-ttu-id="48f07-136">`/webSite:`\< *WebsiteName*\></span><span class="sxs-lookup"><span data-stu-id="48f07-136">`/webSite:` \<*WebsiteName*\></span></span>|<span data-ttu-id="48f07-137">指定使用 Web 宿主模式时（请参见 `/hosting` 标志）用于宿主的网站。</span><span class="sxs-lookup"><span data-stu-id="48f07-137">Specifies the Web site for hosting when Web hosting mode is used (see the `/hosting` flag).</span></span><br /><br /> <span data-ttu-id="48f07-138">缩写形式：`/w`。</span><span class="sxs-lookup"><span data-stu-id="48f07-138">Short form `/w`.</span></span><br /><br /> <span data-ttu-id="48f07-139">如果未指定网站，则使用默认网站。</span><span class="sxs-lookup"><span data-stu-id="48f07-139">If no Web site is specified, the default Web site is used.</span></span>|  
|<span data-ttu-id="48f07-140">`/webDirectory:`\< *WebDirectoryName*\></span><span class="sxs-lookup"><span data-stu-id="48f07-140">`/webDirectory:` \<*WebDirectoryName*\></span></span>|<span data-ttu-id="48f07-141">指定在使用 Web 宿主时（请参见 `/hosting` 标志）用于宿主的虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="48f07-141">Specifies the virtual directory for hosting when Web hosting is used (see the `/hosting` flag).</span></span><br /><br /> <span data-ttu-id="48f07-142">缩写形式：`/d`。</span><span class="sxs-lookup"><span data-stu-id="48f07-142">Short form `/d`.</span></span>|  
|`/mex`|<span data-ttu-id="48f07-143">将元数据交换 (MEX) 服务终结点添加到默认服务配置，以支持要从服务中检索协定定义的客户端。</span><span class="sxs-lookup"><span data-stu-id="48f07-143">Adds a Metadata Exchange (MEX) service endpoint to the default service configuration to support clients that want to retrieve a contract definition from the service.</span></span><br /><br /> <span data-ttu-id="48f07-144">缩写形式：`/x`。</span><span class="sxs-lookup"><span data-stu-id="48f07-144">Short form `/x`.</span></span>|  
|`/id`|<span data-ttu-id="48f07-145">以 ID 的形式显示应用程序、组件和接口信息。</span><span class="sxs-lookup"><span data-stu-id="48f07-145">Displays the application, component, and interface information as IDs.</span></span><br /><br /> <span data-ttu-id="48f07-146">缩写形式：`/k`。</span><span class="sxs-lookup"><span data-stu-id="48f07-146">Short form `/k`.</span></span>|  
|`/nologo`|<span data-ttu-id="48f07-147">防止 ComSvcConfig.exe 显示其徽标。</span><span class="sxs-lookup"><span data-stu-id="48f07-147">Prevents ComSvcConfig.exe from displaying its logo.</span></span><br /><br /> <span data-ttu-id="48f07-148">缩写形式：`/n`。</span><span class="sxs-lookup"><span data-stu-id="48f07-148">Short form `/n`.</span></span>|  
|`/verbose`|<span data-ttu-id="48f07-149">除遇到的任何错误之外还输出所有警告或信息性文本。</span><span class="sxs-lookup"><span data-stu-id="48f07-149">Outputs all warnings or informational text in addition to any errors encountered.</span></span><br /><br /> <span data-ttu-id="48f07-150">缩写形式：`/v`。</span><span class="sxs-lookup"><span data-stu-id="48f07-150">Short form `/v`.</span></span>|  
|`/help`|<span data-ttu-id="48f07-151">显示用法消息。</span><span class="sxs-lookup"><span data-stu-id="48f07-151">Displays the usage message.</span></span><br /><br /> <span data-ttu-id="48f07-152">缩写形式：`/?`。</span><span class="sxs-lookup"><span data-stu-id="48f07-152">Short form `/?`.</span></span>|  
|`/partial`|<span data-ttu-id="48f07-153">在指定的接口包含一个或多个可公开的方法签名时生成一个服务配置。</span><span class="sxs-lookup"><span data-stu-id="48f07-153">Generates a service configuration when the specified interface includes one or more method signatures that can be exposed.</span></span> <span data-ttu-id="48f07-154">在服务初始化时，兼容的方法显示为服务协定上的操作，而非兼容方法将被忽略且不显示在服务协定中。</span><span class="sxs-lookup"><span data-stu-id="48f07-154">At service initialization time, compatible methods appear as operations on the service contract, and non-compatible methods are ignored and absent from the service contract.</span></span><br /><br /> <span data-ttu-id="48f07-155">如果缺少此标志，工具将不会在指定接口包含一个或多个不兼容方法时生成服务配置。</span><span class="sxs-lookup"><span data-stu-id="48f07-155">If this flag is missing, the tool will not generate a service configuration when the specified interface includes one or more incompatible methods.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="48f07-156">示例</span><span class="sxs-lookup"><span data-stu-id="48f07-156">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="48f07-157">描述</span><span class="sxs-lookup"><span data-stu-id="48f07-157">Description</span></span>  
 <span data-ttu-id="48f07-158">下面的示例使用 COM+ 宿主模式将 `IFinances` 组件（来自 OnlineStore COM+ 应用程序）的 `ItemOrders.IFinancial` 接口添加到作为 Web 服务公开的接口集中。</span><span class="sxs-lookup"><span data-stu-id="48f07-158">The following example adds the `IFinances` interface of the `ItemOrders.IFinancial` component (from the OnlineStore COM+ application) to the set of interfaces that are exposed as Web services, using the COM+ hosting mode.</span></span> <span data-ttu-id="48f07-159">除遇到的任何错误外还将输出所有警告。</span><span class="sxs-lookup"><span data-stu-id="48f07-159">All warnings will be output in addition to any errors encountered.</span></span>  
  
### <a name="code"></a><span data-ttu-id="48f07-160">代码</span><span class="sxs-lookup"><span data-stu-id="48f07-160">Code</span></span>  
  
```  
ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose  
```  
  
### <a name="description"></a><span data-ttu-id="48f07-161">描述</span><span class="sxs-lookup"><span data-stu-id="48f07-161">Description</span></span>  
 <span data-ttu-id="48f07-162">下面的示例使用 Web 宿主模式将 `IStockLevels` 组件（来自 OnlineWarehouse COM+ 应用程序）的 `ItemInventory.Warehouse` 接口添加到作为 Web 服务公开的接口集中。</span><span class="sxs-lookup"><span data-stu-id="48f07-162">The following example adds the `IStockLevels` interface of the `ItemInventory.Warehouse` component (from the OnlineWarehouse COM+ application) to the set of interfaces that are exposed as Web services, using the Web hosting mode.</span></span> <span data-ttu-id="48f07-163">Web 服务是宿主在 IIS 的 OnlineWarehouse 虚拟目录中的网站。</span><span class="sxs-lookup"><span data-stu-id="48f07-163">The Web service is Web hosted in the OnlineWarehouse virtual directory of IIS.</span></span>  
  
### <a name="code"></a><span data-ttu-id="48f07-164">代码</span><span class="sxs-lookup"><span data-stu-id="48f07-164">Code</span></span>  
  
```  
ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse  
```  
  
### <a name="description"></a><span data-ttu-id="48f07-165">描述</span><span class="sxs-lookup"><span data-stu-id="48f07-165">Description</span></span>  
 <span data-ttu-id="48f07-166">下面的示例从作为 Web 服务公开的接口集中移除 `IFinances` 组件（来自 OnlineStore COM+ 应用程序）的 `ItemOrders.Financial` 接口。</span><span class="sxs-lookup"><span data-stu-id="48f07-166">The following example removes the `IFinances` interface of the `ItemOrders.Financial` component (from the OnlineStore COM+ application) from the set of interfaces that are exposed as Web services.</span></span>  
  
### <a name="code"></a><span data-ttu-id="48f07-167">代码</span><span class="sxs-lookup"><span data-stu-id="48f07-167">Code</span></span>  
  
```  
ComSvcConfig.exe /uninstall /application:OnlineStore /interface:ItemOrders.Financial,IFinances /hosting:complus  
```  
  
### <a name="description"></a><span data-ttu-id="48f07-168">描述</span><span class="sxs-lookup"><span data-stu-id="48f07-168">Description</span></span>  
 <span data-ttu-id="48f07-169">下面的示例为本地计算机上的 OnlineStore COM+ 应用程序列出当前公开的 COM+ 宿主接口，以及相应的地址和绑定详细信息。</span><span class="sxs-lookup"><span data-stu-id="48f07-169">The following example lists currently exposed COM+ hosted interfaces, along with the corresponding address and binding details, for the OnlineStore COM+ application on the local machine.</span></span>  
  
### <a name="code"></a><span data-ttu-id="48f07-170">代码</span><span class="sxs-lookup"><span data-stu-id="48f07-170">Code</span></span>  
  
```  
ComSvcConfig.exe /list /application:OnlineStore /hosting:complus  
```  
  
## <a name="see-also"></a><span data-ttu-id="48f07-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48f07-171">See Also</span></span>  
 [<span data-ttu-id="48f07-172">如何： 使用 COM + 服务模型配置工具</span><span class="sxs-lookup"><span data-stu-id="48f07-172">How to: Use the COM+ Service Model Configuration Tool</span></span>](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)
