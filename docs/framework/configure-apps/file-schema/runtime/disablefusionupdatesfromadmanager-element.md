---
title: <disableFusionUpdatesFromADManager> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27c8c1cac68aca1c40826ff549d62d9636d9b0c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704903"
---
# <a name="disablefusionupdatesfromadmanager-element"></a><span data-ttu-id="ab9f9-102">\<disableFusionUpdatesFromADManager > 元素</span><span class="sxs-lookup"><span data-stu-id="ab9f9-102">\<disableFusionUpdatesFromADManager> Element</span></span>
<span data-ttu-id="ab9f9-103">指定是否禁用允许运行时主机为应用程序域重写配置设置的默认行为。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-103">Specifies whether the default behavior, which is to allow the runtime host to override configuration settings for an application domain, is disabled.</span></span>  
  
 <span data-ttu-id="ab9f9-104">\<配置 > 元素</span><span class="sxs-lookup"><span data-stu-id="ab9f9-104">\<configuration> Element</span></span>  
<span data-ttu-id="ab9f9-105">\<运行时 > 元素</span><span class="sxs-lookup"><span data-stu-id="ab9f9-105">\<runtime> Element</span></span>  
<span data-ttu-id="ab9f9-106">\<disableFusionUpdatesFromADManager></span><span class="sxs-lookup"><span data-stu-id="ab9f9-106">\<disableFusionUpdatesFromADManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab9f9-107">语法</span><span class="sxs-lookup"><span data-stu-id="ab9f9-107">Syntax</span></span>  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab9f9-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ab9f9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ab9f9-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab9f9-110">特性</span><span class="sxs-lookup"><span data-stu-id="ab9f9-110">Attributes</span></span>  
  
