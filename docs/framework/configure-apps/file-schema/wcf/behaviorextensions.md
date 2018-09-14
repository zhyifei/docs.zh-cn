---
title: '&lt;behaviorExtensions&gt;'
ms.date: 03/30/2017
ms.assetid: 59f2791a-c78f-40d7-aa80-0d9cd10135d9
ms.openlocfilehash: d025497956715913923e839cb6c482f44f96babb
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45513462"
---
# <a name="ltbehaviorextensionsgt"></a><span data-ttu-id="c20e9-102">&lt;behaviorExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="c20e9-102">&lt;behaviorExtensions&gt;</span></span>
<span data-ttu-id="c20e9-103">用户可以使用行为扩展来创建用户定义的行为元素。</span><span class="sxs-lookup"><span data-stu-id="c20e9-103">Behavior extensions enable the user to create user-defined behavior elements.</span></span> <span data-ttu-id="c20e9-104">这些元素可与标准的 Windows Communication Foundation (WCF) 行为元素一起使用。</span><span class="sxs-lookup"><span data-stu-id="c20e9-104">These elements can be used alongside the standard Windows Communication Foundation (WCF) behavior elements.</span></span> <span data-ttu-id="c20e9-105">`behaviorExtensions` 节定义了元素，使其可用于配置中。</span><span class="sxs-lookup"><span data-stu-id="c20e9-105">The `behaviorExtensions` section defines the element such that it can be used in configuration.</span></span> <span data-ttu-id="c20e9-106">下面是一个典型的行为扩展示例。</span><span class="sxs-lookup"><span data-stu-id="c20e9-106">Here is an example of a typical behavior extension.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <behaviorExtensions>  
            <add name="myBehavior" type="Microsoft.ServiceModel.Samples.MyBehaviorSection, MyBehavior,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
       </behaviorExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="c20e9-107">若要向元素添加配置功能，需要编写和注册配置元素。</span><span class="sxs-lookup"><span data-stu-id="c20e9-107">To add configuration abilities to the element, you need to write and register a configuration element.</span></span> <span data-ttu-id="c20e9-108">有关这方面的更多信息，请参见 <xref:System.Configuration> 文档。</span><span class="sxs-lookup"><span data-stu-id="c20e9-108">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="c20e9-109">在定义元素及其配置类型之后，可以使用扩展，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="c20e9-109">After the element and its configuration type are defined, the extension can be used, as shown in the following example.</span></span>  
  
```xml  
<behaviors>  
    <behavior configurationName="testChannelBehavior">  
        <myBehavior />  
        <channelSecurity cacheCookies="false" detectReplays="false" maxCachedNonces="9"  
            maxClockSkew="00:00:03" maxCookieCachingTime="00:07:24" replayWindow="00:07:22.2190000" />  
    </behavior>  
</behaviors>  
```  
  
## <a name="security"></a><span data-ttu-id="c20e9-110">安全性</span><span class="sxs-lookup"><span data-stu-id="c20e9-110">Security</span></span>  
 <span data-ttu-id="c20e9-111">强烈建议在 `machine.config` 和 `app.config` 文件中注册类型时使用完全限定的程序集名称。</span><span class="sxs-lookup"><span data-stu-id="c20e9-111">It is strongly recommended that you use fully qualified assembly names when registering types in the `machine.config` and `app.config` files.</span></span> <span data-ttu-id="c20e9-112">如果没有唯一定义类型，则 CLR 类型加载程序将按照指定的顺序在以下位置中搜索类型：</span><span class="sxs-lookup"><span data-stu-id="c20e9-112">If the type is not uniquely defined, the CLR type loader searches for it in the following locations in the specified order:</span></span>  
  
 <span data-ttu-id="c20e9-113">如果已经知道类型的程序集，则加载程序将搜索配置文件的重定向位置、GAC、使用配置信息的当前程序集以及应用程序基目录。</span><span class="sxs-lookup"><span data-stu-id="c20e9-113">If the assembly of the type is known, the loader searches the configuration file's redirect locations, GAC, the current assembly using configuration information, and the application base directory.</span></span> <span data-ttu-id="c20e9-114">如果程序集未知，则加载程序将搜索当前程序集、mscorlib 以及 `TypeResolve` 事件处理程序返回的位置。</span><span class="sxs-lookup"><span data-stu-id="c20e9-114">If the assembly is unknown, the loader searches the current assembly, mscorlib, and the location returned by the `TypeResolve` event handler.</span></span> <span data-ttu-id="c20e9-115">通过使用“类型转发”机制和 AppDomain.TypeResolve 事件之类的挂钩，可以修改此 CLR 搜索顺序。</span><span class="sxs-lookup"><span data-stu-id="c20e9-115">This CLR search order can be modified with hooks such as the Type Forwarding mechanism and the AppDomain.TypeResolve event.</span></span>  
  
 <span data-ttu-id="c20e9-116">攻击者可以利用 CLR 搜索顺序来执行未授权的代码。</span><span class="sxs-lookup"><span data-stu-id="c20e9-116">An attacker can exploit the CLR search order and execute unauthorized code.</span></span> <span data-ttu-id="c20e9-117">通过使用完全限定的（强）名称，可以唯一标识类型并进一步提高系统的安全性。</span><span class="sxs-lookup"><span data-stu-id="c20e9-117">Using fully qualified (strong) names uniquely identifies a type and further increases security of your system.</span></span>  
  
 <span data-ttu-id="c20e9-118">有关详细信息，请参阅[运行时如何定位程序集](https://go.microsoft.com/fwlink/?LinkId=95336)和<xref:System.AppDomain.TypeResolve>。</span><span class="sxs-lookup"><span data-stu-id="c20e9-118">For more information, see [How the Runtime Locates Assemblies](https://go.microsoft.com/fwlink/?LinkId=95336) and <xref:System.AppDomain.TypeResolve>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c20e9-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="c20e9-119">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>  
 [<span data-ttu-id="c20e9-120">使用行为配置和扩展运行时</span><span class="sxs-lookup"><span data-stu-id="c20e9-120">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
