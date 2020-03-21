---
title: <Directives>元素 (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 49c1aaf005b80a6c1c1fa382eebc2cb0dbfa4be7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181048"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="348f1-102">\<指令>元素（.NET 本机）</span><span class="sxs-lookup"><span data-stu-id="348f1-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="348f1-103">每个运行时指令文件中的根元素为 .NET 本机。</span><span class="sxs-lookup"><span data-stu-id="348f1-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">`
  
## <a name="syntax"></a><span data-ttu-id="348f1-104">语法</span><span class="sxs-lookup"><span data-stu-id="348f1-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="348f1-105">属性</span><span class="sxs-lookup"><span data-stu-id="348f1-105">Attributes</span></span>  
  
|<span data-ttu-id="348f1-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="348f1-106">Attribute</span></span>|<span data-ttu-id="348f1-107">说明</span><span class="sxs-lookup"><span data-stu-id="348f1-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="348f1-108">XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="348f1-108">The XML namespace.</span></span> <span data-ttu-id="348f1-109">它的价值总是 **""。http://schemas.microsoft.com/netfx/2013/01/metadata**</span><span class="sxs-lookup"><span data-stu-id="348f1-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="348f1-110">子元素</span><span class="sxs-lookup"><span data-stu-id="348f1-110">Child elements</span></span>  
  
|<span data-ttu-id="348f1-111">元素</span><span class="sxs-lookup"><span data-stu-id="348f1-111">Element</span></span>|<span data-ttu-id="348f1-112">说明</span><span class="sxs-lookup"><span data-stu-id="348f1-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="348f1-113">\<应用></span><span class="sxs-lookup"><span data-stu-id="348f1-113">\<Application></span></span>](application-element-net-native.md)|<span data-ttu-id="348f1-114">作为应用程序范围内的类型和其元数据可以用于反射的类型成员的容器而服务。</span><span class="sxs-lookup"><span data-stu-id="348f1-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="348f1-115">\<图书馆></span><span class="sxs-lookup"><span data-stu-id="348f1-115">\<Library></span></span>](library-element-net-native.md)|<span data-ttu-id="348f1-116">定义那些子类型和类型成员在运行时间要求元数据的程序集。</span><span class="sxs-lookup"><span data-stu-id="348f1-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="348f1-117">备注</span><span class="sxs-lookup"><span data-stu-id="348f1-117">Remarks</span></span>  
 <span data-ttu-id="348f1-118">每个运行时指令文件都可以只包含一个 `<Directives>` 元素。</span><span class="sxs-lookup"><span data-stu-id="348f1-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="348f1-119">该`<Directives>`元素可以包含零或一个[\<应用程序>](application-element-net-native.md)元素，以及零、一个或多个[\<库>](library-element-net-native.md)元素。</span><span class="sxs-lookup"><span data-stu-id="348f1-119">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="348f1-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="348f1-120">See also</span></span>

- [<span data-ttu-id="348f1-121">运行时指令 (rd.xml) 配置文件引用</span><span class="sxs-lookup"><span data-stu-id="348f1-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="348f1-122">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="348f1-122">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