|<span data-ttu-id="ab9f9-111">特性</span><span class="sxs-lookup"><span data-stu-id="ab9f9-111">Attribute</span></span>|<span data-ttu-id="ab9f9-112">描述</span><span class="sxs-lookup"><span data-stu-id="ab9f9-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ab9f9-113">enabled</span><span class="sxs-lookup"><span data-stu-id="ab9f9-113">enabled</span></span>|<span data-ttu-id="ab9f9-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="ab9f9-115">指定是否禁用重写合成设置的默认功能。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-115">Specifies whether the default ability to override Fusion settings is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="ab9f9-116">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="ab9f9-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="ab9f9-117">“值”</span><span class="sxs-lookup"><span data-stu-id="ab9f9-117">Value</span></span>|<span data-ttu-id="ab9f9-118">Description</span><span class="sxs-lookup"><span data-stu-id="ab9f9-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ab9f9-119">0</span><span class="sxs-lookup"><span data-stu-id="ab9f9-119">0</span></span>|<span data-ttu-id="ab9f9-120">不要禁用重写合成设置的功能。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-120">Do not disable the ability to override Fusion settings.</span></span> <span data-ttu-id="ab9f9-121">这是默认行为，从开始[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-121">This is the default behavior, starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span></span>|  
|<span data-ttu-id="ab9f9-122">1</span><span class="sxs-lookup"><span data-stu-id="ab9f9-122">1</span></span>|<span data-ttu-id="ab9f9-123">禁用重写合成设置的功能。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-123">Disable the ability to override Fusion settings.</span></span> <span data-ttu-id="ab9f9-124">这将恢复为.NET Framework 的早期版本的行为。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-124">This reverts to the behavior of earlier versions of the .NET Framework.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ab9f9-125">子元素</span><span class="sxs-lookup"><span data-stu-id="ab9f9-125">Child Elements</span></span>  
 <span data-ttu-id="ab9f9-126">无。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ab9f9-127">父元素</span><span class="sxs-lookup"><span data-stu-id="ab9f9-127">Parent Elements</span></span>  
  
|<span data-ttu-id="ab9f9-128">元素</span><span class="sxs-lookup"><span data-stu-id="ab9f9-128">Element</span></span>|<span data-ttu-id="ab9f9-129">描述</span><span class="sxs-lookup"><span data-stu-id="ab9f9-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ab9f9-130">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ab9f9-131">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab9f9-132">备注</span><span class="sxs-lookup"><span data-stu-id="ab9f9-132">Remarks</span></span>  
 <span data-ttu-id="ab9f9-133">从开始[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]，默认行为是允许<xref:System.AppDomainManager>对象重写配置设置，通过使用<xref:System.AppDomainSetup.ConfigurationFile%2A>属性或<xref:System.AppDomainSetup.SetConfigurationBytes%2A>方法<xref:System.AppDomainSetup>对象传递给您的实现<xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType>的子类中的方法， <xref:System.AppDomainManager>。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-133">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the default behavior is to allow the <xref:System.AppDomainManager> object to override configuration settings by using the <xref:System.AppDomainSetup.ConfigurationFile%2A> property or the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method of the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method, in your subclass of <xref:System.AppDomainManager>.</span></span> <span data-ttu-id="ab9f9-134">对于默认应用程序域，您更改的设置重写应用程序配置文件指定的设置。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-134">For the default application domain, the settings you change override the settings that were specified by the application configuration file.</span></span> <span data-ttu-id="ab9f9-135">对于其他应用程序域，这些重写的配置设置，已将传递给<xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType>或<xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-135">For other application domains, they override the configuration settings that were passed to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="ab9f9-136">可以传递新的配置信息，也可以传递 null (`Nothing`在 Visual Basic 中) 以消除中传递的配置信息。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-136">You can either pass new configuration information, or pass null (`Nothing` in Visual Basic) to eliminate configuration information that was passed in.</span></span>  
  
 <span data-ttu-id="ab9f9-137">未将配置信息传递给<xref:System.AppDomainSetup.ConfigurationFile%2A>属性和<xref:System.AppDomainSetup.SetConfigurationBytes%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-137">Do not pass configuration information to both the <xref:System.AppDomainSetup.ConfigurationFile%2A> property and the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method.</span></span> <span data-ttu-id="ab9f9-138">如果将配置信息传递给时，信息传递给<xref:System.AppDomainSetup.ConfigurationFile%2A>属性被忽略，因为<xref:System.AppDomainSetup.SetConfigurationBytes%2A>方法重写应用程序配置文件中的配置信息。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-138">If you pass configuration information to both, the information you pass to the <xref:System.AppDomainSetup.ConfigurationFile%2A> property is ignored, because the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method overrides configuration information from the application configuration file.</span></span> <span data-ttu-id="ab9f9-139">如果您使用<xref:System.AppDomainSetup.ConfigurationFile%2A>属性，您可以将传递 null (`Nothing`在 Visual Basic 中) 到<xref:System.AppDomainSetup.SetConfigurationBytes%2A>方法来消除对的调用中指定的任何配置字节<xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType>或<xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-139">If you use the <xref:System.AppDomainSetup.ConfigurationFile%2A> property, you can pass null (`Nothing` in Visual Basic) to the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method to eliminate any configuration bytes that were specified in the call to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="ab9f9-140">除了配置信息，可以更改以下设置，在<xref:System.AppDomainSetup>传递给您的实现的对象<xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType>方法： <xref:System.AppDomainSetup.ApplicationBase%2A>， <xref:System.AppDomainSetup.ApplicationName%2A>， <xref:System.AppDomainSetup.CachePath%2A>， <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>， <xref:System.AppDomainSetup.DisallowBindingRedirects%2A><xref:System.AppDomainSetup.DisallowCodeDownload%2A>， <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>， <xref:System.AppDomainSetup.DynamicBase%2A>， <xref:System.AppDomainSetup.LoaderOptimization%2A>， <xref:System.AppDomainSetup.PrivateBinPath%2A>， <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>， <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>，和<xref:System.AppDomainSetup.ShadowCopyFiles%2A>。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-140">In addition to configuration information, you can change the following settings on the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, and <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span></span>  
  
 <span data-ttu-id="ab9f9-141">作为一种方式使用`<disableFusionUpdatesFromADManager>`元素中，您可以禁用默认行为通过创建注册表设置或通过设置环境变量。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-141">As an alternative to using the `<disableFusionUpdatesFromADManager>` element, you can disable the default behavior by creating a registry setting or by setting an environment variable.</span></span> <span data-ttu-id="ab9f9-142">在注册表中，创建一个名为`COMPLUS_disableFusionUpdatesFromADManager`下`HKCU\Software\Microsoft\.NETFramework`或`HKLM\Software\Microsoft\.NETFramework`，并将值设置为 1。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-142">In the registry, create a DWORD value named `COMPLUS_disableFusionUpdatesFromADManager` under `HKCU\Software\Microsoft\.NETFramework` or `HKLM\Software\Microsoft\.NETFramework`, and set the value to 1.</span></span> <span data-ttu-id="ab9f9-143">在命令行设置环境变量`COMPLUS_disableFusionUpdatesFromADManager`为 1。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-143">At the command line, set the environment variable `COMPLUS_disableFusionUpdatesFromADManager` to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab9f9-144">示例</span><span class="sxs-lookup"><span data-stu-id="ab9f9-144">Example</span></span>  
 <span data-ttu-id="ab9f9-145">下面的示例演示如何禁止重写通过使用合成设置`<disableFusionUpdatesFromADManager>`元素。</span><span class="sxs-lookup"><span data-stu-id="ab9f9-145">The following example shows how to disable the ability to override Fusion settings by using the `<disableFusionUpdatesFromADManager>` element.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab9f9-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab9f9-146">See also</span></span>

- [<span data-ttu-id="ab9f9-147">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="ab9f9-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="ab9f9-148">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="ab9f9-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="ab9f9-149">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="ab9f9-149">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
