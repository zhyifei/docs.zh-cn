---
title: <Directives>元素 (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cfc9dc5c8122f9b1b1696cedcd5d9a8ceead403
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61868579"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="003ba-102">\<指令 > 元素 (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="003ba-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="003ba-103">.NET native 每个运行时指令文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="003ba-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">` 
  
## <a name="syntax"></a><span data-ttu-id="003ba-104">语法</span><span class="sxs-lookup"><span data-stu-id="003ba-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="003ba-105">特性</span><span class="sxs-lookup"><span data-stu-id="003ba-105">Attributes</span></span>  
  
|<span data-ttu-id="003ba-106">特性</span><span class="sxs-lookup"><span data-stu-id="003ba-106">Attribute</span></span>|<span data-ttu-id="003ba-107">描述</span><span class="sxs-lookup"><span data-stu-id="003ba-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="003ba-108">XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="003ba-108">The XML namespace.</span></span> <span data-ttu-id="003ba-109">其值始终是 **"http://schemas.microsoft.com/netfx/2013/01/metadata"**。</span><span class="sxs-lookup"><span data-stu-id="003ba-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="003ba-110">子元素</span><span class="sxs-lookup"><span data-stu-id="003ba-110">Child elements</span></span>  
  
|<span data-ttu-id="003ba-111">元素</span><span class="sxs-lookup"><span data-stu-id="003ba-111">Element</span></span>|<span data-ttu-id="003ba-112">描述</span><span class="sxs-lookup"><span data-stu-id="003ba-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="003ba-113">\<Application></span><span class="sxs-lookup"><span data-stu-id="003ba-113">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)|<span data-ttu-id="003ba-114">作为应用程序范围内的类型和其元数据可以用于反射的类型成员的容器而服务。</span><span class="sxs-lookup"><span data-stu-id="003ba-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="003ba-115">\<Library></span><span class="sxs-lookup"><span data-stu-id="003ba-115">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)|<span data-ttu-id="003ba-116">定义那些子类型和类型成员在运行时间要求元数据的程序集。</span><span class="sxs-lookup"><span data-stu-id="003ba-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="003ba-117">备注</span><span class="sxs-lookup"><span data-stu-id="003ba-117">Remarks</span></span>  
 <span data-ttu-id="003ba-118">每个运行时指令文件都可以只包含一个 `<Directives>` 元素。</span><span class="sxs-lookup"><span data-stu-id="003ba-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="003ba-119">`<Directives>` 元素可包含零个或一个 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 元素，以及零个、一个或多个 [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="003ba-119">The `<Directives>` element can contain zero or one [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element, and zero, one, or more [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="003ba-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="003ba-120">See also</span></span>

- [<span data-ttu-id="003ba-121">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="003ba-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="003ba-122">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="003ba-122">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
