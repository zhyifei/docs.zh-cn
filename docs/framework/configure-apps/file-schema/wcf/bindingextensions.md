---
title: <bindingExtensions>
ms.date: 03/30/2017
ms.assetid: 8373f94d-d095-486f-8f1e-4ac2f72b58c7
ms.openlocfilehash: ed55701e45d8580e37cf4776de6b9c5241e0548c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113030"
---
# <a name="bindingextensions"></a><span data-ttu-id="64c22-101">\<bindingExtensions></span><span class="sxs-lookup"><span data-stu-id="64c22-101">\<bindingExtensions></span></span>
<span data-ttu-id="64c22-102">本节为使用计算机或应用程序配置文件中的用户定义绑定提供支持。</span><span class="sxs-lookup"><span data-stu-id="64c22-102">This section enables the use of a user defined binding from a machine or application configuration file.</span></span> <span data-ttu-id="64c22-103">通过使用 `add` 关键字，并将元素的 `type` 属性设置为用户定义的绑定，将 `name` 属性设置为用户定义的绑定的名称，可以将用户定义的绑定添加到此集合中。</span><span class="sxs-lookup"><span data-stu-id="64c22-103">You can add a user defined binding to this collection by using the `add` keyword, and setting the `type` attribute of the element to a user defined binding, as well as the `name` attribute to the name of the user defined binding.</span></span>  
  
 <span data-ttu-id="64c22-104">用户可以使用绑定扩展来创建用户定义的绑定，并将其作为终结点配置的一部分来使用。</span><span class="sxs-lookup"><span data-stu-id="64c22-104">Binding extensions enable the user to create user-defined bindings for use as part an endpoint configuration.</span></span> <span data-ttu-id="64c22-105">从编程角度来看，绑定扩展是一个实现抽象类 <xref:System.ServiceModel.Channels.Binding> 的类型。</span><span class="sxs-lookup"><span data-stu-id="64c22-105">Programmatically, a binding extension is a type that implements the abstract class <xref:System.ServiceModel.Channels.Binding>.</span></span>  
  
 <span data-ttu-id="64c22-106">下面的示例使用 `add` 元素以及 `name` 属性将绑定扩展添加到配置文件的 `bindingElementExtensions` 节。</span><span class="sxs-lookup"><span data-stu-id="64c22-106">The following example uses the `add` element, as well as the `name` attribute to add a binding extension to the `bindingElementExtensions` section of the configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <bindingExtensions>
      <add name="MyBinding"
           type="Microsoft.ServiceModel.Samples.MyBinding, MyBinding,
                 Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
    </bindingExtensions>
  </extensions>
</system.serviceModel>
```  
  
 <span data-ttu-id="64c22-107">若要向元素添加配置功能，用户需要编写和注册 `bindingSection` 元素。</span><span class="sxs-lookup"><span data-stu-id="64c22-107">To add configuration abilities to the element, the user needs to write and register a `bindingSection` element.</span></span> <span data-ttu-id="64c22-108">有关这方面的更多信息，请参见 <xref:System.Configuration> 文档。</span><span class="sxs-lookup"><span data-stu-id="64c22-108">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="64c22-109">在定义元素及其配置类型之后，可以将扩展用作终结点的一部分，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="64c22-109">After the element and its configuration type are defined, the extension can be used as part of an endpoint as shown in the following example.</span></span>  
  
```xml  
<services>
  <service name="MyService">
    <endpoint address="myAddress"
              binding="MyBinding" />
  </service>
</services>
```  
  
## <a name="see-also"></a><span data-ttu-id="64c22-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="64c22-110">See also</span></span>

- [<span data-ttu-id="64c22-111">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="64c22-111">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
