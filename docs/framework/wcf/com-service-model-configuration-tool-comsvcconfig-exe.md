---
title: COM+ 服务模块配置工具 (ComSvcConfig.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM+ integration
- WCF, COM+ integration
ms.assetid: 7717c6c2-85fc-418b-a8ed-bad8e61cec5c
ms.openlocfilehash: 6d0967355e64640e0fd5c81f04a5bf4f33c7b3f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608835"
---
# <a name="com-service-model-configuration-tool-comsvcconfigexe"></a><span data-ttu-id="18cb0-102">COM+ 服务模块配置工具 (ComSvcConfig.exe)</span><span class="sxs-lookup"><span data-stu-id="18cb0-102">COM+ Service Model Configuration Tool (ComSvcConfig.exe)</span></span>
<span data-ttu-id="18cb0-103">利用 COM+ 服务模块配置命令行工具 (ComSvcConfig.exe)，你可以配置要作为 Web 服务公开的 COM+ 接口。</span><span class="sxs-lookup"><span data-stu-id="18cb0-103">The COM+ Service Model Configuration command-line tool (ComSvcConfig.exe) enables you to configure COM+ interfaces to be exposed as Web services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18cb0-104">语法</span><span class="sxs-lookup"><span data-stu-id="18cb0-104">Syntax</span></span>  
  
```  
ComSvcConfig.exe /install | /uninstall | /list [/application:<ApplicationID | ApplicationName>] [/contract:<ClassID | ProgID | *,InterfaceID | InterfaceName | *>] [/hosting:<complus | was>] [/webSite:<WebsiteName>] [/webDirectory:<WebDirectoryName>] [/mex] [/id] [/nologo] [/verbose] [/help] [/partial]  
```  
  
## <a name="remarks"></a><span data-ttu-id="18cb0-105">备注</span><span class="sxs-lookup"><span data-stu-id="18cb0-105">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18cb0-106">您必须是本地计算机上的管理员才能使用 ComSvcConfig.exe。</span><span class="sxs-lookup"><span data-stu-id="18cb0-106">You must be an administrator on the local computer to use ComSvcConfig.exe.</span></span>  
  
 <span data-ttu-id="18cb0-107">可在以下位置中找到此工具</span><span class="sxs-lookup"><span data-stu-id="18cb0-107">The tool can be found in the following location</span></span>  
  
 <span data-ttu-id="18cb0-108">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\\</span><span class="sxs-lookup"><span data-stu-id="18cb0-108">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\\</span></span>  
  
 <span data-ttu-id="18cb0-109">有关 ComSvcConfig.exe 的更多信息，请参阅[如何：使用 COM + 服务模型配置工具](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="18cb0-109">For more information about ComSvcConfig.exe, see [How to: Use the COM+ Service Model Configuration Tool](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md).</span></span>  
  
 <span data-ttu-id="18cb0-110">下表介绍可用于 ComSvcConfig.exe 的模式。</span><span class="sxs-lookup"><span data-stu-id="18cb0-110">The following table describes the modes that can be used with ComSvcConfig.exe.</span></span>  
  
|<span data-ttu-id="18cb0-111">选项</span><span class="sxs-lookup"><span data-stu-id="18cb0-111">Option</span></span>|<span data-ttu-id="18cb0-112">描述</span><span class="sxs-lookup"><span data-stu-id="18cb0-112">Description</span></span>|  
|------------|-----------------|  
|`install`|<span data-ttu-id="18cb0-113">为服务模块集成安装 COM+ 接口配置。</span><span class="sxs-lookup"><span data-stu-id="18cb0-113">Installs a configuration for a COM+ interface for Service Model integration.</span></span><br /><br /> <span data-ttu-id="18cb0-114">缩写形式：`/i`。</span><span class="sxs-lookup"><span data-stu-id="18cb0-114">Short form `/i`.</span></span>|  
|`uninstall`|<span data-ttu-id="18cb0-115">从服务模块集成中卸载 COM+ 接口配置。</span><span class="sxs-lookup"><span data-stu-id="18cb0-115">Uninstalls a configuration for a COM+ interface from Service Model integration.</span></span><br /><br /> <span data-ttu-id="18cb0-116">缩写形式：`/u`。</span><span class="sxs-lookup"><span data-stu-id="18cb0-116">Short form `/u`.</span></span>|  
|`list`|<span data-ttu-id="18cb0-117">列出有关 COM+ 应用程序和组件的信息，这些应用程序和组件具有为服务模块集成配置的接口。</span><span class="sxs-lookup"><span data-stu-id="18cb0-117">Lists information about COM+ applications and components that have interfaces that are configured for Service Model integration.</span></span><br /><br /> <span data-ttu-id="18cb0-118">缩写形式：`/l`。</span><span class="sxs-lookup"><span data-stu-id="18cb0-118">Short form `/l`.</span></span>|  
  
 <span data-ttu-id="18cb0-119">下表介绍可用于 ComSvcConfig.exe 的标志。</span><span class="sxs-lookup"><span data-stu-id="18cb0-119">The following table describes the flags that can be used with ComSvcConfig.exe.</span></span>  
  
|<span data-ttu-id="18cb0-120">选项</span><span class="sxs-lookup"><span data-stu-id="18cb0-120">Option</span></span>|<span data-ttu-id="18cb0-121">描述</span><span class="sxs-lookup"><span data-stu-id="18cb0-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="18cb0-122">`/application:` \<*ApplicationID* &#124; *ApplicationName*\></span><span class="sxs-lookup"><span data-stu-id="18cb0-122">`/application:` \<*ApplicationID* &#124; *ApplicationName*\></span></span>|<span data-ttu-id="18cb0-123">指定要配置的 COM+ 应用程序。</span><span class="sxs-lookup"><span data-stu-id="18cb0-123">Specifies the COM+ application to configure.</span></span><br /><br /> <span data-ttu-id="18cb0-124">缩写形式：`/a`。</span><span class="sxs-lookup"><span data-stu-id="18cb0-124">Short form `/a`.</span></span>|  
|<span data-ttu-id="18cb0-125">`/contract:` \<*ClassID*  &#124; *ProgID*  &#124; \*,*InterfaceID* &#124; *InterfaceName* &#124; \*\></span><span class="sxs-lookup"><span data-stu-id="18cb0-125">`/contract:` \<*ClassID*  &#124; *ProgID*  &#124; \*,*InterfaceID* &#124; *InterfaceName* &#124; \*\></span></span>|<span data-ttu-id="18cb0-126">指定将作为服务协定配置的 COM+ 组件和接口。</span><span class="sxs-lookup"><span data-stu-id="18cb0-126">Specifies the COM+ component and interface that will be configured as the contract for the service.</span></span><br /><br /> <span data-ttu-id="18cb0-127">缩写形式：`/c`。</span><span class="sxs-lookup"><span data-stu-id="18cb0-127">Short form `/c`.</span></span><br /><br /> <span data-ttu-id="18cb0-128">尽管通配符字符 (\*) 时指定的组件和接口的名称，可以使用我们建议您不要使用它，因为可能会公开您不打算对接口。</span><span class="sxs-lookup"><span data-stu-id="18cb0-128">While the wildcard character (\*) can be used when you specify the component and interface names, we recommend that you do not use it, because you might expose interfaces that you did not intend to.</span></span>|  
|<span data-ttu-id="18cb0-129">`/hosting:` \<*complus*  &#124; *was*\></span><span class="sxs-lookup"><span data-stu-id="18cb0-129">`/hosting:` \<*complus*  &#124; *was*\></span></span>|<span data-ttu-id="18cb0-130">指定是使用 COM+ 宿主模式还是 Web 宿主模式。</span><span class="sxs-lookup"><span data-stu-id="18cb0-130">Specifies whether to use the COM+ hosting mode or the Web hosting mode.</span></span><br /><br /> <span data-ttu-id="18cb0-131">缩写形式：`/h`。</span><span class="sxs-lookup"><span data-stu-id="18cb0-131">Short form `/h`.</span></span><br /><br /> <span data-ttu-id="18cb0-132">如果使用 COM+ 宿主模式，将需要显式激活 COM+ 应用程序。</span><span class="sxs-lookup"><span data-stu-id="18cb0-132">Using the COM+ hosting mode requires explicit activation of the COM+ application.</span></span> <span data-ttu-id="18cb0-133">如果使用 Web 宿主模式，将能够按照需要自动激活 COM+ 应用程序。</span><span class="sxs-lookup"><span data-stu-id="18cb0-133">Using the Web hosting mode allows the COM+ application to be automatically activated as required.</span></span> <span data-ttu-id="18cb0-134">如果 COM+ 应用程序是库应用程序，它将在 Internet 信息服务 (IIS) 进程中运行。</span><span class="sxs-lookup"><span data-stu-id="18cb0-134">If the COM+ application is a library application, it runs in the Internet Information Services (IIS) process.</span></span> <span data-ttu-id="18cb0-135">如果 COM+ 应用程序是服务器应用程序，它将在 Dllhost.exe 进程中运行。</span><span class="sxs-lookup"><span data-stu-id="18cb0-135">If the COM+ application is a server application, it runs in the Dllhost.exe process.</span></span>|  
|<span data-ttu-id="18cb0-136">`/webSite:` \<*WebsiteName*\></span><span class="sxs-lookup"><span data-stu-id="18cb0-136">`/webSite:` \<*WebsiteName*\></span></span>|<span data-ttu-id="18cb0-137">指定使用 Web 宿主模式时（请参见 `/hosting` 标志）用于宿主的网站。</span><span class="sxs-lookup"><span data-stu-id="18cb0-137">Specifies the Web site for hosting when Web hosting mode is used (see the `/hosting` flag).</span></span><br /><br /> <span data-ttu-id="18cb0-138">缩写形式：`/w`。</span><span class="sxs-lookup"><span data-stu-id="18cb0-138">Short form `/w`.</span></span><br /><br /> <span data-ttu-id="18cb0-139">如果未指定网站，则使用默认网站。</span><span class="sxs-lookup"><span data-stu-id="18cb0-139">If no Web site is specified, the default Web site is used.</span></span>|  
|<span data-ttu-id="18cb0-140">`/webDirectory:` \<*WebDirectoryName*\></span><span class="sxs-lookup"><span data-stu-id="18cb0-140">`/webDirectory:` \<*WebDirectoryName*\></span></span>|<span data-ttu-id="18cb0-141">指定在使用 Web 宿主时（请参见 `/hosting` 标志）用于宿主的虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="18cb0-141">Specifies the virtual directory for hosting when Web hosting is used (see the `/hosting` flag).</span></span><br /><br /> <span data-ttu-id="18cb0-142">缩写形式：`/d`。</span><span class="sxs-lookup"><span data-stu-id="18cb0-142">Short form `/d`.</span></span>|  
|`/mex`|<span data-ttu-id="18cb0-143">将元数据交换 (MEX) 服务终结点添加到默认服务配置，以支持要从服务中检索协定定义的客户端。</span><span class="sxs-lookup"><span data-stu-id="18cb0-143">Adds a Metadata Exchange (MEX) service endpoint to the default service configuration to support clients that want to retrieve a contract definition from the service.</span></span><br /><br /> <span data-ttu-id="18cb0-144">缩写形式：`/x`。</span><span class="sxs-lookup"><span data-stu-id="18cb0-144">Short form `/x`.</span></span>|  
|`/id`|<span data-ttu-id="18cb0-145">以 ID 的形式显示应用程序、组件和接口信息。</span><span class="sxs-lookup"><span data-stu-id="18cb0-145">Displays the application, component, and interface information as IDs.</span></span><br /><br /> <span data-ttu-id="18cb0-146">缩写形式：`/k`。</span><span class="sxs-lookup"><span data-stu-id="18cb0-146">Short form `/k`.</span></span>|  
|`/nologo`|<span data-ttu-id="18cb0-147">防止 ComSvcConfig.exe 显示其徽标。</span><span class="sxs-lookup"><span data-stu-id="18cb0-147">Prevents ComSvcConfig.exe from displaying its logo.</span></span><br /><br /> <span data-ttu-id="18cb0-148">缩写形式：`/n`。</span><span class="sxs-lookup"><span data-stu-id="18cb0-148">Short form `/n`.</span></span>|  
|`/verbose`|<span data-ttu-id="18cb0-149">除遇到的任何错误之外还输出所有警告或信息性文本。</span><span class="sxs-lookup"><span data-stu-id="18cb0-149">Outputs all warnings or informational text in addition to any errors encountered.</span></span><br /><br /> <span data-ttu-id="18cb0-150">缩写形式：`/v`。</span><span class="sxs-lookup"><span data-stu-id="18cb0-150">Short form `/v`.</span></span>|  
|`/help`|<span data-ttu-id="18cb0-151">显示用法消息。</span><span class="sxs-lookup"><span data-stu-id="18cb0-151">Displays the usage message.</span></span><br /><br /> <span data-ttu-id="18cb0-152">缩写形式：`/?`。</span><span class="sxs-lookup"><span data-stu-id="18cb0-152">Short form `/?`.</span></span>|  
|`/partial`|<span data-ttu-id="18cb0-153">在指定的接口包含一个或多个可公开的方法签名时生成一个服务配置。</span><span class="sxs-lookup"><span data-stu-id="18cb0-153">Generates a service configuration when the specified interface includes one or more method signatures that can be exposed.</span></span> <span data-ttu-id="18cb0-154">在服务初始化时，兼容的方法显示为服务协定上的操作，而非兼容方法将被忽略且不显示在服务协定中。</span><span class="sxs-lookup"><span data-stu-id="18cb0-154">At service initialization time, compatible methods appear as operations on the service contract, and non-compatible methods are ignored and absent from the service contract.</span></span><br /><br /> <span data-ttu-id="18cb0-155">如果缺少此标志，工具将不会在指定接口包含一个或多个不兼容方法时生成服务配置。</span><span class="sxs-lookup"><span data-stu-id="18cb0-155">If this flag is missing, the tool will not generate a service configuration when the specified interface includes one or more incompatible methods.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="18cb0-156">示例</span><span class="sxs-lookup"><span data-stu-id="18cb0-156">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="18cb0-157">描述</span><span class="sxs-lookup"><span data-stu-id="18cb0-157">Description</span></span>  
 <span data-ttu-id="18cb0-158">下面的示例使用 COM+ 宿主模式将 `IFinances` 组件（来自 OnlineStore COM+ 应用程序）的 `ItemOrders.IFinancial` 接口添加到作为 Web 服务公开的接口集中。</span><span class="sxs-lookup"><span data-stu-id="18cb0-158">The following example adds the `IFinances` interface of the `ItemOrders.IFinancial` component (from the OnlineStore COM+ application) to the set of interfaces that are exposed as Web services, using the COM+ hosting mode.</span></span> <span data-ttu-id="18cb0-159">除遇到的任何错误外还将输出所有警告。</span><span class="sxs-lookup"><span data-stu-id="18cb0-159">All warnings will be output in addition to any errors encountered.</span></span>  
  
### <a name="code"></a><span data-ttu-id="18cb0-160">代码</span><span class="sxs-lookup"><span data-stu-id="18cb0-160">Code</span></span>  
  
```  
ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose  
```  
  
### <a name="description"></a><span data-ttu-id="18cb0-161">描述</span><span class="sxs-lookup"><span data-stu-id="18cb0-161">Description</span></span>  
 <span data-ttu-id="18cb0-162">下面的示例使用 Web 宿主模式将 `IStockLevels` 组件（来自 OnlineWarehouse COM+ 应用程序）的 `ItemInventory.Warehouse` 接口添加到作为 Web 服务公开的接口集中。</span><span class="sxs-lookup"><span data-stu-id="18cb0-162">The following example adds the `IStockLevels` interface of the `ItemInventory.Warehouse` component (from the OnlineWarehouse COM+ application) to the set of interfaces that are exposed as Web services, using the Web hosting mode.</span></span> <span data-ttu-id="18cb0-163">Web 服务是宿主在 IIS 的 OnlineWarehouse 虚拟目录中的网站。</span><span class="sxs-lookup"><span data-stu-id="18cb0-163">The Web service is Web hosted in the OnlineWarehouse virtual directory of IIS.</span></span>  
  
### <a name="code"></a><span data-ttu-id="18cb0-164">代码</span><span class="sxs-lookup"><span data-stu-id="18cb0-164">Code</span></span>  
  
```  
ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse  
```  
  
### <a name="description"></a><span data-ttu-id="18cb0-165">描述</span><span class="sxs-lookup"><span data-stu-id="18cb0-165">Description</span></span>  
 <span data-ttu-id="18cb0-166">下面的示例从作为 Web 服务公开的接口集中移除 `IFinances` 组件（来自 OnlineStore COM+ 应用程序）的 `ItemOrders.Financial` 接口。</span><span class="sxs-lookup"><span data-stu-id="18cb0-166">The following example removes the `IFinances` interface of the `ItemOrders.Financial` component (from the OnlineStore COM+ application) from the set of interfaces that are exposed as Web services.</span></span>  
  
### <a name="code"></a><span data-ttu-id="18cb0-167">代码</span><span class="sxs-lookup"><span data-stu-id="18cb0-167">Code</span></span>  
  
```  
ComSvcConfig.exe /uninstall /application:OnlineStore /interface:ItemOrders.Financial,IFinances /hosting:complus  
```  
  
### <a name="description"></a><span data-ttu-id="18cb0-168">描述</span><span class="sxs-lookup"><span data-stu-id="18cb0-168">Description</span></span>  
 <span data-ttu-id="18cb0-169">下面的示例为本地计算机上的 OnlineStore COM+ 应用程序列出当前公开的 COM+ 主机接口，以及相应的地址和绑定详细信息。</span><span class="sxs-lookup"><span data-stu-id="18cb0-169">The following example lists currently exposed COM+ hosted interfaces, along with the corresponding address and binding details, for the OnlineStore COM+ application on the local machine.</span></span>  
  
### <a name="code"></a><span data-ttu-id="18cb0-170">代码</span><span class="sxs-lookup"><span data-stu-id="18cb0-170">Code</span></span>  
  
```  
ComSvcConfig.exe /list /application:OnlineStore /hosting:complus  
```  
  
## <a name="see-also"></a><span data-ttu-id="18cb0-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="18cb0-171">See also</span></span>

- [<span data-ttu-id="18cb0-172">如何：使用 COM + 服务模型配置工具</span><span class="sxs-lookup"><span data-stu-id="18cb0-172">How to: Use the COM+ Service Model Configuration Tool</span></span>](../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)
