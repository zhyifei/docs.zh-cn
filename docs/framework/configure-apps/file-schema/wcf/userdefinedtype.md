---
title: <userDefinedType>
ms.date: 03/30/2017
ms.assetid: 0f70ec06-8249-4f0c-9f49-b4df59985fb8
ms.openlocfilehash: 46beb88cedf051ed1683161b6ed9b37273ed01f1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182119"
---
# <a name="userdefinedtype"></a><span data-ttu-id="a8a93-101">\<userDefinedType></span><span class="sxs-lookup"><span data-stu-id="a8a93-101">\<userDefinedType></span></span>
<span data-ttu-id="a8a93-102">表示一个要包括到服务协定中的用户定义类型 (UDT)。</span><span class="sxs-lookup"><span data-stu-id="a8a93-102">Represents a User Defined Type (UDT) that is to be included in the service contract.</span></span>  
  
 <span data-ttu-id="a8a93-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a8a93-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a8a93-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="a8a93-104">\<comContracts></span></span>  
<span data-ttu-id="a8a93-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="a8a93-105">\<comContract></span></span>  
<span data-ttu-id="a8a93-106">\<userDefinedTypes></span><span class="sxs-lookup"><span data-stu-id="a8a93-106">\<userDefinedTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8a93-107">语法</span><span class="sxs-lookup"><span data-stu-id="a8a93-107">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8a93-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a8a93-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a8a93-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a8a93-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8a93-110">特性</span><span class="sxs-lookup"><span data-stu-id="a8a93-110">Attributes</span></span>  
  
|<span data-ttu-id="a8a93-111">特性</span><span class="sxs-lookup"><span data-stu-id="a8a93-111">Attribute</span></span>|<span data-ttu-id="a8a93-112">描述</span><span class="sxs-lookup"><span data-stu-id="a8a93-112">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="a8a93-113">一个可选属性，包含提供可读类型名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="a8a93-113">An optional attribute that contains a string that provides the readable type name.</span></span> <span data-ttu-id="a8a93-114">运行库不使用该属性，但该属性可以帮助读取器区分类型。</span><span class="sxs-lookup"><span data-stu-id="a8a93-114">This is not used by the runtime but helps a reader to distinguish the types.</span></span>|  
|`TypeDefID`|<span data-ttu-id="a8a93-115">一个 GUID 字符串，标识已注册类型库中的特定 UDT 类型。</span><span class="sxs-lookup"><span data-stu-id="a8a93-115">A GUID string that identifies the specific UDT type within the registered type library.</span></span>|  
|`TypeLibID`|<span data-ttu-id="a8a93-116">一个 GUID 字符串，标识定义该类型的已注册类型库。</span><span class="sxs-lookup"><span data-stu-id="a8a93-116">A GUID string that identifies the registered type library that defines the type.</span></span>|  
|`TypeLibVersion`|<span data-ttu-id="a8a93-117">一个字符串，标识定义该类型的类型库版本。</span><span class="sxs-lookup"><span data-stu-id="a8a93-117">A string that identifies the type library version that defines the type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a8a93-118">子元素</span><span class="sxs-lookup"><span data-stu-id="a8a93-118">Child Elements</span></span>  
 <span data-ttu-id="a8a93-119">无。</span><span class="sxs-lookup"><span data-stu-id="a8a93-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a8a93-120">父元素</span><span class="sxs-lookup"><span data-stu-id="a8a93-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a8a93-121">元素</span><span class="sxs-lookup"><span data-stu-id="a8a93-121">Element</span></span>|<span data-ttu-id="a8a93-122">描述</span><span class="sxs-lookup"><span data-stu-id="a8a93-122">Description</span></span>|  
|-------------|-----------------|  
|`userDefinedTypes`|<span data-ttu-id="a8a93-123">一个 `userDefinedType` 元素集合。</span><span class="sxs-lookup"><span data-stu-id="a8a93-123">A collection of `userDefinedType` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8a93-124">备注</span><span class="sxs-lookup"><span data-stu-id="a8a93-124">Remarks</span></span>  
 <span data-ttu-id="a8a93-125">COM+ 集成运行时通过检查类型库来创建服务。</span><span class="sxs-lookup"><span data-stu-id="a8a93-125">The COM+ integration runtime creates services by inspecting the type library.</span></span> <span data-ttu-id="a8a93-126">当 COM+ 组件包含传递 VARIANT 的方法时，系统将无法确定要在运行时之前传递的实际类型。</span><span class="sxs-lookup"><span data-stu-id="a8a93-126">When a COM+ component contains methods that pass a VARIANT, the system cannot determine the actual types to be passed prior to runtime.</span></span> <span data-ttu-id="a8a93-127">因此，当您试图在 VARIANT 内传递用户定义类型 (UDT) 时，将由于该类型不是可供序列化的已知类型而失败。</span><span class="sxs-lookup"><span data-stu-id="a8a93-127">Therefore, when you attempt to pass a User Defined Type (UDT) within a VARIANT, it fails because it is not a known type for serialization.</span></span>  
  
 <span data-ttu-id="a8a93-128">若要避免此问题，可以将 UDT 添加到配置文件，以使 UDT 作为已知类型包括到相应的服务协定中。</span><span class="sxs-lookup"><span data-stu-id="a8a93-128">To circumvent this problem, you can add the UDTs to the configuration file so that they can be included as known types on the appropriate service contract.</span></span> <span data-ttu-id="a8a93-129">为此，必须唯一地标识 UDT 和协定（即使用它的原始 COM 接口）。</span><span class="sxs-lookup"><span data-stu-id="a8a93-129">In order to do so, you have to uniquely identify the UDT and the contract(s), that is, the original COM interface(s) that uses it.</span></span>  
  
 <span data-ttu-id="a8a93-130">下面的示例演示如何添加两个特定的 Udt 添加到 <`userDefinedTypes`> 为此配置文件的部分。</span><span class="sxs-lookup"><span data-stu-id="a8a93-130">The following example demonstrates adding two specific UDTs to the <`userDefinedTypes`> section of the configuration file for this purpose.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
    <userDefinedTypes>
      <userDefinedType name="CustomerType"
                       typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"
                       typeLibVersion="1.0"
                       typeDefID="{D129765C-F211-434e-825A-9A63198C41F2}">
      </userDefinedType>
      <userDefinedType name="AddressType"
                       typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"
                       typeLibVersion="1.0"
                       typeDefID="{4616AE0D-687A-43B7-BC63-141AE3DFD099}">
      </userDefinedType>
    </userDefinedTypes>
    <exposedMethods>
      <exposedMethod name="BuyStock" />
      <exposedMethod name="SellStock" />
      <exposedMethod name="ExecuteTransaction" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="a8a93-131">在初始化服务时，集成运行库会查找指定的类型，然后将这些类型添加到指定协定的已知类型集合中。</span><span class="sxs-lookup"><span data-stu-id="a8a93-131">When the service is initialized, the integration runtime looks up the specified types and adds them to the known types collection for the specified contracts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8a93-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8a93-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElement.UserDefinedTypes%2A>
- <xref:System.ServiceModel.Configuration.ComUdtElementCollection>
- <xref:System.ServiceModel.Configuration.ComUdtElement>
- [<span data-ttu-id="a8a93-133">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="a8a93-133">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="a8a93-134">与 COM+ 应用程序集成</span><span class="sxs-lookup"><span data-stu-id="a8a93-134">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="a8a93-135">如何：配置 COM+ 服务设置</span><span class="sxs-lookup"><span data-stu-id="a8a93-135">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
