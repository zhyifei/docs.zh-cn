---
title: '&lt;指令&gt;元素 (.NET Native)'
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd571255f924c9f3878c00a2bc01397d63e6d777
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33394441"
---
# <a name="ltdirectivesgt-element-net-native"></a><span data-ttu-id="4c6bd-102">&lt;指令&gt;元素 (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="4c6bd-102">&lt;Directives&gt; Element (.NET Native)</span></span>
<span data-ttu-id="4c6bd-103">根元素位于 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 的每个运行时指令文件中。</span><span class="sxs-lookup"><span data-stu-id="4c6bd-103">The root element in every runtime directives file for [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
 <span data-ttu-id="4c6bd-104">**\<指令 xmlns ="http://schemas.microsoft.com/netfx/2013/01/metadata">**</span><span class="sxs-lookup"><span data-stu-id="4c6bd-104">**\<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c6bd-105">语法</span><span class="sxs-lookup"><span data-stu-id="4c6bd-105">Syntax</span></span>  
  
```xml  
      <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="4c6bd-106">特性</span><span class="sxs-lookup"><span data-stu-id="4c6bd-106">Attributes</span></span>  
  
|<span data-ttu-id="4c6bd-107">特性</span><span class="sxs-lookup"><span data-stu-id="4c6bd-107">Attribute</span></span>|<span data-ttu-id="4c6bd-108">描述</span><span class="sxs-lookup"><span data-stu-id="4c6bd-108">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="4c6bd-109">XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="4c6bd-109">The XML namespace.</span></span> <span data-ttu-id="4c6bd-110">其值始终是 **"http://schemas.microsoft.com/netfx/2013/01/metadata"**。</span><span class="sxs-lookup"><span data-stu-id="4c6bd-110">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="4c6bd-111">子元素</span><span class="sxs-lookup"><span data-stu-id="4c6bd-111">Child elements</span></span>  
  
|<span data-ttu-id="4c6bd-112">元素</span><span class="sxs-lookup"><span data-stu-id="4c6bd-112">Element</span></span>|<span data-ttu-id="4c6bd-113">描述</span><span class="sxs-lookup"><span data-stu-id="4c6bd-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c6bd-114">\<Application></span><span class="sxs-lookup"><span data-stu-id="4c6bd-114">\<Application></span></span>](../../../docs/framework/net-native/application-element-net-native.md)|<span data-ttu-id="4c6bd-115">作为应用程序范围内的类型和其元数据可以用于反射的类型成员的容器而服务。</span><span class="sxs-lookup"><span data-stu-id="4c6bd-115">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="4c6bd-116">\<Library></span><span class="sxs-lookup"><span data-stu-id="4c6bd-116">\<Library></span></span>](../../../docs/framework/net-native/library-element-net-native.md)|<span data-ttu-id="4c6bd-117">定义那些子类型和类型成员在运行时间要求元数据的程序集。</span><span class="sxs-lookup"><span data-stu-id="4c6bd-117">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c6bd-118">备注</span><span class="sxs-lookup"><span data-stu-id="4c6bd-118">Remarks</span></span>  
 <span data-ttu-id="4c6bd-119">每个运行时指令文件都可以只包含一个 `<Directives>` 元素。</span><span class="sxs-lookup"><span data-stu-id="4c6bd-119">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="4c6bd-120">`<Directives>` 元素可包含零个或一个 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 元素，以及零个、一个或多个 [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="4c6bd-120">The `<Directives>` element can contain zero or one [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) element, and zero, one, or more [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c6bd-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c6bd-121">See Also</span></span>  
 [<span data-ttu-id="4c6bd-122">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="4c6bd-122">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="4c6bd-123">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="4c6bd-123">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
